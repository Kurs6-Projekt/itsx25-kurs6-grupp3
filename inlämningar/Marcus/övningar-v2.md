# Gjord inviduellt

# Del 1 – Förstå MITRE ATT&CK som analysramverk

## Uppgift 1
Beskriv med egna ord vad MITRE ATT&CK används till i ett säkerhetsteam.
Svarsinstruktion: Skriv 150-250 ord. Fokusera på analys, språk, struktur och försvarsperspektiv.

MITRE ATT&CK används i ett säkerhetsteam som ett analysramverk för att beskriva och förstå angripares beteenden. Ramverket bygger på observerade taktiker och tekniker och ger teamet en struktur för att analysera hur en angripare kan försöka nå sina mål. Tactics beskriver angriparens övergripande mål, medan tekniker beskriver typer av beteenden som kan användas för att nå målet.

Ett viktigt användningsområde är att koppla hotinformation och incidenter till ett gemensamt språk. I stället för att en analyst bara skriver att en aktivitet verkar misstänkt kan teamet beskriva vilket beteende som har observerats och varför det är relevant. Det gör analysen tydligare och lättare att följa upp. 
Ur ett försvarsperspektiv kan ATT&CK hjälpa teamet att jämföra relevanta hot med organisationens skydd. Teamet kan undersöka om det finns loggning, larm och rutiner för att upptäcka ett visst beteende. Om det saknas kan det bli en prioriterad förbättring. Ramverket ersätter inte en riskanalys eller kunskap om den egna miljön, men det hjälper teamet att strukturera analys, dokumentation och försvarsåtgärder.

## Uppgift 2

Förklara varför ATT&CK inte ska användas som en checklista för att “göra attacker”.
Svarsinstruktion: Skriv 150-250 ord. Beskriv skillnaden mellan analysramverk och angreppsinstruktion.

MITRE ATT&CK ska inte användas som en checklista för att “göra attacker”, eftersom ramverket främst beskriver och kategoriserar beteenden som har observerats hos angripare. Det är alltså ett kunskaps- och analysstöd, inte en steg-för-steg-guide för att genomföra intrång. ATT&CK hjälper ett säkerhetsteam att förstå vad en motståndare försöker uppnå och vilka typer av beteenden som kan behöva upptäckas eller förebyggas.

En angripare kan använda många olika vägar för att nå samma mål, och en organisation påverkas inte av alla tekniker i Enterprise Matrix. Därför skulle en bokstavlig checklista bli missvisande. Att markera en teknik som “hanterad” betyder inte automatiskt att organisationen har fullgott skydd. Skyddet behöver bedömas utifrån den egna miljön, relevanta hot, tillgångar och risker.

I ett defensivt arbete används ATT&CK i stället för att ställa frågor: Vilka beteenden är relevanta för oss? Vilka loggar kan ge spår av dem? Vilka kontroller saknas? Resultatet bör vara prioriterade och motiverade försvarsåtgärder, inte instruktioner för angrepp.

## Uppgift 3

Välj fem tactics från Enterprise Matrix och beskriv vad varje tactic betyder på en övergripande nivå.
Svarsinstruktion: Använd egna ord. Undvik tekniska genomförandedetaljer.

Reconnaissance

Reconnaissance betyder att angriparen samlar information för att planera framtida aktiviteter. För ett säkerhetsteam är detta relevant eftersom offentlig information om organisationen ibland kan öka risken för exempelvis riktad social manipulation.

Initial Access

Initial Access handlar om angriparens mål att få en första väg in i en organisations miljö. Ur ett försvarsperspektiv behöver teamet därför bedöma skydd kring användarkonton, externa tjänster och andra möjliga ingångar.

Persistence

Persistence betyder att angriparen försöker behålla sin åtkomst över tid. Säkerhetsteamet behöver kunna upptäcka oväntade förändringar och ha rutiner för att säkerställa att en incident verkligen är hanterad.

Credential Access

Credential Access handlar om att angriparen försöker komma åt kontouppgifter eller annan autentiseringsinformation. Detta visar varför stark autentisering, minsta möjliga behörighet och övervakning av konton är viktiga försvarsåtgärder.

