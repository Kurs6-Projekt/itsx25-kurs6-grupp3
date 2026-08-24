# Workshop 2 - MITRE ATT&CK och hotanalys

## Scenario

Vi valde ett scenario där en person på ett företag får ett mejl som ser ut att komma från en leverantör som företaget redan har kontakt med.

I mejlet finns en länk till en sida som ser ut som Microsoft 365. Om personen loggar in där kan angriparen få tag på kontot och använda det för att komma vidare i företagets miljö.

Vi valde detta scenario eftersom det känns ganska realistiskt och inte bygger på att angriparen direkt installerar malware.

## Attackkedja

Vi valde fem tekniker som vi tycker hänger ihop på ett rimligt sätt.

1. Spearphishing Link - T1566.002
2. Valid Accounts: Cloud Accounts - T1078.004
3. Account Discovery: Cloud Account - T1087.004
4. SharePoint - T1213.002
5. Email Forwarding Rule - T1114.003

Tanken är att angriparen först försöker lura användaren via ett falskt mejl. Om användaren lämnar sina uppgifter kan angriparen använda det riktiga kontot.

När angriparen väl är inne försöker den förstå vilka användare som finns och vilken information som kan vara intressant. Därefter kan den söka i SharePoint och skapa en regel som skickar vidare vissa mejl.

## TTP

| Steg | Tactic | Technique | Vad händer? |
|---|---|---|---|
| 1 | Initial Access | T1566.002 Spearphishing Link | Användaren får ett falskt leverantörsmejl med en länk till en falsk Microsoft 365-inloggning. |
| 2 | Initial Access | T1078.004 Valid Accounts | Angriparen använder användarens riktiga konto för att logga in. |
| 3 | Discovery | T1087.004 Account Discovery | Angriparen försöker se vilka andra användare och konton som finns. |
| 4 | Collection | T1213.002 SharePoint | Angriparen letar efter dokument eller annan information i SharePoint. |
| 5 | Collection | T1114.003 Email Forwarding Rule | En regel skapas för att skicka vidare vissa mejl till en extern adress. |

## Försvarsfrågor

För varje steg funderade vi på hur man skulle kunna upptäcka eller minska risken.

- Hur kan man upptäcka att ett mejl leder till en falsk inloggningssida?
- Hur kan man se om någon annan använder ett riktigt konto?
- Hur märker man om ett konto plötsligt börjar leta efter andra användare?
- Hur upptäcker man ovanligt mycket aktivitet i SharePoint?
- Hur ser man om någon skapar en ny regel för vidarebefordring av mejl?

## Backlogg

Vi har uppdaterat backloggen med arbetet från Workshop 2.

Det vi har arbetat med är:

- välja scenario
- bygga attackkedjan
- koppla stegen till MITRE ATT&CK
- skriva försvarsfrågor
- dokumentera det vi fortfarande är osäkra på

Gruppen har gått igenom materialet tillsammans och godkänt det.

## Sprintmål

Vi har följt upp sprintmålet genom att jämföra det vi skulle göra med det vi faktiskt har fått fram.

Vi tycker att vi har kommit ganska långt eftersom attackkedjan är klar och dokumenterad. Vi har också kopplat den till MITRE ATT&CK och skrivit frågor ur ett försvarsperspektiv.

Gruppen har gått igenom arbetet tillsammans och vi räknar därför den här delen som klar.

## Definition of Done

Vi har försökt använda vår Definition of Done för att kontrollera arbetet.

Det som är klart nu:

- arbetet är dokumenterat
- attackkedjan går att följa
- MITRE-teknikerna finns med
- försvarsfrågor finns med
- våra osäkerheter är dokumenterade

Gruppen har gjort en gemensam kontroll och godkänt innehållet. Vi bedömer därför att vår Definition of Done är uppfylld för den här delen.

## Osäkerheter

Det finns fortfarande några saker vi inte är helt säkra på:

- Vi vet inte exakt vilka Microsoft 365-loggar som hade varit viktigast att titta på.
- Det är svårt att veta när vanlig aktivitet börjar bli misstänkt.
- Vi är osäkra på hur lätt det är att upptäcka ett kapat konto om rätt användarnamn och lösenord används.
- En vidarebefordringsregel kan också vara legitim, så man behöver nog titta på mer än bara att regeln finns.

## Frågor till Workshop 3

- Vilka loggar hade varit viktigast för att upptäcka den här attackkedjan?
- I vilket steg hade man haft bäst chans att stoppa angriparen?
- Behöver vi ändra något i backloggen efter den här analysen?

## Källor

- MITRE ATT&CK
- MITRE Enterprise Matrix
- Kursmaterial Workshop 2
