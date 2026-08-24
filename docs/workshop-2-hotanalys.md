# Workshop 2 – MITRE ATT&CK och hotanalys

**Kurs:** ITSX25 – Kurs 6  
**Grupp:** Grupp 3  
**Scenario:** Kapat Microsoft 365-konto genom falsk leverantörslänk

---

## 1. Scenario

Vi har valt ett scenario där en person på ett företag får ett mejl som ser ut att komma från en leverantör som företaget redan har kontakt med. Mejlet innehåller en länk till en falsk inloggningssida som efterliknar Microsoft 365.

I scenariot antar vi att användaren skriver in sina inloggningsuppgifter på den falska sidan. Angriparen får då tillgång till uppgifterna och använder dem för att logga in på användarens riktiga Microsoft 365-konto.

När angriparen har kommit in försöker denne kartlägga organisationens användare, söka efter information i SharePoint och skapa en vidarebefordringsregel för att få tillgång till framtida mejl.

Vi valde scenariot eftersom det är realistiskt och visar hur en angripare kan missbruka ett riktigt konto och vanliga Microsoft 365-funktioner utan att installera traditionell malware.

---

## 2. Attackkedja

Vi har valt fem MITRE ATT&CK-tekniker som tillsammans bildar en sammanhängande attackkedja:

```text
Initial Access
Spearphishing Link
T1566.002
        ↓
Initial Access
Valid Accounts: Cloud Accounts
T1078.004
        ↓
Discovery
Account Discovery: Cloud Account
T1087.004
        ↓
Collection
Data from Information Repositories: SharePoint
T1213.002
        ↓
Collection
Email Collection: Email Forwarding Rule
T1114.003
```

Kedjan kan sammanfattas så här:

> Falskt leverantörsmejl → stulna inloggningsuppgifter → kapat molnkonto → kartläggning av användare → sökning i SharePoint → vidarebefordring av mejl.

---

## 3. TTP-analys

TTP står för **Tactics, Techniques and Procedures**:

- **Tactic:** Vad angriparen försöker uppnå.
- **Technique:** Hur angriparen försöker uppnå målet.
- **Procedure:** Hur tekniken används i vårt konkreta scenario.

| Steg | Tactic | Technique | Procedure i vårt scenario |
| ---: | --- | --- | --- |
| 1 | Initial Access | **T1566.002 – Spearphishing Link** | Ett riktat mejl ser ut att komma från en känd leverantör. Mejlet innehåller en länk till en falsk Microsoft 365-inloggning. |
| 2 | Initial Access | **T1078.004 – Valid Accounts: Cloud Accounts** | Angriparen använder de komprometterade inloggningsuppgifterna för att logga in på användarens riktiga molnkonto. |
| 3 | Discovery | **T1087.004 – Account Discovery: Cloud Account** | Angriparen undersöker vilka användare och konton som finns samt vilka som verkar arbeta med ekonomi, administration eller IT. |
| 4 | Collection | **T1213.002 – Data from Information Repositories: SharePoint** | Angriparen söker i SharePoint efter avtal, kontaktlistor, interna rutiner och annat värdefullt projektmaterial. |
| 5 | Collection | **T1114.003 – Email Collection: Email Forwarding Rule** | Angriparen skapar en regel som vidarebefordrar utvalda mejl till en extern adress för att behålla insyn i kommunikationen. |

Vi använder `T1078.004` som **Initial Access** eftersom angriparen i vårt scenario använder det komprometterade molnkontot för att få åtkomst till organisationens miljö.

---

## 4. Försvarsfrågor

### T1566.002 – Spearphishing Link

**Försvarsfråga:** Hur kan vi upptäcka att ett mejl som verkar komma från en känd leverantör leder till en falsk inloggningssida?

**Det vi skulle undersöka:**

- avsändarens adress och domän
- länkens verkliga URL och rykte
- om måldomänen tillhör Microsoft
- resultat från e-postfiltrering
- användarnas rapporter om misstänkta mejl

### T1078.004 – Valid Accounts: Cloud Accounts

**Försvarsfråga:** Hur skiljer vi en riktig användare från en angripare som använder användarens konto?

**Det vi skulle undersöka:**

- inloggningsplats och IP-adress
- vilken enhet som används
- tidpunkten för inloggningen
- misslyckade eller ovanliga MFA-händelser
- förändringar i användarens normala beteende

### T1087.004 – Account Discovery: Cloud Account

**Försvarsfråga:** Hur upptäcker vi att ett vanligt konto plötsligt börjar kartlägga andra användare och roller?

**Det vi skulle undersöka:**

- ovanligt många katalogfrågor
- kontosökningar som inte hör till användarens arbetsuppgifter
- ovanliga anrop mot Microsoft Graph eller andra API:er
- sökningar efter administratörer och privilegierade konton

### T1213.002 – Data from Information Repositories: SharePoint

**Försvarsfråga:** Hur upptäcker vi att någon söker igenom eller laddar ner ovanligt mycket information från SharePoint?

**Det vi skulle undersöka:**

- åtkomst till känsliga webbplatser och filer
- stora mängder läsningar eller nedladdningar
- nya externa delningar
- aktivitet från oväntade platser eller enheter
- beteenden som avviker från användarens normala arbete

### T1114.003 – Email Collection: Email Forwarding Rule

**Försvarsfråga:** Hur upptäcker vi en misstänkt vidarebefordringsregel innan information hinner samlas in?

**Det vi skulle undersöka:**

- nya eller ändrade inbox- och transportregler
- automatisk vidarebefordran till externa adresser
- vem som skapade regeln
- när och från vilken session regeln skapades
- om beteendet är normalt för användaren

