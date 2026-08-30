# Självstudier vecka 1

**Kurs:** ITSX25 Kurs 6  
**Namn:** André Edvardsson  
**Datum:** 2026-08-30

---

## Del 1 – Reflektion kring säkerhetsteam

### Övning 1

**Vad skiljer ett cybersäkerhetsteam från en vanlig utvecklingsgrupp?**

> **Svarsinstruktion:** Skriv 150–300 ord. Ge gärna exempel på ansvar, arbetsflöden och typer av leverabler.

#### Mitt svar

Ett cybersäkerhetsteam och en vanlig utvecklingsgrupp kan arbeta på liknande sätt med backlog, sprintar och gemensamma mål, men de har olika fokus. En utvecklingsgrupp bygger oftast nya funktioner eller förbättrar en produkt. Ett säkerhetsteam försöker i stället förstå vad som kan gå fel, hur ett angrepp kan se ut och hur organisationen kan skydda sig.

Säkerhetsteamet behöver både arbeta förebyggande och kunna reagera snabbt. Planerat arbete kan till exempel vara att kontrollera sårbarheter, förbättra loggning eller ta fram säkerhetsrutiner. Om det kommer ett allvarligt larm eller upptäcks en ny sårbarhet kan teamet behöva lägga den vanliga planeringen åt sidan. Det gör arbetet mer händelsestyrt än i många utvecklingsprojekt.

Leverablerna skiljer sig också. En utvecklingsgrupp kan leverera kod och funktioner, medan ett säkerhetsteam exempelvis tar fram en hotanalys, incidentrapport, detektionsregel eller rekommendation om en säkerhetsåtgärd. Jag tycker också att dokumentation och spårbarhet blir extra viktigt inom säkerhet. Det ska gå att se vilka källor som använts, varför en risk har fått en viss prioritet och vem som har granskat slutsatsen. Samtidigt behöver säkerhetsteamet samarbeta med utvecklare och verksamheten, eftersom en säkerhetsåtgärd också måste fungera i praktiken.

### Övning 2

**Vilka tre utmaningar tror du att ett säkerhetsteam möter i vardagen?**

> **Svarsinstruktion:** Motivera dina svar. Beskriv också varför utmaningarna påverkar teamets sätt att planera arbete.

#### Mitt svar

1. **Utmaning: Nya hot och oväntade incidenter**
   **Motivering:** Säkerhetsläget kan ändras snabbt. Ett nytt intrång eller en allvarlig sårbarhet kan göra att teamet måste pausa annat arbete. Därför går det inte att planera varje sprint för hårt utan att lämna utrymme för akuta saker.

2. **Utmaning: För mycket information och för många larm**
   **Motivering:** Alla larm betyder inte att ett riktigt angrepp pågår. Teamet behöver sortera bort brus och prioritera det som har störst risk. Annars kan mycket tid gå åt till fel saker.

3. **Utmaning: Kommunikation med resten av organisationen**
   **Motivering:** Säkerhetsproblem behöver ofta lösas tillsammans med IT, utvecklare eller andra delar av företaget. Om en åtgärd är dåligt förklarad kan den uppfattas som ett hinder. Teamet behöver därför planera tid både för tekniskt arbete och för att förklara risker och lösningar.

### Övning 3

**Vilka kompetenser behöver finnas i ett säkerhetsteam?**

> **Svarsinstruktion:** Beskriv minst fem roller eller förmågor och förklara kort varför de behövs.

#### Mitt svar

| Roll eller förmåga | Varför behövs den? |
| --- | --- |
| SOC-analys och loggning | För att kunna upptäcka avvikande aktivitet och förstå vad som har hänt. |
| Incidenthantering | För att kunna begränsa skadan, samla information och återställa systemen när något händer. |
| Nätverk och system | För att förstå hur datorer, servrar, identiteter och trafik hänger ihop. |
| Threat Intelligence | För att bedöma vilka hot och angriparbeteenden som är relevanta för organisationen. |
| Sårbarhetshantering | För att hitta svagheter och prioritera vilka som behöver åtgärdas först. |
| Kommunikation och dokumentation | För att andra ska kunna förstå, granska och använda teamets resultat. |

---

## Del 2 – Teamarbete

### Övning 4

**Formulera tre regler som du tycker bör finnas i er Team Charter.**

