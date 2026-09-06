# Individuell examineringsuppgift – MITRE ATT&CK och hotanalys

## Syfte
Den här uppgiften knyter an till innehållet från Workshop 2 och 3, med tyngdpunkt på MITRE ATT&CK-ramverket, TTP-modellen (tactic, technique, procedure), defensiv hotanalys och uppbyggnad av attackkedjor. Vidare berörs försvarsfrågor kopplade till varje steg, hur källor och spårbarhet hanteras, samt hur arbetet knyter an till det löpande projektet.

Som utgångspunkt använder gruppen ett påhittat scenario där ett Microsoft 365-konto antas ha blivit kapat. Det rör sig alltså inte om en faktisk säkerhetsincident, och inget verkligt loggmaterial har granskats. All information om aktivitet och tänkbara signaler i texten ska därför läsas som illustrativa exempel på vad ett säkerhetsteam bör vara uppmärksamt på – inte som verifierade observationer.

Genom hela arbetet ligger tyngdpunkten på att analysera, dokumentera och resonera kring försvar. Konkreta tillvägagångssätt för att faktiskt genomföra ett angrepp tas inte upp någonstans i texten.

---
## Del 1 – Förstå MITRE ATT&CK som analysramverk
### Uppgift 1
MITRE ATT&CK kan man se som ett stort bibliotek över hur angripare faktiskt brukar jobba i verkliga fall. Ett säkerhetsteam kan använda det för att beskriva vad som hänt på ett mycket klarare sätt, i stället för att bara säga "något gick fel". Man kan i stället visa exakt vad angriparen försökte uppnå och vilken väg som ledde dit.

Något av det bästa med ATT&CK är att hela teamet får ett gemensamt språk. Varje teknik har både ett namn och en kod, vilket gör det mycket lättare att förstå varandra utan krångel. I stället för att förklara att någon kommit åt ett system genom en fjärranslutning som redan fanns på plats, kan man bara säga T1021 – Remote Services, en teknik som handlar om att en angripare använder befintliga sätt att ansluta på distans, till exempel RDP eller liknande tjänster, för att ta sig vidare i miljön.

ATT&CK är också till stor hjälp när man jobbar med försvar. När teamet vet vilka tekniker som är relevanta blir det enklare att se vilka loggar som borde finnas, vad man ska hålla utkik efter om något är fel, och var det finns svaga punkter i övervakningen. Det gör det i sin tur lättare att avgöra vad som borde åtgärdas först.

Men ATT&CK löser inte problemet på egen hand. Man behöver fortfarande kunna sin egen miljö och själv bedöma om en teknik faktiskt stämmer med det man sett hända. För mig är ATT&CK mest ett verktyg för att strukturera tankarna, dokumentera och kommunicera – inte något facit man bara kan slå upp svaret i.

### Uppgift 2
Poängen med ATT&CK är inte att den ska funka som en manual för hur man hackar sig in någonstans. Ramverket bygger på sånt som redan hänt i riktiga attacker, men här använder vi det bara för att förstå hur en attack kan gå till och hur man skyddar sig mot den. Det handlar om att fatta vad angriparen är ute efter och ungefär vilka knep som brukar användas – inte att lära sig göra det själv.

Det som är bra med ett sånt här ramverk är att det hjälper till att hålla ordning på information. Man kan koppla ihop det man ser med rätt tactic och technique, jämföra olika fall med varandra och upptäcka vilka delar av en attackkedja som man vet minst om. En "instruktion" för att attackera nåt skulle i stället visa exakt hur man gör, typ vilka kommandon man kör eller hur man tar sig förbi ett skydd. Sånt behövs inte alls för att svara på frågorna här.

Man ska också vara försiktig med att bara bocka av tekniker som en checklista. Att man har ett skydd mot en viss teknik betyder inte att man är skyddad mot alla varianter av den, för angripare byter ju metod hela tiden. Ibland kan samma sak man ser i loggarna dessutom passa in på flera olika tekniker samtidigt, så det är inte alltid glasklart.

I det här arbetet handlar det alltså om att använda ATT&CK för att beskriva scenariot, testa om våra antaganden håller och komma på bra frågor kring upptäckt och skydd. Det viktiga är vad ett säkerhetsteam behöver hålla koll på och följa upp – inte hur själva attacken går till rent tekniskt.