Discovery

Discovery betyder att angriparen försöker förstå miljön efter att ha fått åtkomst, till exempel vilka system, användare och resurser som finns. Försvarsteamet kan använda kunskapen för att avgöra vilken loggning och vilka avvikande beteenden som bör följas upp.

## Uppgift 4

Beskriv hur ATT&CK kan stödja kommunikationen mellan red team, blue team och ledning.
Svarsinstruktion: Skriv 200-300 ord. Ta upp gemensamt språk, spårbarhet och prioritering.

MITRE ATT&CK kan stödja kommunikationen mellan red team, blue team och ledning genom att skapa ett gemensamt språk för angriparbeteenden och risker. Red team kan använda ramverket för att beskriva vilka typer av beteenden som ska analyseras i ett scenario. Blue team kan koppla samma beteenden till loggkällor, detektering och skyddsåtgärder. På så sätt blir dialogen mer konkret än om teamen enbart använder allmänna uttryck som “vi behöver bättre säkerhet”.

Ramverket förbättrar även spårbarheten. En observation, risk eller förbättringsåtgärd kan kopplas till relevanta tactics och tekniker. Då blir det lättare att följa varför en viss åtgärd föreslås, vilken risk den ska minska och hur resultatet kan kontrolleras senare. Det hjälper också när flera personer arbetar med samma analys eller när arbetet ska dokumenteras i en rapport.

För ledningen behöver informationen däremot översättas från tekniska detaljer till verksamhetsrisk. ATT&CK kan ge ett underlag för att förklara vilka beteenden som är relevanta, vilka skyddsluckor som finns och vilka åtgärder som bör prioriteras. Ledningen behöver inte kunna varje teknik, men behöver förstå konsekvenser, prioriteringar och ansvar. ATT&CK blir därmed en bro mellan teknisk analys och beslut om riskhantering.

# Del 2 - TTP: Tactic, Technique och Procedure

## Uppgift 5

Förklara skillnaden mellan tactic, technique och procedure.
Svarsinstruktion: Använd ett eget defensivt exempel. Håll dig på konceptuell nivå.

Tactic, technique och procedure beskriver angriparbeteenden på tre olika nivåer. En tactic beskriver varför angriparen gör något, alltså det övergripande målet. En technique beskriver vilken typ av beteende angriparen använder för att nå målet. En procedure beskriver hur ett visst beteende har använts i ett konkret fall eller i en specifik miljö.

Ett defensivt exempel kan vara misstänkta e-postmeddelanden som försöker få åtkomst till organisationen. Tacticen kan då vara Initial Access, eftersom målet är att få en första väg in. Tekniken kan vara Phishing, eftersom angriparen använder social manipulation via elektroniska meddelanden för att försöka nå det målet.

En procedure kan i detta exempel vara att säkerhetsteamet i en incident ser ett antal riktade e-postmeddelanden som utger sig för att komma från en betrodd intern funktion och försöker leda mottagaren till en falsk inloggningssida. Det är inte en instruktion för ett angrepp, utan en beskrivning av ett observerat beteende som teamet kan dokumentera och utreda. Blue team kan då kontrollera e-postloggar, berörda konton och om någon användare har interagerat med meddelandet.

MITRE beskriver tactics som angriparens mål, techniques som hur målet kan uppnås och procedures som konkreta användningar av tekniken.

## Uppgift 6

Skapa en TTP-förklaring för tre valfria ATT&CK-tekniker.
Svarsinstruktion: För varje teknik: skriv tactic, technique och en kort procedure-beskrivning utan operativa instruktioner.

1. Phishing (T1566)

Tactic: Initial Access

Technique: Phishing innebär att angriparen använder elektroniska meddelanden och social manipulation för att försöka få en första åtkomst.

Procedure: Säkerhetsteamet upptäcker en serie riktade e-postmeddelanden som utger sig för att komma från en betrodd avsändare. Teamet dokumenterar avsändare, mottagare och indikatorer, samt undersöker om något konto har påverkats.

2. Account Discovery (T1087)

Tactic: Discovery