> **Svarsinstruktion:** Motivera varje regel. Koppla gärna till samarbete, ansvar, dokumentation eller kvalitet.

#### Mitt svar

| Regel | Motivering |
| --- | --- |
| Säg till tidigt om man fastnar eller blir sen. | Gruppen får då en chans att hjälpa till eller fördela om arbetet innan det blir ett större problem. |
| Viktiga beslut och ändringar ska dokumenteras. | Det minskar missförstånd och gör att även den som missat ett möte kan se vad gruppen har bestämt. |
| Minst en annan person ska granska en uppgift innan den blir Done. | Det är lätt att missa fel i sitt eget arbete. En enkel granskning förbättrar både kvalitet och kunskapsdelning. |

### Övning 5

**Beskriv hur ni vill kommunicera inom gruppen.**

> **Svarsinstruktion:** Beskriv när ni använder Teams, e-post, möten och dokumentation.

#### Mitt svar

| Kommunikationssätt | När och hur använder vi det? |
| --- | --- |
| Teams/Slack | Vi använder främst gruppkanalen för snabba frågor, uppdateringar och information från läraren. |
| E-post | E-post passar bättre för mer formella meddelanden eller kontakt med någon utanför gruppen. |
| Möten | Vi använder möten när vi behöver planera, fördela arbete eller fatta ett beslut tillsammans. Mötet bör avslutas med att alla vet vad de ska göra. |
| Dokumentation | Färdigt material, beslut och backlog sparas i GitHub. Då kan alla hitta den senaste versionen och se historiken. |

### Övning 6

**Hur bör en grupp agera om någon medlem inte hinner med sina uppgifter?**

> **Svarsinstruktion:** Beskriv ett arbetssätt som är tydligt, respektfullt och möjligt att följa upp.

#### Mitt svar

Personen bör säga till så tidigt som möjligt och beskriva vad som är klart, vad som återstår och vad som hindrar arbetet. Gruppen ska inte börja med att leta efter vem som gjort fel, utan försöka lösa situationen. Uppgiften kan delas i mindre delar, få en ny realistisk deadline eller lämnas över till någon som har möjlighet att hjälpa till.

Ändringen behöver också synas i backloggen så att gruppen inte tror att uppgiften fortfarande följer den gamla planen. Vid nästa avstämning kontrollerar gruppen om lösningen fungerade. Om samma problem återkommer behöver man prata om orsaken och kanske ändra arbetsfördelningen. Jag tycker att det viktigaste är att personen vågar säga till i tid. En försening som gruppen känner till går ofta att hantera, medan en försening som upptäcks precis före inlämning blir mycket svårare.

---

## Del 3 – Product Backlog

### Övning 7

**Skapa fem backlog items kopplade till Threat Intelligence.**

> **Svarsinstruktion:** Varje backlog item ska ha titel och kort beskrivning.

#### Mitt svar

| # | Titel | Kort beskrivning |
| ---: | --- | --- |
| 1 | Hitta relevanta hotkällor | Samla källor som MITRE ATT&CK, CISA och rapporter från etablerade säkerhetsföretag. |
| 2 | Bedöma källornas trovärdighet | Kontrollera vem som publicerat informationen, hur aktuell den är och om den stöds av andra källor. |
| 3 | Identifiera relevanta hotaktörer | Undersök vilka typer av aktörer eller kampanjer som kan vara relevanta för vårt scenario. |
| 4 | Sammanställa aktuella hot | Samla de viktigaste hoten i ett gemensamt underlag som gruppen kan använda. |
| 5 | Koppla hotinformation till projektet | Förklara varför den insamlade informationen är relevant och vad gruppen bör analysera vidare. |

### Övning 8

**Skapa fem backlog items kopplade till MITRE ATT&CK.**

> **Svarsinstruktion:** Tänk på vad ni behöver förstå, undersöka, dokumentera eller presentera.

#### Mitt svar

| # | Titel | Kort beskrivning |
| ---: | --- | --- |
| 1 | Förstå ATT&CK-strukturen | Ta reda på skillnaden mellan tactics, techniques, sub-techniques och procedures. |
| 2 | Välja ett scenario | Bestäm ett realistiskt angrepp som gruppen kan analysera utan att göra kedjan för stor. |
| 3 | Mappa attackkedjan | Koppla varje steg i scenariot till rätt ATT&CK-teknik och ID. |
| 4 | Formulera försvarsfrågor | Beskriv vad ett Blue Team skulle vilja upptäcka eller stoppa i varje steg. |
| 5 | Visualisera kedjan | Visa teknikerna i ett enkelt diagram eller i ATT&CK Navigator. |