### Uppgift 3
| # | Tactic | Övergripande betydelse |
|---|--------|--------------------------|
| 1 | Execution | Steget där angriparen får skadlig kod eller kommandon att köras på ett system. |
| 2 | Persistence | Steget där angriparen ser till att fortfarande ha tillgång till systemet, även om det startas om eller lösenord byts. |
| 3 | Privilege Escalation | Steget där angriparen försöker få högre rättigheter, till exempel gå från ett vanligt konto till ett med adminbehörighet. |
| 4 | Lateral Movement | Steget där angriparen tar sig vidare från ett system till andra system inom samma nätverk. |
| 5 | Exfiltration | Steget där angriparen försöker föra ut information från organisationen till sig själv. |

### Uppgift 4
Ett stort problem i säkerhetsarbete är att olika grupper pratar olika språk. En tekniker kanske beskriver ett problem i termer av loggar och kommandon, medan en chef vill veta vad det kostar och hur farligt det är. ATT&CK löser delvis det här genom att ge alla samma ord att utgå från.

Tänk dig att red team ska testa hur bra företaget är på att upptäcka intrång. I stället för att bara säga "vi ska försöka ta oss in" kan de peka på specifika tekniker de tänker använda. Blue team vet då exakt vad de letar efter, och kan i efterhand visa om de upptäckte det eller inte – och i så fall varför inte.

Fördelen syns tydligast när man ska förklara resultatet efteråt. Om en logg visar nåt konstigt går det att koppla direkt till en känd teknik. Den tekniken kan i sin tur kopplas till en åtgärd som borde finnas på plats, eller till en ny uppgift som läggs in i backloggen. Hela kedjan blir spårbar från observation till åtgärd.

Ledningen slipper också sitta med en massa tekniska detaljer de ändå inte förstår. I stället kan de få veta ungefär: "vi är bra på att stoppa nätfiske, men dåliga på att se vad som händer efter att någon loggat in." Det räcker för att förstå var pengarna och resurserna borde läggas.

Sist men inte minst hjälper ATT&CK till att undvika att man försöker göra allt på en gång. Ingen organisation hinner skydda sig mot alla tekniker i hela matrisen samtidigt. Det smartare sättet är att välja ut det som är mest relevant utifrån den egna hotbilden, och sen kunna förklara varför just de sakerna prioriterades.

---
## Del 2 – TTP: Tactic, Technique och Procedure
### Uppgift 5 
| Begrepp | Förklaring med egna ord | Del av mitt defensiva exempel |
|---------|--------------------------|-------------------------------|
| Tactic | Vad angriparen egentligen vill uppnå – alltså motivet bakom hela handlingen. | Målet är att få ett första insteg i Microsoft 365-miljön. |
| Technique | Sättet eller metoden som används för att nå det målet. | Ett mejl skickas till användaren med en länk till en falsk inloggningssida. |
| Procedure | Hur tekniken faktiskt ser ut just i det här scenariot. | Mejlet är byggt för att se ut som att det kommer från en leverantör och handlar om en uppdaterad offert. |

### Uppgift 6
| # | Tactic | Technique och ID | Kort procedure-beskrivning |
|---|--------|-------------------|------------------------------|
| 1 | Initial Access | T1078 – Valid Accounts | Ett kapat men giltigt konto används för att logga in i molnmiljön som om det vore den riktiga användaren. |
| 2 | Persistence | T1136.003 – Create Account: Cloud Account | Ett nytt konto skapas i molnmiljön för att säkerställa fortsatt åtkomst även om det ursprungliga kontot spärras. |
| 3 | Exfiltration | T1567.002 – Exfiltration to Cloud Storage | Information kopieras eller flyttas till en extern molntjänst utanför organisationens kontroll. |

### Uppgift 7 
| # | Technique och ID | Varför passar tekniken i tacticen? |
|---|---------------------|---------------------------------------|
| 1 | T1566.002 – Spearphishing Link | En länk i ett mejl lurar användaren att lämna ifrån sig inloggningsuppgifter, vilket ger angriparen ett första insteg. |
| 2 | T1195 – Supply Chain Compromise | Genom att kompromettera en leverantör eller en tredjepartstjänst kan angriparen komma in i organisationens miljö indirekt. |
| 3 | T1133 – External Remote Services | Fjärråtkomsttjänster som är öppna mot internet, till exempel VPN, kan utnyttjas för att ta sig in i nätverket. |

### Uppgift 8
En logg eller ett larm berättar sällan hela historien på egen hand. Säg att någon loggar in vid en konstig tidpunkt – det säger bara att nåt sticker ut, inte varför. Det kan lika gärna vara en anställd som jobbar sent eller är utomlands, som nån som faktiskt inte borde vara där.