Technique: Account Discovery innebär att angriparen försöker få information om vilka konton som finns i miljön.

Procedure: Vid incidentutredning ser teamet avvikande aktivitet där information om användarkonton och behörigheter efterfrågas från en enhet som normalt inte har detta arbetsflöde. Teamet jämför observationen med normal administrativ aktivitet innan den mappas till tekniken.

3. System Network Configuration Discovery (T1016)

Tactic: Discovery

Technique: System Network Configuration Discovery innebär att angriparen försöker förstå nätverksinställningar och anslutningar i en miljö.

Procedure: Loggar visar att en process, efter en misstänkt inloggning, samlar in information om nätverksgränssnitt och nätverksmiljö. Säkerhetsteamet bedömer tidpunkt, användarkonto och berörd enhet för att avgöra om beteendet är legitim administration eller en del av en incident.

## Uppgift 7

Välj en tactic och identifiera tre tekniker som kan höra hemma inom den.
Svarsinstruktion: Motivera varför teknikerna passar in i tacticen.

Jag väljer tacticen Discovery. Den handlar om att angriparen försöker förstå organisationens miljö, exempelvis vilka konton, system och nätverksresurser som finns. Tre tekniker som passar inom denna tactic är:

Account Discovery (T1087).Tekniken passar eftersom information om användarkonton och roller hjälper angriparen att förstå vilka identiteter som finns och vilka som kan vara värdefulla.

System Network Configuration Discovery (T1016).Tekniken passar eftersom nätverksinformation hjälper angriparen att skapa en bild av den aktuella enheten och dess anslutningar.

Remote System Discovery (T1018).Tekniken passar eftersom den handlar om att identifiera andra system i nätverket. Den informationen kan ge en angripare bättre förståelse för miljön, men ur försvarsperspektiv kan den också vara en signal om avvikande kartläggningsaktivitet.

Teknikerna hör ihop eftersom de alla ger information snarare än direkt förändrar eller skadar system. För ett säkerhetsteam är det viktigt att förstå att samma aktivitet ibland kan vara legitim administration. Därför måste observationen alltid bedömas utifrån vem som gjorde den, när den skedde och om den stämmer med den normala verksamheten.

## Uppgift 8

Beskriv varför det kan vara svårt att mappa en observation till rätt teknik.
Svarsinstruktion: Ta upp osäkerhet, kontext, datakvalitet och behov av källor

Det kan vara svårt att mappa en observation till rätt ATT&CK-teknik eftersom en enskild logghändelse sällan visar hela sammanhanget. Samma aktivitet kan vara normal administration i ett fall och misstänkt i ett annat. Exempelvis kan informationsinsamling om konton eller nätverksinställningar vara en legitim arbetsuppgift för IT-drift, men bli relevant för en incident om den sker från ett ovanligt konto, på en oväntad tid eller tillsammans med andra avvikelser.

Osäkerhet uppstår också när loggar saknas, är ofullständiga eller inte innehåller tillräckligt med information om användare, enhet och tidpunkt. Då riskerar analytikern att göra en för bred eller för specifik mappning. En observation kan dessutom stödja flera möjliga tekniker, och det kan vara oklart vilket angriparmål som bäst förklarar beteendet.

Därför behöver teamet jämföra flera datakällor, dokumentera sina antaganden och ange säkerhetsgrad i bedömningen. Källor som MITRE ATT&CK, interna loggar, incidentrapporter och hotinformation ger spårbarhet till analysen. Om underlaget inte räcker bör teamet skriva vad som är osäkert och vilken ytterligare data som behövs, i stället för att presentera en gissning som ett säkert resultat.

MITRE betonar också att ATT&CK beskriver observerade beteenden, men inte täcker alla möjliga hot eller ersätter organisationens egna underrättelsekällor och analys.

# Del 3 - Bygg en defensiv attackkedja

## Uppgift 9

Bygg en enkel attackkedja med 3-5 steg.
Svarsinstruktion: Använd tactics som etiketter. Syftet är analys och försvar, inte teknisk genomförandeinstruktion.

En möjlig hypotetisk attackkedja är:

