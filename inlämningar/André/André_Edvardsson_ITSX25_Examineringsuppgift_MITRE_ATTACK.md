# Individuell examineringsuppgift – MITRE ATT&CK och hotanalys

**Kurs:** ITSX25 Kurs 6
**Namn:** André Edvardsson
**Uppdaterad:** 2026-09-05

## Syfte och avgränsning

Uppgiften utgår från Workshop 2 och 3 och behandlar MITRE ATT&CK, TTP, defensiv hotanalys, attackkedjor, försvarsfrågor, källor, spårbarhet och koppling till projektarbetet.

Analysen bygger på gruppens tänkta scenario med ett kapat Microsoft 365-konto. Vi har inte undersökt en verklig incident eller samlat in riktiga loggar. Beskrivningar av aktivitet och signaler är därför exempel på vad ett säkerhetsteam skulle kunna leta efter, inte bekräftade fynd.

Fokus ska ligga på analys, dokumentation och försvar. Tekniska genomförandesteg för angrepp ska inte beskrivas.

## Redovisning av AI-användning

**Verktyg som använts:** Codex, som är en AI-assistent.

**Hur verktyget användes:** Jag använde AI för struktur, utkast till svar, formuleringar och kontroll av att alla frågor hade svar. AI hjälpte även till att jämföra del 6 med gruppens dokumentation och GitHub Issues efter Workshop 3.

**Egen bedömning:** Jag lyfte att ansvarsfördelningen ibland var otydlig trots att instruktioner fanns, särskilt vem som skulle ändra dokument, pusha till GitHub och förklara varför ändringen behövdes. Den erfarenheten har tagits med i kopplingen till Workshop 3.

**Det jag kontrollerade själv:** Kompletteras av André före inlämning med vilka källor och svar jag själv har kontrollerat och om kontrollen ledde till någon ändring. AI:s kontroller ska inte redovisas som mina egna.

---

## Del 1 – Förstå MITRE ATT&CK som analysramverk

### Uppgift 1

**Beskriv med egna ord vad MITRE ATT&CK används till i ett säkerhetsteam.**

> **Svarsinstruktion:** Skriv 150–250 ord. Fokusera på analys, språk, struktur och försvarsperspektiv.

#### Mitt svar

MITRE ATT&CK är ett ramverk som samlar information om hur angripare brukar bete sig. Ett säkerhetsteam kan använda det för att beskriva en attack på ett mer ordnat sätt. I stället för att bara säga att ett konto blev kapat kan man visa vilket mål angriparen hade och vilka tekniker som användes på vägen.

En viktig del är att ATT&CK ger ett gemensamt språk. Teknikerna har namn och ID, vilket gör det lättare för olika personer att förstå varandra. En analytiker kan till exempel hänvisa till `T1566.002 – Spearphishing Link` i stället för att bara skriva att användaren klickade på en misstänkt länk.

Ramverket kan också användas ur ett försvarsperspektiv. När teamet har identifierat relevanta tekniker kan det undersöka vilka loggar och signaler som finns, vad som går att upptäcka och var försvaret har luckor. Det hjälper teamet att prioritera vilka kontroller som behöver förbättras.

ATT&CK ger däremot inte hela svaret. Teamet behöver fortfarande förstå sin egen miljö och bedöma om tekniken verkligen passar det som har observerats. Jag ser därför ATT&CK som ett stöd för analys, dokumentation och kommunikation.

### Uppgift 2

**Förklara varför ATT&CK inte ska användas som en checklista för att ”göra attacker”.**

> **Svarsinstruktion:** Skriv 150–250 ord. Beskriv skillnaden mellan analysramverk och angreppsinstruktion.

#### Mitt svar

ATT&CK ska inte användas som en checklista för att genomföra attacker. Ramverket beskriver beteenden som har observerats i verkliga händelser, men syftet i den här uppgiften är att förstå och försvara sig mot dem. Det visar vad en angripare kan försöka uppnå och vilka typer av metoder som kan förekomma.