---

## 5. Varför är attackkedjan rimlig?

Attackkedjan är rimlig eftersom varje steg skapar förutsättningar för nästa steg. Nätfiskemejlet används för att samla in inloggningsuppgifter. Uppgifterna används sedan för att logga in på ett riktigt molnkonto.

När angriparen har åtkomst kan denne kartlägga organisationen och identifiera intressanta användare och informationskällor. Därefter kan angriparen söka efter dokument i SharePoint och skapa en vidarebefordringsregel för att fortsätta samla in mejl.

Det intressanta ur ett försvarsperspektiv är att flera steg använder legitima funktioner. Det gör att ett säkerhetsteam inte enbart kan leta efter skadlig kod. Inloggningsmönster, användarbeteende och flera kombinerade signaler behöver också analyseras.

---

## 6. Uppdatering av Product Backlog

Följande backlog items har behandlats under Workshop 2:

| Backlog item | Kort beskrivning | Prioritet | Status |
| --- | --- | --- | --- |
| Välja scenario | Välja ett realistiskt scenario för gruppens hotanalys. | Must | Done |
| Skapa attackkedja | Skapa en sammanhängande attackkedja med fem steg. | Must | Done |
| Mappa mot MITRE ATT&CK | Koppla varje steg till rätt tactic, technique och ID. | Must | Done |
| Beskriva TTP:er | Förklara angriparens mål, metod och konkreta agerande. | Must | Done |
| Formulera försvarsfrågor | Identifiera vad ett Blue Team behöver upptäcka eller stoppa. | Should | Done |
| Dokumentera osäkerheter | Samla frågor och områden som behöver undersökas vidare. | Should | Done |

---

## 7. Uppföljning av Sprint Goal

> **Sprint Goal:** Sprintens mål är att etablera ett gemensamt arbetssätt och förbereda gruppen för att påbörja en MITRE ATT&CK-baserad hotanalys.

Vi bedömer att sprintmålet är uppnått eftersom gruppen har:

- valt och dokumenterat ett scenario
- skapat en sammanhängande attackkedja
- kopplat kedjan till relevanta MITRE ATT&CK-tekniker
- formulerat frågor ur ett försvarsperspektiv
- dokumenterat kvarvarande osäkerheter
- granskat och godkänt arbetet gemensamt

Gruppen är därför redo att fortsätta med en mer fördjupad analys.

---

## 8. Kontroll mot Definition of Done

Följande kriterier är uppfyllda:

- [x] Uppgiftens syfte och krav är uppfyllda.
- [x] Attackkedjan är dokumenterad och går att följa.
- [x] Teknikerna har namn och MITRE ATT&CK-ID.
- [x] Varje steg har en tactic, technique och procedure.
- [x] Försvarsfrågor finns för varje steg.
- [x] Osäkerheter och fortsatta frågor är dokumenterade.
- [x] Innehållet har granskats gemensamt av gruppen.
- [x] Dokumentationen är sparad i gruppens GitHub-repository.
- [x] Resultatet är redo att presenteras.

Vi bedömer därför att gruppens Definition of Done är uppfylld för denna del av arbetet.

---

## 9. Osäkerheter

Vi har identifierat följande osäkerheter:

- Vi vet inte exakt vilka Microsoft 365-loggar som är viktigast för att upptäcka hela attackkedjan.
- Det kan vara svårt att avgöra när normal användaraktivitet börjar bli misstänkt.
- Vi är osäkra på hur lätt det är att upptäcka en angripare som använder rätt användarnamn och lösenord.
- En vidarebefordringsregel kan vara legitim och behöver därför bedömas tillsammans med andra signaler.
- Vi behöver undersöka hur MFA påverkar möjligheten att använda stulna inloggningsuppgifter.

---

## 10. Slutsats

Analysen visar att en attack mot Microsoft 365 inte måste innehålla traditionell malware. En angripare kan missbruka ett riktigt konto och legitima funktioner som SharePoint och vidarebefordringsregler.

Det gör identitets- och beteendeanalys viktig. En enskild signal behöver inte vara tillräcklig för att upptäcka attacken. Det är mer användbart att koppla samman ett ovanligt inloggningsmönster med efterföljande kontosökningar, omfattande SharePoint-aktivitet eller en ny vidarebefordringsregel.

---

## 11. Frågor till Workshop 3

1. Vilka loggar är viktigast för att upptäcka den här attackkedjan?
2. I vilket steg har säkerhetsteamet bäst möjlighet att stoppa angriparen?
3. Vilka signaler behöver kombineras för att upptäcka ett kapat konto?
4. Hur kan MFA och andra identitetsskydd minska risken?
5. Behöver vi ändra något i Product Backlog eller Definition of Done efter analysen?

---

## 12. Källor

- [MITRE ATT&CK Enterprise Matrix](https://attack.mitre.org/matrices/enterprise/)
- [T1566.002 – Spearphishing Link](https://attack.mitre.org/techniques/T1566/002/)
- [T1078.004 – Valid Accounts: Cloud Accounts](https://attack.mitre.org/techniques/T1078/004/)
- [T1087.004 – Account Discovery: Cloud Account](https://attack.mitre.org/techniques/T1087/004/)
- [T1213.002 – Data from Information Repositories: SharePoint](https://attack.mitre.org/techniques/T1213/002/)
- [T1114.003 – Email Collection: Email Forwarding Rule](https://attack.mitre.org/techniques/T1114/003/)
- Kursmaterial för Workshop 2