### Övning 9

**Skapa fem backlog items kopplade till rapportering.**

> **Svarsinstruktion:** Fokusera på vad en mottagare behöver förstå av ert arbete.

#### Mitt svar

| # | Titel | Kort beskrivning |
| ---: | --- | --- |
| 1 | Bestäm rapportens målgrupp | Klargör om texten riktar sig till tekniker, ledning eller båda. |
| 2 | Beskriv scenario och metod | Förklara vad som analyserats och hur gruppen gjorde sina val. |
| 3 | Sammanfatta viktigaste fynden | Lyft fram det mottagaren verkligen behöver förstå från analysen. |
| 4 | Dokumentera källor och osäkerheter | Visa vilket underlag som använts och vad gruppen fortfarande är osäker på. |
| 5 | Kvalitetsgranska rapporten | Kontrollera språk, teknik-ID, länkar och att slutsatserna stöds av innehållet. |

### Övning 10

**Välj tre backlog items och skriv titel, beskrivning och förväntat resultat.**

> **Svarsinstruktion:** Formulera dem så att någon annan i gruppen kan förstå vad som ska göras.

#### Mitt svar

| # | Titel | Beskrivning | Förväntat resultat |
| ---: | --- | --- | --- |
| 1 | Mappa attackkedjan | Välj 3–5 steg och koppla varje steg till rätt tactic, technique och ATT&CK-ID. | En tydlig kedja där en annan gruppmedlem kan följa hur angreppet utvecklas. |
| 2 | Formulera försvarsfrågor | Skriv en fråga för varje teknik om hur beteendet kan upptäckas eller begränsas. | En lista med konkreta frågor som kan användas i nästa analyssteg. |
| 3 | Kvalitetsgranska rapporten | Kontrollera att innehållet är begripligt, att länkar fungerar och att teknikernas namn och ID är rätt. | Ett granskat dokument som gruppen kan stå bakom och presentera. |

---

## Del 4 – Prioritering

### Övning 11

**Prioritera era backlog items enligt Must Have, Should Have och Could Have.**

> **Svarsinstruktion:** Motivera minst tre av era prioriteringar.

#### Mitt svar

| Backlog item | Prioritet | Motivering |
| --- | --- | --- |
| Välja scenario och skapa attackkedja | Must Have | Utan ett avgränsat scenario har gruppen inget gemensamt att analysera. |
| Mappa tekniker mot MITRE ATT&CK | Must Have | Detta är en central del av uppgiften och behövs för att kedjan ska använda ett gemensamt språk. |
| Dokumentera källor och osäkerheter | Must Have | Resultatet måste gå att kontrollera och gruppen ska vara tydlig med sådant vi inte vet. |
| Formulera försvarsfrågor | Should Have | Det gör analysen mer användbar, men kräver att attackkedjan redan är klar. |
| Skapa en avancerad visualisering | Could Have | En snygg matris förbättrar presentationen, men en enkel kedja räcker för att förstå innehållet. |

### Övning 12

**Vilka tre aktiviteter anser du ger högst värde för projektet?**

> **Svarsinstruktion:** Förklara varför dessa aktiviteter bör prioriteras tidigt.

#### Mitt svar

| Aktivitet | Varför ger den högt värde? |
| --- | --- |
| Välja och avgränsa scenariot | Gruppen får en gemensam riktning och minskar risken att analysen blir för bred. |
| Mappa attackkedjan mot ATT&CK | Det gör att vi kan beskriva angreppet på ett strukturerat sätt och kontrollera våra val mot en trovärdig källa. |
| Granska varandras arbete | Fel och otydligheter upptäcks innan de följer med till nästa del av projektet. |

### Övning 13

**Vilka aktiviteter skulle kunna vänta till senare?**

> **Svarsinstruktion:** Motivera varför dessa kan vänta utan att projektet tappar riktning.

#### Mitt svar