Ett analysramverk hjälper ett säkerhetsteam att sortera information. Teamet kan koppla observationer till tactics och techniques, jämföra olika händelser och se vilka delar av en attackkedja som behöver undersökas mer. En angreppsinstruktion skulle däremot beskriva exakt hur någon ska göra, till exempel konkreta kommandon eller steg för att utnyttja ett system. Sådana detaljer behövs inte för att besvara försvarsfrågorna.

Det finns också en risk att en checklista blir missvisande. Att en organisation har en kontroll mot en teknik betyder inte att alla varianter av tekniken är hanterade. Angripare kan ändra sitt arbetssätt, och samma observation kan ibland passa in på flera tekniker.

I vårt arbete använder vi därför ATT&CK för att beskriva scenariot, kontrollera våra antaganden och formulera frågor om upptäckt och skydd. Fokus ligger på vad säkerhetsteamet behöver se och följa upp, inte på att lära ut hur attacken genomförs.

### Uppgift 3

**Välj fem tactics från Enterprise Matrix och beskriv vad varje tactic betyder på en övergripande nivå.**

> **Svarsinstruktion:** Använd egna ord. Undvik tekniska genomförandedetaljer.

#### Mitt svar

| # | Tactic | Övergripande betydelse |
| ---: | --- | --- |
| 1 | Initial Access | Angriparen försöker få en första väg in i organisationens miljö. |
| 2 | Credential Access | Angriparen försöker få tillgång till lösenord eller annat material som kan användas för inloggning. |
| 3 | Discovery | Angriparen försöker förstå miljön, till exempel vilka konton, system och resurser som finns. |
| 4 | Collection | Angriparen samlar information som är intressant för målet med attacken. |
| 5 | Impact | Angriparen försöker påverka verksamheten, informationen eller tillgängligheten. |

### Uppgift 4

**Beskriv hur ATT&CK kan stödja kommunikationen mellan red team, blue team och ledning.**

> **Svarsinstruktion:** Skriv 200–300 ord. Ta upp gemensamt språk, spårbarhet och prioritering.

#### Mitt svar

MITRE ATT&CK kan fungera som ett gemensamt språk mellan red team, blue team och ledning. Red team kan använda teknikerna för att beskriva vilka beteenden som ska simuleras i ett godkänt test. Blue team kan använda samma tekniker för att undersöka om beteendena går att upptäcka och vilka loggar eller kontroller som behövs.

Det gemensamma språket minskar risken för missförstånd. Om båda teamen använder samma tekniknamn och ID blir det tydligare vad som testades och vad resultatet betyder. Det ger också bättre spårbarhet. En observation i en logg kan kopplas till en teknik, som sedan kan kopplas till en detektionsregel, en säkerhetsåtgärd eller en uppgift i backloggen.

För ledningen kan ATT&CK hjälpa till att göra tekniska resultat mer begripliga. Ledningen behöver inte känna till varje detalj, men kan få en bild av vilka delar av en attackkedja organisationen kan upptäcka och var det finns luckor. Resultatet kan exempelvis visa att organisationen har bra skydd mot nätfiske men saknar tillräcklig övervakning efter en lyckad inloggning.

ATT&CK kan även stödja prioritering. Teamet kan välja de tekniker som är mest relevanta för den egna hotbilden och börja med de största riskerna. Det är viktigt att inte försöka täcka hela matrisen direkt. Valen behöver motiveras och följas upp så att både tekniker och ledning förstår varför en åtgärd prioriteras.

---

## Del 2 – TTP: Tactic, Technique och Procedure

### Uppgift 5

**Förklara skillnaden mellan tactic, technique och procedure.**

> **Svarsinstruktion:** Använd ett eget defensivt exempel. Håll dig på konceptuell nivå.

#### Mitt svar