Det är därför man måste titta på helheten och inte bara på själva händelsen. Hur brukar personen jobba annars? Vilka system pratar vi om? Vad hände strax innan och strax efter? Utan det sammanhanget är det lätt att gissa fel. Och om loggarna dessutom är ofullständiga, eller tiderna inte stämmer överens mellan olika system, blir det ännu svårare att lita på slutsatsen.

Ett sätt att minska risken för att välja fel teknik är att faktiskt läsa igenom hela beskrivningen på MITRE ATT&CK i stället för att bara kika på rubriken, och gärna jämföra med fler ställen. Det är också bra att skriva ner varför man landade i just den tekniken – och om det fanns andra alternativ som också kunde passa. Att låta någon annan i gruppen läsa igenom resonemanget är ofta ett bra sätt att fånga upp om man dragit en slutsats för snabbt.

---
## Del 3 – Bygg en defensiv attackkedja
### Uppgift 9
| Steg | Tactic | Technique och ID | Övergripande händelse |
|------|--------|-------------------|---------------------------|
| 1 | Initial Access | T1078 – Valid Accounts | Ett läckt lösenord används för att logga in på ett giltigt konto i Microsoft 365. |
| 2 | Persistence | T1136.003 – Create Account: Cloud Account | Ett nytt, extra konto skapas i molnmiljön för att säkra fortsatt åtkomst. |
| 3 | Discovery | T1526 – Cloud Service Discovery | Angriparen undersöker vilka molntjänster och resurser som är kopplade till organisationen. |
| 4 | Collection | T1530 – Data from Cloud Storage | Filer och dokument i molnlagringen genomsöks efter känslig information. |
| 5 | Exfiltration | T1567.002 – Exfiltration to Cloud Storage | Information förs över till en extern molntjänst utanför organisationens kontroll. |

### Uppgift 10
| Steg | Varför? – Tactic | Hur? – Technique | Tänkt procedure eller möjlig observation |
|------|---------------------|----------------------|----------------------------------------------|
| 1 | Skaffa en första giltig åtkomst till miljön | Använda ett läckt lösenord till ett riktigt konto | En inloggning sker med korrekta uppgifter, men från en plats eller enhet som avviker från det vanliga. |
| 2 | Säkra fortsatt åtkomst även om det ursprungliga kontot upptäcks | Skapa ett nytt konto i molnmiljön | Ett konto som ingen i organisationen känner igen dyker upp i användarlistan. |
| 3 | Förstå vilka resurser och tjänster som finns att tillgå | Söka igenom tillgängliga molntjänster | Ovanligt många förfrågningar görs mot administrationsgränssnitt eller tjänstelistor. |
| 4 | Hitta värdefull information att gå vidare med | Söka i molnlagringen | Ett stort antal filer öppnas eller laddas ner under kort tid, ofta utanför personens vanliga arbetsområde. |
| 5 | Föra ut informationen från organisationen | Flytta data till en extern molntjänst | Stora datamängder skickas till en molntjänst som organisationen normalt inte använder. |

### Uppgift 11
| Osäkert steg | Vad är osäkert? | Vad behöver jag veta eller kontrollera? |
|--------------|--------------------|----------------------------------------------|
| Steg 1 | Vi antar att lösenordet läckt utan att veta hur, och att inloggningen gick igenom utan att stoppas av annat skydd. | Om MFA var aktiverat på kontot, samt varifrån och när inloggningen faktiskt skedde. |
| Steg 2 | Det är osäkert om ett nytt konto verkligen hade kunnat skapas utan att det upptäcktes direkt. | Vilka behörigheter som krävs för att skapa konton, och om sådana händelser larmar automatiskt. |
| Steg 4 | Stor filaktivitet kan bero på helt vanligt arbete, inte bara på en pågående attack. | Jämförelse med hur mycket data personen normalt öppnar eller laddar ner under en arbetsdag. |
| Steg 5 | En stor dataöverföring till en molntjänst behöver inte vara skadlig i sig. | Vilken molntjänst det rör sig om, om det är en tjänst som är godkänd av organisationen, och hur stor mängden data faktiskt är. |

### Uppgift 12
```text
Läckt lösenord används – T1078  
↓  
Nytt konto skapas i molnmiljön – T1136.003  
↓  
Kartläggning av molntjänster – T1526  
↓  
Sökning i molnlagring – T1530  
↓  
Data förs ut till extern molntjänst – T1567.002
```