Initial Access → Execution → Discovery → Collection → Impact

Initial Access: Phishing (T1566)

Execution: Command and Scripting Interpreter (T1059)

Discovery: Account Discovery (T1087)

Collection: Data from Information Repositories (T1213)

Impact: Data Encrypted for Impact (T1486)

Kedjan visar hur en angripare först kan försöka få åtkomst, därefter utföra aktiviteter, förstå miljön, samla information och slutligen påverka tillgängligheten till data. Syftet är att hjälpa säkerhetsteamet att identifiera möjliga detekteringspunkter och försvarsåtgärder, inte att beskriva hur ett angrepp ska genomföras.

## Uppgift 10

Beskriv varje steg i er kedja med “varför”, “hur” och “vad såg vi?”.
ITSX25 Kurs 6 · Individuell inlämningsuppgift Workshop 2
Svarsinstruktion: Koppla till TTP-modellen: tactic, technique och procedure.

Steg 1 – Initial Access: Phishing (T1566)

Varför: Angriparen försöker få en första väg in i organisationens miljö.

Hur: Ett elektroniskt meddelande använder social manipulation och utger sig för att komma från en betrodd avsändare.

Vad såg vi?: Hypotetiskt ser teamet riktade meddelanden, avvikande avsändarinformation och länkar eller bilagor som inte passar mottagarens normala arbete.

TTP-koppling: Tacticen är Initial Access, tekniken är Phishing och proceduren är det specifika observerade beteendet i den aktuella kampanjen.

Steg 2 – Execution: Command and Scripting Interpreter (T1059)

Varför: Angriparen försöker få aktiviteter eller kod att köras i miljön.

Hur: En inbyggd kommando- eller skriptmiljö används på ett sätt som avviker från normal användaraktivitet.

Vad såg vi?: Hypotetiskt ser teamet en ovanlig processkedja eller aktivitet kopplad till ett konto som normalt inte använder sådana verktyg.

TTP-koppling: Tacticen är Execution, tekniken är Command and Scripting Interpreter och proceduren är det konkreta beteendet som syns i endpoint- eller processloggar.

Steg 3 – Discovery: Account Discovery (T1087)

Varför: Angriparen försöker förstå vilka konton och roller som finns i miljön.

Hur: Information om användare eller behörigheter efterfrågas från en enhet eller ett konto som normalt inte gör detta.

Vad såg vi?: Hypotetiskt ser teamet avvikande frågor eller åtkomstmönster kring kontoinformation efter en misstänkt inloggning.

TTP-koppling: Tacticen är Discovery, tekniken är Account Discovery och proceduren är den specifika kontokartläggning som kan ha observerats.

Steg 4 – Collection: Data from Information Repositories (T1213)

Varför: Angriparen försöker samla information som kan ha värde för det fortsatta angreppet.

Hur: Gemensamma dokumentytor, kodarkiv eller andra informationsdatabaser används på ett sätt som avviker från användarens normala behov.

Vad såg vi?: Hypotetiskt ser teamet ovanligt många läsningar, sökningar eller hämtningar från känsliga lagringsytor.

TTP-koppling: Tacticen är Collection, tekniken är Data from Information Repositories och proceduren är det konkreta åtkomstmönstret i miljön.

Steg 5 – Impact: Data Encrypted for Impact (T1486)

Varför: Angriparen försöker störa verksamheten genom att göra data otillgänglig.

Hur: Data förändras på ett sätt som påverkar användarnas eller systemens tillgång till information.

Vad såg vi?: Hypotetiskt ser teamet en plötslig ökning av misslyckade filåtkomster, omfattande förändringar i dokument eller att viktiga tjänster inte längre fungerar normalt.

TTP-koppling: Tacticen är Impact, tekniken är Data Encrypted for Impact och proceduren är det observerade mönstret av påverkan.

## Uppgift 11

Identifiera vilka steg i attackkedjan som är mest osäkra.
Svarsinstruktion: Beskriv vad ni behöver veta mer om för att göra analysen bättre.

De mest osäkra stegen är Initial Access, Execution och Collection.