En mer avancerad visualisering kan vänta tills gruppen vet att teknikerna och sambanden är rätt. Det är onödigt att lägga mycket tid på en snygg bild om innehållet senare måste göras om. En djupare jämförelse mellan flera hotaktörer kan också vänta, eftersom vårt första mål är att förstå ett avgränsat scenario. Slutlig språkgranskning och presentationsdesign görs bäst när analysen har blivit stabil. De här sakerna förbättrar slutresultatet, men projektet tappar inte riktning om vi först fokuserar på scenario, källor och korrekt ATT&CK-mappning.

---

## Del 5 – Sprint Goal

### Övning 14

**Formulera ett första Sprint Goal för gruppen.**

> **Svarsinstruktion:** Skriv max två meningar. Målet ska beskriva varför sprinten är värdefull.

#### Mitt svar

Sprintens mål är att skapa ett gemensamt arbetssätt och ett dokumenterat underlag som gör gruppen redo att påbörja en MITRE ATT&CK-baserad hotanalys.

### Övning 15

**Beskriv hur ni ska veta att Sprint Goal är uppnått.**

> **Svarsinstruktion:** Skriv cirka 150 ord. Beskriv vilka tecken eller leverabler som visar att målet är uppnått.

#### Mitt svar

Vi vet att sprintmålet är uppnått när gruppen har mer än bara lösa anteckningar och muntliga överenskommelser. Det ska finnas en färdig Team Charter med roller, ansvar, kommunikationssätt och regler för hur vi hanterar problem. Vi ska också ha en prioriterad Product Backlog med minst tio tydliga aktiviteter samt en gemensam Definition of Done.

Materialet ska ligga i vårt GitHub-repo så att alla kan komma åt samma version. Minst en annan person ska ha granskat varje viktig leverabel och eventuella synpunkter ska vara hanterade. Gruppen ska kunna förklara vilka backlog items som är viktigast, vad vi arbetar med just nu och vad som återstår. Ett annat tecken är att vi kan börja Workshop 2 utan att först behöva diskutera roller eller var dokument ska sparas. Om alla känner till arbetssättet och vi kan använda backloggen för att följa framdriften anser jag att sprintmålet är uppnått.

### Övning 16

**Vilka risker kan göra att sprintmålet inte uppnås?**

> **Svarsinstruktion:** Beskriv minst tre risker och föreslå hur gruppen kan minska dem.

#### Mitt svar

| Risk | Hur kan gruppen minska risken? |
| --- | --- |
| Otydlig arbetsfördelning | Skriv ansvarig person på varje viktig uppgift och kontrollera fördelningen vid avstämningar. |
| Någon hinner inte klart | Meddela hinder tidigt, dela upp stora uppgifter och omfördela arbete när det behövs. |
| Gruppen fastnar i detaljer | Jämför arbetet med Sprint Goal och prioritera Must före Should och Could. |
| Filer eller ändringar hamnar fel | Använd den gemensamma strukturen i GitHub och gör `git pull` innan nya ändringar. |

---

## Del 6 – Definition of Done

### Övning 17

**Lista minst fem kriterier som måste vara uppfyllda innan en uppgift räknas som klar.**

> **Svarsinstruktion:** Kriterierna ska gå att använda av hela gruppen.

#### Mitt svar

- [ ] Uppgiftens krav och förväntade resultat är uppfyllda.
- [ ] Resultatet är dokumenterat på gruppens gemensamma plats.
- [ ] Källor, antaganden och viktiga val går att följa.
- [ ] Minst en annan gruppmedlem har granskat arbetet.
- [ ] Fel och synpunkter från granskningen är åtgärdade.
- [ ] Filnamn, länkar och formatering har kontrollerats.
- [ ] Uppgiftens status är uppdaterad till Done i backloggen.

### Övning 18

**Ge exempel på en uppgift som ser klar ut men egentligen inte är det.**

> **Svarsinstruktion:** Motivera med hjälp av dokumentation, granskning, kvalitet eller spårbarhet.

#### Mitt svar

Ett exempel är att attackkedjan är skriven i ett dokument men att ingen har kontrollerat teknikernas namn och ID mot MITRE ATT&CK. Den kan se färdig ut eftersom alla steg finns med, men ett felaktigt ID gör att analysen pekar på fel beteende. Uppgiften är inte heller klar om filen bara ligger på en persons dator eller om källorna saknas. Då kan resten av gruppen varken granska resultatet eller förstå hur personen kom fram till sina val. Först när kedjan är sparad i GitHub, källorna är länkade, innehållet är granskat och eventuella fel är rättade bör uppgiften markeras som Done.