---
## Del 4 – Försvarsfrågor och Blue/Purple-perspektiv
### Uppgift 13
| Steg | Technique | Försvarsfråga |
|------|-----------|-----------------|
| 1 | T1078 | Hur upptäcker vi en inloggning med rätt lösenord som ändå sker från en ovanlig plats eller enhet? |
| 2 | T1136.003 | Hur märker vi att ett nytt konto skapats i molnmiljön utan att det gått genom vår vanliga process? |
| 3 | T1526 | Vilka signaler visar att någon undersöker vilka molntjänster och resurser som finns, mer än vad som är normalt? |
| 4 | T1530 | Hur kan vi se att ovanligt mycket data öppnas eller laddas ner från vår molnlagring? |
| 5 | T1567.002 | Hur upptäcker vi att stora mängder data skickas till en molntjänst som organisationen inte normalt använder? |

### Uppgift 14
| Technique och ID | Möjliga typer av detektionssignaler | Begränsningar eller osäkerheter |
|--------------------|----------------------------------------|-------------------------------------|
| T1078 – Valid Accounts | Inloggning från en ny plats eller enhet, ovanlig tidpunkt, avvikande beteende jämfört med hur kontot brukar användas. | En legitim användare kan också resa eller byta enhet, så en enskild signal räcker sällan för att dra en säker slutsats. |
| T1567.002 – Exfiltration to Cloud Storage | Stora datavolymer som skickas till en extern molntjänst, ovanligt hög nätverkstrafik, eller överföringar till tjänster organisationen normalt inte använder. | Stora dataöverföringar kan även bero på legitima behov, till exempel backup eller delning med samarbetspartners. |

### Uppgift 15
| Technique och ID | Organisatoriska åtgärder | Tekniska åtgärder | Processmässiga åtgärder |
|--------------------|-----------------------------|-----------------------|------------------------------|
| T1136.003 – Create Account: Cloud Account | Bestäm tydligt vem som har rätt att skapa nya konton i molnmiljön och varför. | Kräv godkännande i flera steg innan ett nytt konto med högre behörighet kan skapas. | Ha en rutin för att regelbundet stämma av listan över aktiva konton mot vilka som faktiskt borde finnas. |
| T1526 – Cloud Service Discovery | Informera IT-avdelningen om vilka molntjänster som normalt används, så avvikelser blir lättare att märka. | Begränsa vilka konton som kan lista eller söka igenom alla molntjänster och resurser. | Ha en rutin för att undersöka varför ett konto plötsligt börjar utforska tjänster det aldrig använt tidigare. |

### Uppgift 16
Om man inte har en attackkedja blir det lätt att bara jaga enskilda larm utan att förstå hur de hänger ihop. Med en attackkedja ser man i stället hela förloppet – var attacken började, hur den fortsatte, och var man faktiskt hade en chans att stoppa den.

Ett bra sätt att använda kedjan är att jämföra den med vad som verkligen syntes i loggarna efter en övning eller en riktig händelse. Man kan fråga sig: syntes det här steget i våra loggar? Om svaret är nej kan det bero på att man inte loggar rätt saker, eller att loggarna finns men ingen regel slår larm på dem. Kom larmet men ingen gjorde något åt det, då är det i stället rutinerna som behöver bli bättre, inte tekniken.

Kedjan hjälper också till att bestämma vad som ska fixas först. Man hinner inte skydda sig mot allt på en gång, så det gäller att välja ut de svagaste eller viktigaste stegen. I vårt fall skulle det till exempel kunna vara att bli bättre på att upptäcka läckta lösenord tidigt, eftersom resten av kedjan bygger vidare på just det.

Till sist är en attackkedja inget man gör en gång och sen är klar med. Hoten ändras hela tiden, så man behöver gå tillbaka, lägga in förbättringar i backloggen och senare kolla om skyddet faktiskt blivit bättre.

---
## Del 5 – Källor, spårbarhet och kvalitet
### Uppgift 17
| # | Källa och länk | Vad bidrar källan med? | Hämtad/kontrollerad datum |
|---|-------------------|---------------------------|-------------------------------|
| 1 | MITRE ATT&CK Enterprise Matrix | Ger en översikt över ramverkets tactics och vilka tekniker som hör till varje tactic. | 2026-09-05 |
| 2 | MITRE – Valid Accounts (T1078) | Beskriver hur giltiga konton kan missbrukas och vilka tactics tekniken hör till. | 2026-09-05 |
| 3 | MITRE – Create Account: Cloud Account (T1136.003) | Förklarar hur nya konton kan skapas i molnmiljöer för att säkra fortsatt åtkomst. | 2026-09-05 |
| 4 | MITRE – Exfiltration to Cloud Storage (T1567.002) | Beskriver hur data kan föras ut via externa molntjänster och vilka signaler som kan vara relevanta. | 2026-09-05 |