Vid Initial Access visar ett misstänkt e-postmeddelande inte automatiskt att någon klickade på det eller att ett konto faktiskt komprometterades. För att göra bedömningen bättre behöver vi e-postloggar, autentiseringsloggar och information från berörda enheter.

Execution är också osäkert eftersom kommandotolkar och skriptverktyg används legitimt av IT-personal. Vi behöver veta vilket konto som använde verktyget, vilken enhet det gällde, vid vilken tidpunkt och om aktiviteten stämmer med personens arbetsuppgifter.

Vid Collection kan stora mängder läsningar eller hämtningar vara normalt för vissa roller. Vi behöver därför jämföra med tidigare beteende, granska behörigheter och se vilka typer av data som berördes.

Även steget Impact behöver bekräftas innan vi drar slutsatsen att det rör sig om ett angrepp. Förändrade eller otillgängliga filer kan ha andra orsaker, exempelvis tekniska fel. En förbättrad analys kräver därför flera oberoende källor, en tidslinje och tydlig dokumentation av vad som är fakta respektive antaganden.

## Uppgift 12

Rita eller beskriv attackkedjan som en enkel kedja från första kontakt till påverkan.
Svarsinstruktion: Använd pilar och korta rubriker. Om ni skriver digitalt kan ni använda tabell eller punktlista.

[Första kontakt]
        ↓
[Initial Access – Phishing]
        ↓
[Execution – Command and Scripting Interpreter]
        ↓
[Discovery – Account Discovery]
        ↓
[Collection – Data from Information Repositories]
        ↓
[Impact – Data Encrypted for Impact]
        ↓
[Påverkan på data och verksamhet]

Steg

Tactic

Technique

Exempel på defensiv kontroll

1

Initial Access

Phishing (T1566)

E-postfiltrering och användarrapportering

2

Execution

Command and Scripting Interpreter (T1059)

Endpoint-loggning och avvikelseanalys

3

Discovery

Account Discovery (T1087)

Övervakning av ovanlig kontokartläggning

4

Collection

Data from Information Repositories (T1213)

Granskning av åtkomst till känsliga lagringsytor

5

Impact

Data Encrypted for Impact (T1486)

Säkerhetskopior, återställningsplan och larm vid massförändringar

# Del 4 - Försvarsfrågor och Blue/Purple-perspektiv

## Uppgift 13

Formulera minst en försvarsfråga per steg i attackkedjan.
Svarsinstruktion: Exempel: Hur skulle detta kunna upptäckas? Vilken signal, rutin eller kontroll kan vara relevant?

Initial Access – Phishing

Hur kan vi upptäcka och stoppa misstänkta meddelanden innan de leder till konto- eller systempåverkan?

Vilka signaler visar att ett meddelande avviker från normal kommunikation?

Finns det en tydlig rutin för att rapportera misstänkta meddelanden?

Execution – Command and Scripting Interpreter

Hur upptäcker vi att kommando- eller skriptverktyg används av ett oväntat konto eller på en ovanlig enhet?

Vilken loggning behöver finnas för att kunna koppla aktiviteten till användare, tidpunkt och system?

Hur skiljer vi legitim administration från misstänkt användning?

Discovery – Account Discovery

Hur kan vi upptäcka ovanlig kartläggning av användarkonton och behörigheter?

Har vi tillräcklig loggning för att se vem som efterfrågat kontoinformation och från vilken enhet?

Vilka kontroller begränsar åtkomst till information som inte behövs för arbetsuppgiften?

Collection – Data from Information Repositories

Hur upptäcker vi ovanligt stora läsningar, sökningar eller hämtningar från gemensamma lagringsytor?

Kan vi se om ett konto plötsligt får åtkomst till dokument eller kodarkiv som det normalt inte använder?

Finns det en rutin för att kontrollera och stoppa misstänkt åtkomst till känslig information?

Impact – Data Encrypted for Impact

Hur upptäcker vi snabbt en onormal mängd förändrade eller otillgängliga filer?

Finns det fungerande säkerhetskopior och en testad rutin för återställning?

Vem fattar beslut om att isolera system och starta incidenthantering?

## Uppgift 14