---

## Del 7 – Förberedelse inför MITRE ATT&CK

### Övning 19

**Vilka frågor hoppas du få svar på under MITRE ATT&CK-workshopen?**

> **Svarsinstruktion:** Skriv minst fem frågor. Försök formulera frågor som hjälper er i projektarbetet.

#### Mitt svar

1. Hur vet vi att vi har valt rätt teknik och inte bara en teknik med ett passande namn?
2. Hur detaljerad behöver en attackkedja vara för att fortfarande vara lätt att förstå?
3. Vilka loggar kan visa att en viss ATT&CK-teknik används?
4. Hur kopplar man en verklig händelse till tactics, techniques och procedures?
5. Hur kan ett Blue Team använda ATT&CK för att hitta luckor i övervakningen?
6. Hur använder man ATT&CK Navigator för att presentera en analys?

### Övning 20

**Vad tror du att MITRE ATT&CK kan användas till i ett säkerhetsteam?**

> **Svarsinstruktion:** Skriv 200–300 ord. Fokusera på analys, språk, prioritering och försvarsperspektiv.

#### Mitt svar

Jag tror att MITRE ATT&CK framför allt kan hjälpa ett säkerhetsteam att skapa ordning i information om attacker. I stället för att bara skriva att någon har gjort ett intrång kan teamet beskriva vad angriparen försökte uppnå och vilka tekniker som användes. Det blir mer konkret och lättare att jämföra med andra händelser.

ATT&CK ger också ett gemensamt språk. En SOC-analytiker, incidenthanterare och den som skriver rapporten kan hänvisa till samma teknik och ID. Det minskar risken att olika personer menar olika saker. Samtidigt räcker det inte att bara välja en ruta i matrisen. Gruppen måste läsa beskrivningen och kunna motivera varför tekniken passar det beteende som har observerats.

Ramverket kan även hjälpa till med prioritering. Om vissa tekniker är relevanta för organisationens hotbild kan säkerhetsteamet undersöka om rätt loggar samlas in och om beteendet går att upptäcka. På så sätt kan man hitta luckor i försvaret och prioritera förbättringar där de ger störst nytta.

I vårt scenario med ett kapat Microsoft 365-konto kunde vi använda ATT&CK för att skilja mellan nätfiskelänken, användningen av ett riktigt molnkonto, sökningar i SharePoint och en regel för vidarebefordring av mejl. Det gjorde kedjan lättare att förklara. Ur ett Blue Team-perspektiv kan varje steg sedan bli en fråga om vilka signaler som finns och var attacken kan stoppas. Jag ser därför ATT&CK som ett analysstöd och ett gemensamt språk, inte som en färdig checklista som löser analysen åt teamet.

---

## Frivillig fördjupningsutmaning

**Designa säkerhetsteamets första sprint.**

> Inkludera Sprint Goal, backlog, prioritering, Definition of Done, risker och leverabler. Max två sidor.

### Mitt svar

#### Sprint Goal

Skapa ett gemensamt och granskat underlag som gör gruppen redo att genomföra en första MITRE ATT&CK-baserad hotanalys.

#### Backlog och prioritering

| Backlog item | Prioritet |
| --- | --- |
| Bestäm arbetssätt och roller | Must |
| Välj och avgränsa scenario | Must |
| Skapa en attackkedja med 3–5 steg | Must |
| Mappa tekniker mot ATT&CK | Must |
| Formulera försvarsfrågor | Should |
| Skapa en visuell ATT&CK-mappning | Could |

#### Definition of Done

Arbetet ska vara dokumenterat i GitHub, ha kontrollerade källor och ha granskats av minst en annan gruppmedlem. Eventuella synpunkter ska vara åtgärdade och uppgiften ska vara markerad som Done.

#### Risker

- Otydlig arbetsfördelning.
- För stora uppgifter eller för lite tid.
- Att gruppen väljer tekniker utan att läsa hela beskrivningen.
- Att hinder kommuniceras för sent.

#### Leverabler

- Team Charter och prioriterad backlog.
- Ett tydligt Sprint Goal och gemensam Definition of Done.
- En dokumenterad attackkedja med ATT&CK-ID:n.
- Försvarsfrågor och en lista över kvarvarande osäkerheter.
