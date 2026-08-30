# Individuell inlämningsuppgift – Workshop 2

**Kurs:** ITSX25 Kurs 6
**Namn:** André Edvardsson
**Datum:** ____________________

## Syfte och avgränsning

Uppgiften följer upp Workshop 2 och behandlar MITRE ATT&CK, TTP, defensiv hotanalys, attackkedjor, försvarsfrågor, källor, spårbarhet och koppling till projektarbetet.

Fokus ska ligga på analys, dokumentation och försvar. Tekniska genomförandesteg för angrepp ska inte beskrivas.

## Redovisning av AI-användning

> Beskriv om och hur en AI-assistent har använts samt vad du har kontrollerat manuellt.

**Verktyg som använts:**

**Hur verktyget användes:**

**Det jag kontrollerade manuellt:**

---

## Del 1 – Förstå MITRE ATT&CK som analysramverk

### Uppgift 1

**Beskriv med egna ord vad MITRE ATT&CK används till i ett säkerhetsteam.**

> **Svarsinstruktion:** Skriv 150–250 ord. Fokusera på analys, språk, struktur och försvarsperspektiv.

#### Mitt svar

<!-- Skriv ditt svar här. -->



### Uppgift 2

**Förklara varför ATT&CK inte ska användas som en checklista för att ”göra attacker”.**

> **Svarsinstruktion:** Skriv 150–250 ord. Beskriv skillnaden mellan analysramverk och angreppsinstruktion.

#### Mitt svar

<!-- Skriv ditt svar här. -->



### Uppgift 3

**Välj fem tactics från Enterprise Matrix och beskriv vad varje tactic betyder på en övergripande nivå.**

> **Svarsinstruktion:** Använd egna ord. Undvik tekniska genomförandedetaljer.

#### Mitt svar

| # | Tactic | Övergripande betydelse |
| ---: | --- | --- |
| 1 |  |  |
| 2 |  |  |
| 3 |  |  |
| 4 |  |  |
| 5 |  |  |

### Uppgift 4

**Beskriv hur ATT&CK kan stödja kommunikationen mellan red team, blue team och ledning.**

> **Svarsinstruktion:** Skriv 200–300 ord. Ta upp gemensamt språk, spårbarhet och prioritering.

#### Mitt svar

<!-- Skriv ditt svar här. -->



---

## Del 2 – TTP: Tactic, Technique och Procedure

### Uppgift 5

**Förklara skillnaden mellan tactic, technique och procedure.**

> **Svarsinstruktion:** Använd ett eget defensivt exempel. Håll dig på konceptuell nivå.

#### Mitt svar

| Begrepp | Förklaring med egna ord | Del av mitt defensiva exempel |
| --- | --- | --- |
| Tactic |  |  |
| Technique |  |  |
| Procedure |  |  |

### Uppgift 6

**Skapa en TTP-förklaring för tre valfria ATT&CK-tekniker.**

> **Svarsinstruktion:** För varje teknik: skriv tactic, technique och en kort procedure-beskrivning utan operativa instruktioner.

#### Mitt svar

| # | Tactic | Technique och ID | Kort procedure-beskrivning |
| ---: | --- | --- | --- |
| 1 |  |  |  |
| 2 |  |  |  |
| 3 |  |  |  |

### Uppgift 7

**Välj en tactic och identifiera tre tekniker som kan höra hemma inom den.**

> **Svarsinstruktion:** Motivera varför teknikerna passar in i tacticen.

#### Vald tactic

**Tactic:**

#### Mitt svar

| # | Technique och ID | Varför passar tekniken i tacticen? |
| ---: | --- | --- |
| 1 |  |  |
| 2 |  |  |
| 3 |  |  |

### Uppgift 8

**Beskriv varför det kan vara svårt att mappa en observation till rätt teknik.**

> **Svarsinstruktion:** Ta upp osäkerhet, kontext, datakvalitet och behov av källor.

#### Mitt svar

<!-- Skriv ditt svar här. -->



