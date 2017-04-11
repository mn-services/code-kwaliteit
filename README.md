# Codekwaliteitsbeleid

## Inleiding en scope
Dit document beschrijft een aantal pijlers die zullen leiden tot code van betere kwaliteit.

Met codekwaliteit bedoelen we in dit document de eigenschap van code die ook wel "onderhoudbaarheid" wordt genoemd, bijvoorbeeld in ISO 25010. Die eigenschap laat zich weer onderverdelen naar: modulariteit, herbruikbaarheid, analyseerbaarheid, wijzigbaarheid en testbaarheid.

De termen "codekwaliteit" en "onderhoubaarheid" worden in dit document behandeld als synoniemen. Code van goede kwaliteit is onderhoudbaar. En code die onderhoudbaar is, is dus ook van goede kwaliteit. Maar omdat de titel "onderhoudsbaarheidsbeleid" minder goed de lading van dit document zou communiceren naar mogeljke lezers, kiezen we voor de titel "codekwaliteitsbeleid".    

Met codekwaliteit bedoelen we nu dus niet de functionele geschiktheid, de efficiency of de security van code. De behandeling van dergelijke aspecten laten we over aan andere stukken.

## Pijler 1: Hou het simpel

> Simple is better than complex
> Complex is better than complicated

*Tim Peters, "The Zen of Python"*

De beste kwaliteit die een stuk code kan hebben, is dat het simpel is. Simpele code is gemakkelijk te doorgronden door andere programmeurs, gemakkelijk opnieuw te gebruiken in andere context, gemakkelijk te testen, en bovenal, gemakkelijk te wijzigen.

Het schrijven van simpele code vereist grote vaardigheid van de programmeur. Analytisch vermogen is nodig om het concrete probleem te zien in een abstracte weergave, zodat het op te lossen is met de juiste code. Ook is uitgebreide kennis van de programmeertaal en het programmeerplatform noodzakelijk. Niet elke programmeur kan simpele code schrijven. Steker nog, niet elke programmeur kan dit leren. En dan nog zijn er problemen die wezenlijk complex zijn, die zelfs voor de meest vaardige programmeur niet te vangen zijn in simpele code. Complexe code is dan onvermijdbaar maar de programmeur onderneemt alle moeite om die complexiteit zoveel mogelijk te beteugelen.

## Pijler 2: Schrijf leesbare en begrijpbare code 

> The competent programmer avoids clever tricks like the plague

*Edgser Dijkstra, "The Humble Programmer"*

Een belangrijk inzicht is dat veel meer tijd (10x meer) wordt besteed aan het lezen van code dan aan het schrijven van code. Het is de inspanning dus ruimschoots waard om code te schrijven die leesbaar en begrijpelijk is. Nota bene, dus niet alleen leesbaar, maar ook begrijpelijk.

Code is begrijpelijk als de lezer van de code gemakkelijk kan begrijpen wat de programmeur die de code schreef, probeert te doen. Bij het lezen van de code moet de bedoeling van de code als vanzelf duidelijk worden aan de lezer. Een belangrijke manier om dat te bereiken is door betekenisvolle namen te gebruiken voor variabelen, methodes en modules. Namen die de lading dekken. Een andere belangrijk hulpmiddel is de toepassing van consistentie bij het kiezen van namen en oplossingsconstructies. Consistentie verhoogt de herkenbaarheid van namen en constructies en daarmee de begrijpelijkheid van de code. 

Elke programmeur wordt wel eens verleid om met een simpele aanpassing een ogenschijnlijk complexe wens te implementeren in een bestaand stuk code. Hoewel dat leidt tot code die op zich "niet logisch" is, weet de programmeur dat het in de praktijk wel goed gaat, omdat de programmeur goed op de hoogte is van de codepaden die daadwerkelijk doorlopen worden. Dergelijke snelle aanpssingen, "clever trics" zoals Dijkstra het noemt, moeten worden vermeden, zij maken de code minder begrijpbaar.  

Als de programmeur verwacht dat ondanks alle moeite de bedoeling van code mogelijk toch niet duidelijk zal zijn aan lezers, en alleen dan, verduidelijkt de programmeur de code met commentaar. Dit is een uiterste optie, het risico is dat het commentaar na wijziging van de code verouderd raakt en de lezer juist de verkeerde kant op stuurt.

## Pijler 3: Hou rekening met toekomstige verandering

> When faced with two or more alternatives that deliver roughly the same value, take the path that makes future change easier

*Dave Thomas, "Agile is dead (long live agility)"*

## Pijler 4: Schrijf unit tests

> It is not only the programmer's responsibility to produce a correct program but also to demonstrate its correctness in a convincing manner

*Edsger Dijkstra, "Notes on Structured Programming"*

## Pijler 5: Eis collegiale review



## Pijler 6: Benader de programmertaak met nederigheid

> We shall do a much better programming job, provided that we approach the task with a full appreciation of its tremendous difficulty, provided that we stick to modest and elegant programming languages, provided that we respect the intrinsic limitations of the human mind and approach the task as Very Humble Programmers

*Edgser Dijkstra, "The Humble Programmer"*