| Begrepp | Förklaring med egna ord | Del av mitt defensiva exempel |
| --- | --- | --- |
| Tactic | Angriparens övergripande mål, alltså varför något görs. | Målet är att få en första väg in i Microsoft 365-miljön. |
| Technique | Metoden eller beteendet som används för att nå målet. | Ett mejl innehåller en länk till en falsk inloggningssida. |
| Procedure | Hur tekniken visar sig i det aktuella scenariot. | Mejlet ser ut att komma från en leverantör och handlar om en uppdaterad offert. |

### Uppgift 6

**Skapa en TTP-förklaring för tre valfria ATT&CK-tekniker.**

> **Svarsinstruktion:** För varje teknik: skriv tactic, technique och en kort procedure-beskrivning utan operativa instruktioner.

#### Mitt svar

| # | Tactic | Technique och ID | Kort procedure-beskrivning |
| ---: | --- | --- | --- |
| 1 | Initial Access | T1566.002 – Spearphishing Link | Användaren får ett leverantörsmejl med en länk som leder till en falsk Microsoft 365-inloggning. |
| 2 | Discovery | T1087.004 – Account Discovery: Cloud Account | Efter inloggningen försöker angriparen förstå vilka användare och roller som finns i molnmiljön. |
| 3 | Collection | T1114.003 – Email Forwarding Rule | En regel skapas som kan skicka utvalda mejl vidare till en extern adress. |

### Uppgift 7

**Välj en tactic och identifiera tre tekniker som kan höra hemma inom den.**

> **Svarsinstruktion:** Motivera varför teknikerna passar in i tacticen.

#### Vald tactic

**Tactic:** Initial Access

#### Mitt svar

| # | Technique och ID | Varför passar tekniken i tacticen? |
| ---: | --- | --- |
| 1 | T1566 – Phishing | Phishing används för att försöka få den första kontakten eller åtkomsten genom att lura en användare. |
| 2 | T1078 – Valid Accounts | Ett giltigt men kapat konto kan användas för att komma in på ett sätt som liknar en vanlig inloggning. |
| 3 | T1190 – Exploit Public-Facing Application | En sårbar tjänst som är tillgänglig från internet kan ge angriparen en första väg in. |

### Uppgift 8

**Beskriv varför det kan vara svårt att mappa en observation till rätt teknik.**

> **Svarsinstruktion:** Ta upp osäkerhet, kontext, datakvalitet och behov av källor.

#### Mitt svar

Det kan vara svårt eftersom en observation sällan berättar hela historien. En ovanlig inloggning visar till exempel att något avviker, men inte automatiskt varför det hände eller vem som låg bakom. Samma händelse kan också vara legitim, till exempel om en användare reser eller byter enhet.

Kontexten är därför viktig. Analytikern behöver veta hur användaren brukar arbeta, vilka system som berörs och vad som hände före och efter observationen. Datakvaliteten påverkar också bedömningen. Om viktiga loggar saknas eller tiderna inte stämmer blir mappningen mer osäker.

För att minska risken för fel behöver man läsa hela beskrivningen på MITRE ATT&CK, jämföra med fler källor och dokumentera varför tekniken valdes. Om det finns flera möjliga tekniker bör även det skrivas ner. En granskning av någon annan i gruppen kan hjälpa till att upptäcka en för snabb eller felaktig slutsats.

---

## Del 3 – Bygg en defensiv attackkedja

### Uppgift 9

**Bygg en enkel attackkedja med 3–5 steg.**

> **Svarsinstruktion:** Använd tactics som etiketter. Syftet är analys och försvar, inte teknisk genomförandeinstruktion.

#### Mitt svar

| Steg | Tactic | Technique och ID | Övergripande händelse |
| ---: | --- | --- | --- |
| 1 | Initial Access | T1566.002 – Spearphishing Link | Ett falskt leverantörsmejl leder till en falsk Microsoft 365-sida. |
| 2 | Initial Access | T1078.004 – Valid Accounts: Cloud Accounts | De komprometterade uppgifterna används för att logga in på molnkontot. |
| 3 | Discovery | T1087.004 – Account Discovery: Cloud Account | Angriparen undersöker vilka andra konton och roller som finns. |
| 4 | Collection | T1213.002 – Data from Information Repositories: SharePoint | Information söks fram i organisationens SharePoint. |
| 5 | Collection | T1114.003 – Email Collection: Email Forwarding Rule | En regel skapas för att vidarebefordra vissa mejl. |