Välj två tekniker och resonera kring möjliga detektionssignaler.
Svarsinstruktion: Håll svaret på konceptuell nivå. Beskriv typer av signaler, inte tekniska exploit-steg.

Phishing (T1566)

Möjliga detektionssignaler är meddelanden från ovanliga eller falska avsändare, avvikande e-postdomäner, många liknande meddelanden till flera mottagare och användarrapporter om misstänkta meddelanden. En annan signal kan vara misslyckade eller ovanliga inloggningar kort efter att ett meddelande skickats. E-postfilter, identitetsloggar och användarnas rapporter behöver därför analyseras tillsammans i stället för var för sig.

Data from Information Repositories (T1213)

Möjliga signaler är ett ovanligt stort antal läsningar eller hämtningar, åtkomst vid ovanliga tider, aktivitet från en ny enhet eller plötslig åtkomst till många känsliga mappar. Även ett privilegierat konto som börjar använda lagringsytor det normalt inte arbetar med kan vara relevant. För att bedöma signalen behöver teamet jämföra med normal användning och kontrollera vilken information som faktiskt berördes.

## Uppgift 15

Välj två tekniker och resonera kring möjliga riskreducerande åtgärder.
Svarsinstruktion: Beskriv organisatoriska, tekniska eller processmässiga åtgärder.

Phishing (T1566)

Riskerna kan minskas organisatoriskt genom regelbunden utbildning och en enkel rutin för att rapportera misstänkta meddelanden. Tekniskt kan organisationen använda e-postfiltrering, skydd mot falska avsändare och multifaktorautentisering. Processmässigt bör rapporterade meddelanden snabbt bedömas och berörda konton följas upp om det finns tecken på påverkan.

Data Encrypted for Impact (T1486)

En viktig teknisk åtgärd är att ha separata och testade säkerhetskopior som inte enkelt kan påverkas från de vanliga användarkontona. Organisationen bör också använda behörighetsstyrning, segmentering och övervakning av onormalt många filförändringar. Processmässigt behövs en återställningsplan med tydliga roller, kontaktvägar och prioriterade system. Återställningen bör testas regelbundet, eftersom en säkerhetskopia som aldrig har provats inte garanterar att verksamheten kan återhämta sig.

## Uppgift 16

Beskriv hur ett säkerhetsteam kan använda en attackkedja för att förbättra sitt försvar.
Svarsinstruktion: Skriv 200-300 ord. Ta upp lärande, prioritering och uppföljning.

Ett säkerhetsteam kan använda en attackkedja som en gemensam modell för att förstå hur olika händelser kan hänga ihop. Genom att placera varje steg under en tactic och teknik blir det lättare att diskutera både angriparens möjliga mål och vilka försvar som finns. Teamet kan då jämföra kedjan med sina loggar, rutiner och säkerhetskontroller.

Attackkedjan hjälper också till att hitta luckor. Om organisationen kan upptäcka phishing men inte ovanlig kontoanvändning efteråt behöver det bli tydligt att identitetsövervakningen behöver förbättras. På samma sätt kan bristande säkerhetskopior eller återställningsrutiner göra det svårt att begränsa påverkan. Prioriteringen bör baseras på hur sannolikt ett steg är, vilken konsekvens det kan få och hur enkelt det är att minska risken.

Efter analysen bör varje åtgärd få en ansvarig person, en tidsplan och ett sätt att kontrollera resultatet. Teamet kan exempelvis följa upp om nya loggar samlas in, om larm testas och om återställning fungerar i en övning. Händelser, tester och nya hot kan sedan användas för att uppdatera kedjan.

På så sätt blir attackkedjan ett verktyg för lärande och kontinuerlig förbättring, inte bara en bild i en rapport. Den hjälper red team, blue team och ledning att se samma risk ur olika perspektiv och fatta mer välgrundade beslut.

# Del 5 - Källor, spårbarhet och kvalitet

## Uppgift 17

Dokumentera vilka källor ni använder i er ATT&CK-analys.
Svarsinstruktion: Skriv minst tre källor eller länkar. Beskriv kort vad varje källa bidrar med