### Uppgift 18 
Innan jag bestämmer mig för en teknik läser jag alltid igenom hela beskrivningen på MITRE ATT&CK, inte bara rubriken eller namnet. Jag kollar att både beteendet som beskrivs och den tactic tekniken hör till faktiskt stämmer överens med vårt scenario. Sen skriver jag ner en kort motivering till varför just den här tekniken passar in på det vi ser i exemplet.

Om jag är osäker på nåt, eller om information saknas, försöker jag skriva ut det tydligt – vad som är ett antagande och vad som faktiskt går att belägga. Ibland finns det flera tekniker som skulle kunna passa, och då jämför jag dem mot varandra i stället för att bara välja den första som verkar rimlig. Jag sparar alltid källan och länken jag utgått ifrån, så att någon annan kan kolla samma sak själv.

Sist låter jag någon annan i gruppen läsa igenom mappningen. Om personen inte förstår kopplingen, eller kommer på en teknik som passar bättre, går vi igenom det tillsammans och justerar om det behövs.

### Uppgift 19
- Det går tydligt att förstå vilket scenario analysen bygger på och varför den gjorts.
- Varje steg i kedjan har fått en tactic, technique och procedure som känns rimlig och motiverad.
- Alla teknik-ID och namn stämmer med det som faktiskt står i MITRE ATT&CK.
- Det finns minst en försvarsfråga kopplad till varje steg i kedjan.
- Osäkerheter och antaganden är utskrivna, inte bara underförstådda.
- Källorna till analysen är listade, med fungerande länkar.
- Minst en till person utöver skribenten har läst igenom och kommenterat innehållet.
- Kommentarer från granskningen har antingen åtgärdats eller medvetet valts bort, med motivering.

### Uppgift 20
En hotanalys skriven bara för sig själv är i praktiken ganska värdelös för alla andra. Det som gör skillnad är om läsaren, någon som inte satt bredvid när analysen gjordes, faktiskt kan förstå vad som undersökts och varför, utan att behöva fråga skribenten.

Grunden för det är ett scenario som är tydligt formulerat från början, så att man vet vad hela analysen kretsar kring. Sen behöver varje viktig slutsats gå att spåra: varifrån kom informationen, vilka källor pekar på just den här tekniken, och vad är egentligen bekräftat jämfört med vad som mest är en kvalificerad gissning? Att gömma osäkerheter för att texten ska kännas mer säker gör bara att nästa person litar på nåt som inte håller.

Det spelar också roll vem som förväntas läsa texten. En teknisk kollega behöver ofta mer information om exakt vilka loggar och signaler som är relevanta, medan en chef mest behöver förstå vad risken faktiskt innebär och vad som bör göras åt saken, utan att drunkna i detaljer. En bra analys är byggd så att båda kan hitta det de behöver, ganska snabbt.

Och till sist: en hotanalys som bara beskriver vad som hänt är ofullständig. Den blir mer värd om den även säger något om vad som borde hända sen, nya frågor att undersöka, brister att åtgärda, eller konkreta förslag som går rakt in i backloggen.

---
## Del 6 – Koppling till backlog, sprint och Workshop 3
### Uppgift 21 
I samband med Workshop 3 gick gruppen igenom vad som framkommit under Workshop 2, och nedanstående punkter finns just nu som öppna Issues i GitHub (uppdaterat 2026-09-05).