---

## Del 3 – Bygg en defensiv attackkedja

### Uppgift 9

**Bygg en enkel attackkedja med 3–5 steg.**

> **Svarsinstruktion:** Använd tactics som etiketter. Syftet är analys och försvar, inte teknisk genomförandeinstruktion.

#### Mitt svar

| Steg | Tactic | Technique och ID | Övergripande händelse |
| ---: | --- | --- | --- |
| 1 |  |  |  |
| 2 |  |  |  |
| 3 |  |  |  |
| 4 |  |  |  |
| 5 |  |  |  |

### Uppgift 10

**Beskriv varje steg i kedjan med ”varför”, ”hur” och ”vad såg vi?”.**

> **Svarsinstruktion:** Koppla till TTP-modellen: tactic, technique och procedure.

#### Mitt svar

| Steg | Varför? – Tactic | Hur? – Technique | Vad såg vi? – Procedure/observation |
| ---: | --- | --- | --- |
| 1 |  |  |  |
| 2 |  |  |  |
| 3 |  |  |  |
| 4 |  |  |  |
| 5 |  |  |  |

### Uppgift 11

**Identifiera vilka steg i attackkedjan som är mest osäkra.**

> **Svarsinstruktion:** Beskriv vad du behöver veta mer om för att göra analysen bättre.

#### Mitt svar

| Osäkert steg | Vad är osäkert? | Vad behöver jag veta eller kontrollera? |
| --- | --- | --- |
|  |  |  |
|  |  |  |
|  |  |  |

### Uppgift 12

**Rita eller beskriv attackkedjan som en enkel kedja från första kontakt till påverkan.**

> **Svarsinstruktion:** Använd pilar och korta rubriker. Digitalt kan du använda tabell eller punktlista.

#### Min attackkedja

```text
[Steg 1]
    ↓
[Steg 2]
    ↓
[Steg 3]
    ↓
[Steg 4]
    ↓
[Steg 5]
```

---

## Del 4 – Försvarsfrågor och Blue/Purple-perspektiv

### Uppgift 13

**Formulera minst en försvarsfråga per steg i attackkedjan.**

> **Svarsinstruktion:** Exempelvis: Hur skulle detta kunna upptäckas? Vilken signal, rutin eller kontroll kan vara relevant?

#### Mitt svar

| Steg | Technique | Försvarsfråga |
| ---: | --- | --- |
| 1 |  |  |
| 2 |  |  |
| 3 |  |  |
| 4 |  |  |
| 5 |  |  |

### Uppgift 14

**Välj två tekniker och resonera kring möjliga detektionssignaler.**

> **Svarsinstruktion:** Håll svaret på konceptuell nivå. Beskriv typer av signaler, inte tekniska exploit-steg.

#### Mitt svar

| Technique och ID | Möjliga typer av detektionssignaler | Begränsningar eller osäkerheter |
| --- | --- | --- |
|  |  |  |
|  |  |  |

### Uppgift 15

**Välj två tekniker och resonera kring möjliga riskreducerande åtgärder.**

> **Svarsinstruktion:** Beskriv organisatoriska, tekniska eller processmässiga åtgärder.

#### Mitt svar

| Technique och ID | Organisatoriska åtgärder | Tekniska åtgärder | Processmässiga åtgärder |
| --- | --- | --- | --- |
|  |  |  |  |
|  |  |  |  |

### Uppgift 16

**Beskriv hur ett säkerhetsteam kan använda en attackkedja för att förbättra sitt försvar.**

> **Svarsinstruktion:** Skriv 200–300 ord. Ta upp lärande, prioritering och uppföljning.

#### Mitt svar

<!-- Skriv ditt svar här. -->



---

## Del 5 – Källor, spårbarhet och kvalitet

### Uppgift 17

**Dokumentera vilka källor du använder i din ATT&CK-analys.**

> **Svarsinstruktion:** Skriv minst tre källor eller länkar. Beskriv kort vad varje källa bidrar med.