### Uppgift 10

**Beskriv varje steg i kedjan med ”varför”, ”hur” och ”vad såg vi?”.**

> **Svarsinstruktion:** Koppla till TTP-modellen: tactic, technique och procedure.

#### Mitt svar

Tabellen beskriver tänkbara händelser i scenariot. Rubriken ”vad såg vi?” ska här förstås som vad vi skulle leta efter, eftersom vi inte har verkliga loggfynd.

| Steg | Varför? – Tactic | Hur? – Technique | Tänkt procedure eller möjlig observation |
| ---: | --- | --- | --- |
| 1 | Förbereda en första åtkomst till miljön | Använda en riktad nätfiskelänk | Ett mejl som liknar kommunikation från en känd leverantör. |
| 2 | Få åtkomst till molnmiljön | Använda ett giltigt men kapat konto | En inloggning sker med användarens riktiga konto från en avvikande session. |
| 3 | Förstå organisationens konton | Söka efter molnkonton och roller | Kontot börjar göra ovanliga sökningar efter andra användare. |
| 4 | Samla verksamhetsinformation | Söka i SharePoint | Ovanligt många dokument eller känsliga områden öppnas. |
| 5 | Fortsätta samla mejl | Skapa en vidarebefordringsregel | En ny regel skickar mejl till en extern adress. |

### Uppgift 11

**Identifiera vilka steg i attackkedjan som är mest osäkra.**

> **Svarsinstruktion:** Beskriv vad du behöver veta mer om för att göra analysen bättre.

#### Mitt svar

| Osäkert steg | Vad är osäkert? | Vad behöver jag veta eller kontrollera? |
| --- | --- | --- |
| Steg 1 till 2 | Vi antar att användaren faktiskt lämnar sina uppgifter och att angriparen kan logga in. | Information om MFA, inloggningsförloppet och om länken verkligen samlade in uppgifter. |
| Steg 3 | Vanliga katalogsökningar kan likna legitimt arbete. | En jämförelse med användarens normala aktivitet och relevanta katalogloggar. |
| Steg 5 | En vidarebefordringsregel kan vara tillåten och legitim. | Vem som skapade regeln, vart mejlen skickas och om extern vidarebefordran är normal. |

### Uppgift 12

**Rita eller beskriv attackkedjan som en enkel kedja från första kontakt till påverkan.**

> **Svarsinstruktion:** Använd pilar och korta rubriker. Digitalt kan du använda tabell eller punktlista.

#### Min attackkedja

```text
[Falsk leverantörslänk – T1566.002]
    ↓
[Kapat molnkonto – T1078.004]
    ↓
[Kartläggning av konton – T1087.004]
    ↓
[Sökning i SharePoint – T1213.002]
    ↓
[Vidarebefordring av mejl – T1114.003]
```

---

## Del 4 – Försvarsfrågor och Blue/Purple-perspektiv

### Uppgift 13

**Formulera minst en försvarsfråga per steg i attackkedjan.**

> **Svarsinstruktion:** Exempelvis: Hur skulle detta kunna upptäckas? Vilken signal, rutin eller kontroll kan vara relevant?

#### Mitt svar

| Steg | Technique | Försvarsfråga |
| ---: | --- | --- |
| 1 | T1566.002 | Hur kan vi se att länken leder till en domän som inte tillhör den förväntade tjänsten? |
| 2 | T1078.004 | Hur upptäcker vi att en inloggning med rätt konto ändå är ovanlig? |
| 3 | T1087.004 | Hur märker vi att kontot börjar söka efter fler användare än normalt? |
| 4 | T1213.002 | Hur kan vi upptäcka ovanligt omfattande läsning eller nedladdning från SharePoint? |
| 5 | T1114.003 | Hur upptäcker vi en ny regel som vidarebefordrar mejl till en extern adress? |