1. MITRE ATT&CK Enterprise

MITRE ATT&CK Enterprise är huvudkällan för min ATT&CK-analys. Den bidrar med definitioner av tactics, techniques och sub-techniques samt exempel på observerade angriparbeteenden. Jag använder den för att kontrollera att mina TTP-mappningar har rätt namn, ID och tactic.

2. CISA Known Exploited Vulnerabilities Catalog

CISA KEV-katalog innehåller sårbarheter som är kända för att ha utnyttjats i verkligheten. Den bidrar med aktuell information för att bedöma vilka sårbarheter som bör prioriteras i en riskanalys. Katalogen ersätter inte min ATT&CK-mappning, men kan ge stöd för att bedöma hur brådskande en teknisk risk är.

3. NIST Cybersecurity Framework 2.0

NIST Cybersecurity Framework 2.0 bidrar med ett riskbaserat försvarsperspektiv. Jag använder den för att koppla analysen till att identifiera, skydda, upptäcka, hantera och återställa efter säkerhetsrisker. Den hjälper också till att formulera resultatet så att det kan förstås och prioriteras av olika mottagare.

4. Kursmaterial och egna anteckningar

Kursmaterialet används för att kontrollera att vi använder begreppen på det sätt som tagits upp under undervisningen och att analysen svarar mot uppgiftens mål. Egna anteckningar visar vilka antaganden och diskussioner som har påverkat våra slutsatser.

## Uppgift 18

Beskriv hur ni säkerställer att er TTP-mappning är rimlig.
Svarsinstruktion: Ta upp källa, motivering, osäkerhet och gruppgranskning.

Jag säkerställer att vår TTP-mappning är rimlig genom att arbeta systematiskt med varje observation. Först dokumenterar jag vad som faktiskt har observerats, när det skedde, vilken datakälla som användes och vilken kontext som finns. Därefter jämför jag observationen med MITRE ATT&CK officiella beskrivning och eventuella procedure-exempel.

Jag skriver sedan en motivering till varför en viss tactic och technique passar bättre än möjliga alternativ. Om en observation kan förklaras på flera sätt dokumenterar jag alternativen i stället för att presentera en osäker bedömning som säker fakta. Jag anger också vilken ytterligare information som skulle kunna bekräfta eller försvaga mappningen.

Alla mappningar ska innehålla källa, teknik-ID, kort motivering, antaganden och en bedömning av säkerhetsgrad.

## Uppgift 19

Skapa en mini-Definition of Done för en färdig hotanalys.
Svarsinstruktion: Lista minst fem kriterier. Kriterierna ska gå att använda av hela gruppen.

En färdig hotanalys ska uppfylla följande kriterier:

Omfattning, scenario och berörda tillgångar är tydligt beskrivna.

Varje observation har en angiven källa, tidpunkt och relevant kontext.

Tactic, technique och eventuellt sub-technique har korrekt namn och ATT&CK-ID.

Varje mappning har en begriplig motivering.

Antaganden, alternativa tolkningar och osäkerheter är dokumenterade.

Relevanta detektionssignaler och riskreducerande åtgärder är identifierade.

Källorna är aktuella, trovärdiga och länkade.

Analysen har granskats av minst en annan person i gruppen.

Kommentarer från granskningen är hanterade eller dokumenterade.

Den färdiga versionen är sparad på rätt plats och går att förstå utan muntlig förklaring från författaren.

## Uppgift 20

Beskriv vad som gör en hotanalys användbar för någon annan än den som skrev den.
Svarsinstruktion: Skriv 150-250 ord. Fokusera på tydlighet, spårbarhet och mottagare.

En hotanalys är användbar för någon annan än den som skrev den när läsaren kan förstå både slutsatsen och vägen dit. Analysen bör därför börja med en kort sammanfattning av det viktigaste: vilket hot eller scenario som analyseras, vilka tillgångar som berörs och vilka risker som bör prioriteras.

Tydlighet innebär att begrepp som tactic, technique och procedure används konsekvent och att tekniska detaljer förklaras på en nivå som passar mottagaren. En teknisk analytiker kan behöva se mer information om loggar och indikatorer, medan ledningen främst behöver förstå konsekvens, prioritet och rekommenderad åtgärd.