#### Mitt svar

| # | Källa och länk | Vad bidrar källan med? | Hämtad/kontrollerad datum |
| ---: | --- | --- | --- |
| 1 |  |  |  |
| 2 |  |  |  |
| 3 |  |  |  |

### Uppgift 18

**Beskriv hur du säkerställer att din TTP-mappning är rimlig.**

> **Svarsinstruktion:** Ta upp källa, motivering, osäkerhet och gruppgranskning.

#### Mitt svar

<!-- Skriv ditt svar här. -->



### Uppgift 19

**Skapa en mini-Definition of Done för en färdig hotanalys.**

> **Svarsinstruktion:** Lista minst fem kriterier. Kriterierna ska gå att använda av hela gruppen.

#### Mitt svar

- [ ]
- [ ]
- [ ]
- [ ]
- [ ]

### Uppgift 20

**Beskriv vad som gör en hotanalys användbar för någon annan än den som skrev den.**

> **Svarsinstruktion:** Skriv 150–250 ord. Fokusera på tydlighet, spårbarhet och mottagare.

#### Mitt svar

<!-- Skriv ditt svar här. -->



---

## Del 6 – Koppling till backlog, sprint och Workshop 3

### Uppgift 21

**Uppdatera er backlog baserat på det ni upptäckte i Workshop 2.**

> **Svarsinstruktion:** Skriv minst fem nya eller ändrade backlog items. Ge en kort motivering.

#### Mitt svar

| # | Nytt eller ändrat backlog item | Kort beskrivning | Prioritet | Motivering |
| ---: | --- | --- | --- | --- |
| 1 |  |  | Must/Should/Could |  |
| 2 |  |  | Must/Should/Could |  |
| 3 |  |  | Must/Should/Could |  |
| 4 |  |  | Must/Should/Could |  |
| 5 |  |  | Must/Should/Could |  |

### Uppgift 22

**Beskriv hur er attackkedja förhåller sig till ert Sprint Goal.**

> **Svarsinstruktion:** Är sprintmålet fortfarande relevant? Behöver något justeras?

#### Mitt svar

**Nuvarande Sprint Goal:**

**Min bedömning:**

**Eventuell justering:**

### Uppgift 23

**Formulera minst två uppföljningsfrågor inför Workshop 3.**

> **Svarsinstruktion:** Frågorna ska kunna användas vid review eller retrospektiv.

#### Mitt svar

1.
2.

### Uppgift 24

**Förbered en kort statusrapport till Workshop 3.**

> **Svarsinstruktion:** Skriv 5–7 punkter: vad ni gjorde, vad som blev klart, vad som är oklart och vad ni vill ändra.

#### Min statusrapport

- **Detta gjorde vi:**
- **Detta blev klart:**
- **Detta blev också klart:**
- **Detta är fortfarande oklart:**
- **Detta behöver följas upp:**
- **Detta vill vi ändra eller förbättra:**

---

## Frivillig fördjupningsutmaning

**Skapa en komplett mini-hotanalys baserad på din Workshop 2-kedja.**

> Inkludera mål med analysen, attackkedja, TTP-tabell, försvarsfrågor, källor, osäkerheter, uppdaterad backlog och förslag till nästa sprint. Max tre sidor.

### Mål med analysen

<!-- Skriv här. -->



### Attackkedja

<!-- Skriv eller rita kedjan här. -->



### TTP-tabell

| Steg | Tactic | Technique | Procedure/observation |
| ---: | --- | --- | --- |
| 1 |  |  |  |
| 2 |  |  |  |
| 3 |  |  |  |
| 4 |  |  |  |
| 5 |  |  |  |

### Försvarsfrågor

<!-- Skriv här. -->



### Källor

<!-- Skriv här. -->



### Osäkerheter

<!-- Skriv här. -->



### Uppdaterad backlog

<!-- Skriv här. -->



### Förslag till nästa sprint

<!-- Skriv här. -->



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