### Uppgift 14

**Välj två tekniker och resonera kring möjliga detektionssignaler.**

> **Svarsinstruktion:** Håll svaret på konceptuell nivå. Beskriv typer av signaler, inte tekniska exploit-steg.

#### Mitt svar

| Technique och ID | Möjliga typer av detektionssignaler | Begränsningar eller osäkerheter |
| --- | --- | --- |
| T1078.004 – Valid Accounts: Cloud Accounts | Avvikande plats, ny enhet, ovanlig tidpunkt, förändrade MFA-händelser och annat beteende efter inloggningen. | En legitim användare kan resa eller byta enhet, så en enda signal räcker inte alltid. |
| T1114.003 – Email Forwarding Rule | Skapande eller ändring av regler, extern mottagare och en regel som skapas från en ovanlig session. | Vidarebefordring kan vara legitim och behöver jämföras med organisationens regler och användarens normala arbete. |

### Uppgift 15

**Välj två tekniker och resonera kring möjliga riskreducerande åtgärder.**

> **Svarsinstruktion:** Beskriv organisatoriska, tekniska eller processmässiga åtgärder.

#### Mitt svar

| Technique och ID | Organisatoriska åtgärder | Tekniska åtgärder | Processmässiga åtgärder |
| --- | --- | --- | --- |
| T1566.002 – Spearphishing Link | Utbilda användare att kontrollera länkar och rapportera misstänkta mejl. | E-postfiltrering, domänkontroller och skydd mot kända skadliga länkar. | Ha en tydlig rutin för rapportering och snabb spärr av misstänkta länkar. |
| T1078.004 – Valid Accounts: Cloud Accounts | Informera användare om att aldrig godkänna oväntade MFA-förfrågningar. | MFA, villkorsstyrd åtkomst och begränsade behörigheter. | Regelbunden granskning av inloggningar och snabb återställning av misstänkta konton. |

### Uppgift 16

**Beskriv hur ett säkerhetsteam kan använda en attackkedja för att förbättra sitt försvar.**

> **Svarsinstruktion:** Skriv 200–300 ord. Ta upp lärande, prioritering och uppföljning.

#### Mitt svar

En attackkedja hjälper säkerhetsteamet att se en händelse som flera steg i stället för ett enda larm. Det gör det lättare att förstå hur en angripare kan gå från första kontakt till att få tillgång till information. När stegen finns dokumenterade kan teamet diskutera var attacken hade kunnat upptäckas eller stoppas.

Kedjan kan också användas för lärande. Efter en incident eller övning kan teamet jämföra vad man förväntade sig med det som faktiskt syntes i loggarna. Om ett steg inte gick att se kan det betyda att loggning saknas eller att en detektionsregel behöver förbättras. Om ett larm kom men ingen reagerade kan rutinen för hantering behöva ändras.

För prioritering kan teamet bedöma vilka steg som har störst risk och vilka skydd som ger bäst effekt. Det är ofta bättre att börja med några relevanta tekniker än att försöka täcka hela ATT&CK-matrisen. I vårt scenario kan det vara viktigt att både minska risken för nätfiske och upptäcka vad som händer efter en lyckad molninloggning.

Kedjan behöver följas upp när miljön eller hotbilden ändras. Teamet kan lägga förbättringar i backloggen, ge dem ansvarig person och kontrollera senare om skyddet har blivit bättre. På det sättet blir attackkedjan ett underlag för fortsatt säkerhetsarbete och inte bara en bild i en rapport.

---

## Del 5 – Källor, spårbarhet och kvalitet

### Uppgift 17

**Dokumentera vilka källor du använder i din ATT&CK-analys.**

> **Svarsinstruktion:** Skriv minst tre källor eller länkar. Beskriv kort vad varje källa bidrar med.

#### Mitt svar