Spårbarhet innebär att varje viktig slutsats kan kopplas till en källa, en observation eller ett tydligt antagande. Läsaren ska kunna se varför en viss ATT&CK-teknik valdes och vad som fortfarande är osäkert. Därför bör analysen även beskriva datakvalitet och alternativa tolkningar.

En användbar analys avslutas med prioriterade rekommendationer, ansvar och nästa steg. Då blir den ett beslutsunderlag och inte bara en beskrivning av ett hot. Kvaliteten ökar också när en annan person kan granska analysen och förstå den utan att behöva fråga författaren om bakgrunden.

# Del 6 - Koppling till backlog, sprint och Workshop 3

## Uppgift 21

Uppdatera er backlog baserat på det ni upptäckte i Workshop 2.
Svarsinstruktion: Skriv minst fem nya eller ändrade backlog items. Ge kort motivering.

Min grupp har uppdaterat/ändrat i backlog items

## Uppgift 22

Beskriv hur er attackkedja förhåller sig till ert Sprint Goal.
Svarsinstruktion: Är sprintmålet fortfarande relevant? Behöver något justeras?

Vår attackkedja stödjer fortfarande Sprint Goal eftersom den hjälper oss att skapa ett gemensamt och dokumenterat underlag för hotanalysen. Genom kedjan kan vi koppla ihop hot, TTP, möjliga observationer och försvarsåtgärder i en tydlig ordning.

Sprintmålet är därför fortfarande relevant, men det behöver preciseras något. Det bör inte bara handla om att identifiera hot och sårbarheter, utan också om att visa hur en möjlig kedja kan upptäckas och brytas. Vi behöver därför lägga till kvalitetssäkring av TTP-mappningar, dokumentation av osäkerheter och prioritering av försvarsåtgärder.

Ett justerat Sprint Goal kan vara:

Målet med sprinten är att skapa en källbaserad och granskad attackkedja som visar relevanta TTP, möjliga detektionssignaler och prioriterade försvarsåtgärder.

## Uppgift 23

Formulera minst två uppföljningsfrågor inför Workshop 3.
Svarsinstruktion: Frågorna ska kunna användas vid review eller retrospektiv.

Vilka steg i attackkedjan har bäst stöd i källor och observationer, och vilka steg bygger fortfarande främst på antaganden?

Vilken detektionssignal eller försvarsåtgärd skulle ge störst riskminskning, och varför bör den prioriteras?

Kan en person utanför gruppen förstå attackkedjan och veta vad organisationen bör göra härnäst?

## Uppgift 24

Förbered en kort statusrapport till Workshop 3.
Svarsinstruktion: Skriv 5-7 punkter: vad ni gjorde, vad som blev klart, vad som är oklart och vad ni vill ändra.

Vi analyserade hur MITRE ATT&CK kan användas för att beskriva tactics, techniques och procedures ur ett defensivt perspektiv.

Vi byggde en hypotetisk attackkedja från Initial Access till Impact.

Vi kopplade varje steg till en teknik, möjlig observation och relevant försvarsfråga.

Vi dokumenterade MITRE ATT&CK, CISA och NIST som källor för analys och prioritering.

Vi blev klara med en första TTP-mappning, men vissa steg är fortfarande osäkra eftersom vi saknar fullständig kontext och verkliga loggdata.

Vi behöver granska mappningarna tillsammans och skilja tydligare mellan fakta, antaganden och alternativa förklaringar.

Inför Workshop 3 vill vi uppdatera backloggen, prioritera försvarsåtgärder och förbättra hur attackkedjan presenteras för olika mottagare.

## AI-användning

Jag använde ChatGPT som stöd för att strukturera svar, förklara MITRE ATT&CK-begrepp och formulera defensiva exempel. Jag kontrollerade manuellt tekniknamn, tactic-namn och ATT&CK-ID:n mot [MITRE ATT&CK](https://attack.mitre.org/) samt jämförde innehållet med kursmaterial och egna anteckningar.