| Issue | Nytt eller ändrat backlog item | Kort beskrivning | Prioritet | Motivering |
|-------|----------------------------------|----------------------|-----------|---------------|
| #24 | Kartlägg vilka loggar som saknas | Gå igenom varje steg i kedjan och identifiera vilken loggkälla som borde finnas men inte gör det idag. | Must | Utan rätt loggar går det inte att avgöra om ett steg i kedjan faktiskt går att upptäcka. |
| #25 | Beskriv hur konton övervakas | Dokumentera vilka signaler som skulle visa att ett nytt konto skapats utan godkännande. | Must | Steget där ett extra konto skapas är svårt att bedöma utan tydligare underlag. |
| #11 | Tydliggör roller inför nästa sprint | Ge varje kvarvarande uppgift en namngiven ansvarig person. | Must | Det har varit svårt att veta vem som ska driva en viss uppgift framåt, trots tidigare instruktioner. |
| #14 | Fastställ rutin för ändringar i repot | Bestäm hur ändringar ska granskas innan de pushas till GitHub. | Must | Gruppen saknar en gemensam överenskommelse kring vem som gör vad i det tekniska arbetsflödet. |
| #27 | Utöka källhänvisningarna | Lägg till ytterligare dokumentation kring molnrelaterade hot och skydd. | Should | Fler källor stärker trovärdigheten och underlättar granskning av analysen. |

Sedan tidigare är visualiseringen av attackkedjan klar, och Issue #9 har stängts och räknas inte längre som en öppen punkt. Resterande förbättringar kvarstår att genomföra och ska stämmas av mot respektive klarkriterium.

### Uppgift 22
Målet för Sprint 1 handlade i stort om tre saker: få ett arbetssätt på plats som gruppen faktiskt kunde jobba efter, bli klara med Team Charter och backlog, och skaffa sig en grund i hur MITRE ATT&CK och hotanalys fungerar. Exakt hur målet var formulerat går att läsa i dokumenten för Sprint Goal och Definition of Done.

Ser man till innehållet har vi kommit ganska långt. Attackkedjan är byggd, flera tekniker är kopplade till den, och vi har både försvarsfrågor och kända osäkerheter dokumenterade. Det som stack ut mest under Workshop 3 var däremot att sättet vi jobbade på inte höll samma nivå som resultatet. Jag tänker särskilt på att det uppstod förvirring kring vem som skulle uppdatera och pusha ändringar till GitHub, trots att det faktiskt fanns skrivna instruktioner om detta sedan tidigare. Det säger nåt viktigt om skillnaden mellan att ha en rutin nedskriven och att den verkligen används.

Om jag skulle föreslå vad nästa sprint borde fokusera på, är det att göra hotanalysen mer skarp i praktiken: klargöra vad som gäller kring lösenord och skydd, ta reda på vilka loggar som faktiskt saknas, och se till att varje uppgift har en person som äger den. Det här är bara mitt förslag i nuläget, gruppen har inte fattat något gemensamt beslut om det ännu.

### Uppgift 23
- Hur säkra kan vi egentligen vara på att vi valt rätt tekniker i attackkedjan och vad skulle krävas för att stärka det underlaget ytterligare?
- Vilken av våra dokumenterade osäkerheter är mest brådskande att reda ut innan analysen används av någon annan i projektet?

Även efter Workshop 3 känns de här frågorna lika aktuella som innan. Retrospektivet visade att gruppen brottas med två saker samtidigt: dels osäkerhet kring vilket loggunderlag som faktiskt finns tillgängligt, dels otydlighet kring vem som gör vad. Det betyder att uppföljningen framöver bör handla om både kvaliteten i själva analysen och hur arbetet är fördelat mellan oss i gruppen.

### Uppgift 24
- Vi använde MITRE ATT&CK och TTP-modellen som grund för att bygga upp och strukturera vår hotanalys.
- Vi tog fram en enkel, defensiv attackkedja där varje steg märktes med en tydlig tactic.
- Vi tog fram försvarsfrågor kopplade till varje steg, samt resonerade kring detektionssignaler och åtgärder som kan minska risken.
- Vi skrev ner våra osäkerheter och märkte att vissa steg behöver mer underlag, bland annat bättre loggning.
- Utifrån analysen tog vi fram nya och uppdaterade punkter till backloggen.
- Inför Workshop 3 vill vi prioritera de största kunskapsluckorna och gå igenom vår TTP-mappning en extra gång.
- Vi vill också se om de föreslagna förbättringarna kan kopplas tydligare till Sprint Goal och Definition of Done.

---

## Frivillig fördjupningsutmaning EJ GENOMFÖRD

---

## Rekommenderade referenser
- [MITRE ATT&CK](https://attack.mitre.org/)
- [MITRE ATT&CK Enterprise Matrix](https://attack.mitre.org/matrices/enterprise/)
- [CISA – Best Practices for MITRE ATT&CK Mapping](https://www.cisa.gov/news-events/news/best-practices-mitre-attckr-mapping)
- [MITRE ATT&CK Data & Tools](https://attack.mitre.org/resources/attack-data-and-tools/)