| # | Källa och länk | Vad bidrar källan med? | Hämtad/kontrollerad datum |
| ---: | --- | --- | --- |
| 1 | [MITRE ATT&CK Enterprise Matrix](https://attack.mitre.org/matrices/enterprise/) | Visar ramverkets tactics och vilka tekniker som hör till dem. | 2026-08-31 |
| 2 | [MITRE – Spearphishing Link](https://attack.mitre.org/techniques/T1566/002/) | Ger teknikens namn, ID, tactic och beskrivning. | 2026-08-31 |
| 3 | [MITRE – Valid Accounts: Cloud Accounts](https://attack.mitre.org/techniques/T1078/004/) | Förklarar hur giltiga molnkonton kan missbrukas och vilka tactics som är relevanta. | 2026-08-31 |
| 4 | [CISA – Best Practices for MITRE ATT&CK Mapping](https://www.cisa.gov/news-events/news/best-practices-mitre-attckr-mapping) | Ger vägledning om att mappa observationer noggrant och dokumentera sammanhanget. | 2026-08-31 |

### Uppgift 18

**Beskriv hur du säkerställer att din TTP-mappning är rimlig.**

> **Svarsinstruktion:** Ta upp källa, motivering, osäkerhet och gruppgranskning.

#### Mitt svar

Jag börjar med att läsa teknikens fullständiga beskrivning på MITRE ATT&CK och kontrollerar att både beteendet och tacticen passar vårt scenario. Jag väljer alltså inte en teknik bara för att namnet låter rätt. Sedan skriver jag en kort motivering som kopplar observationen i scenariot till teknikens beskrivning.

Om information saknas markerar jag vad som är ett antagande och vad som faktiskt är känt. Jag jämför också med andra möjliga tekniker om mappningen är osäker. Källan och länken dokumenteras så att någon annan kan kontrollera samma information. Till sist låter jag en annan gruppmedlem läsa mappningen. Om personen inte förstår sambandet eller hittar en bättre teknik behöver valet diskuteras och eventuellt ändras.

### Uppgift 19

**Skapa en mini-Definition of Done för en färdig hotanalys.**

> **Svarsinstruktion:** Lista minst fem kriterier. Kriterierna ska gå att använda av hela gruppen.

#### Mitt svar

- Scenariot och syftet med analysen är tydligt beskrivna.
- Varje steg har en motiverad tactic, technique och procedure.
- Teknikernas namn och ID har kontrollerats mot MITRE ATT&CK.
- Försvarsfrågor och relevanta osäkerheter är dokumenterade.
- Källorna är angivna och går att öppna.
- Minst en annan person har granskat analysen.
- Synpunkter från granskningen är hanterade och statusen är uppdaterad.

### Uppgift 20

**Beskriv vad som gör en hotanalys användbar för någon annan än den som skrev den.**

> **Svarsinstruktion:** Skriv 150–250 ord. Fokusera på tydlighet, spårbarhet och mottagare.

#### Mitt svar

En hotanalys blir användbar när mottagaren kan förstå vad som har analyserats, varför det är relevant och hur slutsatserna togs fram. Texten behöver därför ha ett tydligt scenario och en logisk struktur. Begrepp och förkortningar bör förklaras så att även någon som inte gjorde analysen kan följa med.

Spårbarhet är också viktigt. Det ska gå att se vilka källor som användes, vilka observationer som stödjer mappningen och vad som bara är ett antagande. MITRE-tekniker bör ha både namn, ID och länk. Om analysen innehåller osäkerheter ska de skrivas ut i stället för att döljas.

Mottagaren påverkar hur resultatet presenteras. En teknisk analytiker kan behöva mer information om loggar och signaler, medan en chef främst behöver förstå risken, påverkan och vilka åtgärder som bör prioriteras. Det viktigaste bör därför komma fram tydligt utan att läsaren behöver leta i hela dokumentet.

Till sist behöver analysen ge stöd för nästa steg. Det kan vara försvarsfrågor, rekommenderade kontroller eller nya backlog items. Då blir analysen något som går att använda i fortsatt arbete och inte bara en beskrivning av vad som redan har hänt.

---

## Del 6 – Koppling till backlog, sprint och Workshop 3

### Uppgift 21

**Uppdatera er backlog baserat på det ni upptäckte i Workshop 2.**

> **Svarsinstruktion:** Skriv minst fem nya eller ändrade backlog items. Ge en kort motivering.

#### Mitt svar

Efter Workshop 3 finns följande förbättringar i gruppens GitHub Issues. De är öppna vid uppdateringen av den här texten den 5 september 2026.

| Issue | Nytt eller ändrat backlog item | Kort beskrivning | Prioritet | Motivering |
| --- | --- | --- | --- | --- |
| [#19](https://github.com/Kurs6-Projekt/itsx25-kurs6-grupp3/issues/19) | Identifiera relevanta loggar | Hitta minst en relevant loggkälla för varje steg i attackkedjan. | Must | Vi behöver veta vilket underlag som kan användas för att upptäcka kedjan. |
| [#20](https://github.com/Kurs6-Projekt/itsx25-kurs6-grupp3/issues/20) | Förtydliga MFA-antagandet | Beskriv hur MFA påverkar möjligheten att använda stulna uppgifter. | Must | Övergången från nätfiske till kapat konto är en viktig osäkerhet. |
| [#3](https://github.com/Kurs6-Projekt/itsx25-kurs6-grupp3/issues/3) | Tydligare ansvarsfördelning | Ge varje uppgift en tydlig ansvarig. | Must | Det har ibland varit oklart vem som ska göra vad, även när instruktioner finns. |
| [#16](https://github.com/Kurs6-Projekt/itsx25-kurs6-grupp3/issues/16) | Gemensamt GitHub-arbetsflöde | Bestäm vem som ändrar, granskar och pushar. | Must | Gruppen behöver förstå både vad som ändras och varför. |
| [#21](https://github.com/Kurs6-Projekt/itsx25-kurs6-grupp3/issues/21) | Lägg till officiella Microsoft-källor | Komplettera analysen med relevanta källor om Microsoft 365. | Should | Det gör de tekniska resonemangen lättare att kontrollera. |

Visualiseringen är redan klar i [gruppens hotanalys](../../docs/workshop-2-hotanalys.md), och [Issue #15](https://github.com/Kurs6-Projekt/itsx25-kurs6-grupp3/issues/15) är stängd. Den ska därför inte längre beskrivas som en ny uppgift. De öppna förbättringarna behöver fortfarande genomföras och följas upp mot sina klarkriterier.

### Uppgift 22

**Beskriv hur er attackkedja förhåller sig till ert Sprint Goal.**

> **Svarsinstruktion:** Är sprintmålet fortfarande relevant? Behöver något justeras?

#### Mitt svar

**Sprint 1-målet, sammanfattat:** Gruppen ska etablera ett gemensamt arbetssätt, färdigställa Team Charter och backlog samt bygga en grundläggande förståelse för MITRE ATT&CK och hotanalys. Den fullständiga formuleringen finns i [Sprint Goal och Definition of Done](../../docs/sprint-goal-and-dod.md).

**Min bedömning:** Vi har till stor del uppnått målet. Gruppen har skapat en attackkedja, mappat fem tekniker och dokumenterat försvarsfrågor och osäkerheter. Samtidigt visade Workshop 3 att arbetssättet behöver bli tydligare. Jag upplevde att det ibland var oklart vem som skulle ändra och pusha dokument, även när instruktioner fanns. Att en rutin är dokumenterad betyder därför inte att den fungerar fullt ut i praktiken.

**Förslag till nästa sprintmål:** Nästa sprint ska ge oss en mer användbar hotanalys genom tydliga MFA-antaganden och relevanta loggkällor, med en ansvarig för varje uppgift. Detta är ett förslag och inte ett nytt mål som gruppen redan har beslutat om.

### Uppgift 23

**Formulera minst två uppföljningsfrågor inför Workshop 3.**

> **Svarsinstruktion:** Frågorna ska kunna användas vid review eller retrospektiv.

#### Mitt svar

1. Vilka delar av attackkedjan kunde vi mappa med bra underlag, och vilka bygger fortfarande mest på antaganden?
2. Vilken förbättring bör prioriteras först för att göra analysen mer användbar ur ett Blue Team-perspektiv?

Efter Workshop 3 är frågorna fortfarande relevanta. I [retrospektivet](../../docs/workshop-3-retrospektiv.md) lyfte gruppen både osäkerheten kring loggar och behovet av tydligare ansvar. Uppföljningen behöver därför omfatta både analysens kvalitet och hur vi fördelar arbetet.

### Uppgift 24

**Förbered en kort statusrapport till Workshop 3.**

> **Svarsinstruktion:** Skriv 5–7 punkter: vad ni gjorde, vad som blev klart, vad som är oklart och vad ni vill ändra.

#### Min statusrapport, uppdaterad efter Workshop 3

- **Detta gjorde vi:** Vi valde ett scenario med ett kapat Microsoft 365-konto och byggde en attackkedja med fem steg.
- **Detta blev klart:** Alla steg kopplades till tactics, techniques och ATT&CK-ID.
- **Detta blev också klart:** Vi skrev minst en försvarsfråga per steg, dokumenterade våra viktigaste osäkerheter och skapade ett diagram över attackkedjan.
- **Detta är fortfarande oklart:** Vi vet inte exakt vilka Microsoft 365-loggar som ger bäst möjlighet att upptäcka hela kedjan.
- **Detta behöver följas upp:** MFA, normalt användarbeteende och extern vidarebefordring behöver undersökas mer.
- **Detta lärde vi oss om arbetssättet:** Ansvar för uppgifter, ändringar och pushar behöver vara tydligare, vilket också togs upp i retrospektivet.
- **Detta tar vi vidare:** Förbättringarna finns som prioriterade Issues. Nästa steg är att fördela ansvar och genomföra dem, bland annat arbetet med loggkällor och MFA.

---

## Frivillig fördjupningsutmaning

**Skapa en komplett mini-hotanalys baserad på din Workshop 2-kedja.**

> Inkludera mål med analysen, attackkedja, TTP-tabell, försvarsfrågor, källor, osäkerheter, uppdaterad backlog och förslag till nästa sprint. Max tre sidor.

### Mål med analysen

Den frivilliga fördjupningsutmaningen har inte genomförts.

### Attackkedja

Ej genomförd.

### TTP-tabell

| Steg | Tactic | Technique | Procedure/observation |
| ---: | --- | --- | --- |
| – | Ej genomförd | – | – |

### Försvarsfrågor

Ej genomförd.

### Källor

Ej genomförd.

### Osäkerheter

Ej genomförd.

### Uppdaterad backlog

Ej genomförd.

### Förslag till nästa sprint

Ej genomförd.

---

## Rekommenderade referenser

- [MITRE ATT&CK](https://attack.mitre.org/)
- [MITRE ATT&CK Enterprise Matrix](https://attack.mitre.org/matrices/enterprise/)
- [CISA – Best Practices for MITRE ATT&CK Mapping](https://www.cisa.gov/news-events/news/best-practices-mitre-attckr-mapping)
- [MITRE ATT&CK Data & Tools](https://attack.mitre.org/resources/attack-data-and-tools/)

## Egen slutkontroll före inlämning

- [ ] Jag har besvarat uppgift 1–24.
- [ ] Jag har följt angivna ordgränser.
- [ ] Jag har hållit analysen defensiv och undvikit operativa angreppsinstruktioner.
- [ ] Jag har använt TTP-begreppen konsekvent.
- [ ] Jag har motiverat mina val och dokumenterat osäkerheter.
- [ ] Jag har angett minst tre källor och kontrollerat länkarna.
- [ ] Jag har kopplat analysen till backlog, Sprint Goal eller Definition of Done.
- [ ] Jag har beskrivit eventuell AI-användning och vad jag kontrollerat manuellt.
- [ ] Jag har läst igenom texten och kontrollerat att den uttrycker mina egna resonemang.
