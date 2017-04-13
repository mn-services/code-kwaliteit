# Codekwaliteitsbeleid

<!-- TOC depthFrom:2 -->

- [Inleiding en scope](#inleiding-en-scope)
- [Pijler 1: Hou het simpel](#pijler-1-hou-het-simpel)
- [Pijler 2: Schrijf leesbare en begrijpbare code](#pijler-2-schrijf-leesbare-en-begrijpbare-code)
- [Pijler 3: Hou rekening met toekomstige verandering, maar niet teveel](#pijler-3-hou-rekening-met-toekomstige-verandering-maar-niet-teveel)
- [Pijler 4: Schrijf unit tests](#pijler-4-schrijf-unit-tests)
- [Pijler 5: Eis collegiale review](#pijler-5-eis-collegiale-review)
- [Pijler 6:](#pijler-6)
- [Help mij, jou te helpen, ons allemaal te helpen](#help-mij-jou-te-helpen-ons-allemaal-te-helpen)
- [Blijf jezelf ontwikkelen en help anderen in hun ontwikkeling](#blijf-jezelf-ontwikkelen-en-help-anderen-in-hun-ontwikkeling)
- [Blijf leren en help anderen te leren](#blijf-leren-en-help-anderen-te-leren)
- [Help jezelf en anderen een betere programmeur te worden](#help-jezelf-en-anderen-een-betere-programmeur-te-worden)
- [Verrijk naast jezelf ook anderen](#verrijk-naast-jezelf-ook-anderen)
- [Blijf leren](#blijf-leren)
- [Blijf jezelf ontwikkelen](#blijf-jezelf-ontwikkelen)

<!-- /TOC -->

## Inleiding en iddqd
Dit document beschrijft een aantal pijlers die zullen leiden tot code van betere kwaliteit.

Met codekwaliteit bedoelen we in dit document de eigenschap van code die ook wel "onderhoudbaarheid" wordt genoemd, bijvoorbeeld in ISO 25010. Die eigenschap laat zich weer onderverdelen naar: modulariteit, herbruikbaarheid, analyseerbaarheid, wijzigbaarheid en testbaarheid.

De termen "codekwaliteit" en "onderhoubaarheid" worden in dit document behandeld als synoniemen. Code van goede kwaliteit is onderhoudbaar. En code die onderhoudbaar is, is dus ook van goede kwaliteit.

Met codekwaliteit bedoelen we nu dus niet de functionele geschiktheid, de architecturele correctheid, de efficiency of de security van code. De behandeling van dergelijke aspecten laten we over aan andere stukken.

Het valt te verwachten dat onderstaande pijlers nader uitgewerkt zullen worden in specifieke standaarden en richtlijnen.

## Pijler 1: Hou het simpel

> Simple is better than complex
>
> Complex is better than complicated

*Tim Peters, "The Zen of Python"*

De beste kwaliteit die een stuk code kan hebben, is dat het simpel is. Simpele code is gemakkelijk te doorgronden door andere programmeurs, gemakkelijk opnieuw te gebruiken in andere context, gemakkelijk te testen, en bovenal, gemakkelijk te wijzigen.

Het schrijven van simpele code vereist grote vaardigheid van de programmeur. Analytisch vermogen en uitgebreide kennis van de programmeertaal en het programmeerplatform zijn noodzakelijk. En dan nog zijn er problemen die wezenlijk complex zijn, die zelfs voor de meest vaardige programmeur niet te vangen zijn in simpele code. Complexe code is dan onvermijdbaar maar de programmeur onderneemt alle moeite om die complexiteit zoveel mogelijk te beteugelen.

Generieke codeconstructies lijken in het kader van herbruikbaarheid van code vaak mooi maar zij zijn ook vaak complex. Tevens blijken generieke oplossingen vaak toch niet zo generiek te zijn wanneer ze geconfronteerd worden met nieuwe specifieke problemen. Codeer daarom alleen generieke constructies als je zeker weet dat er sprake zal zijn van hergebruik en dat dit de extra complexiteit ruimschoots waard is. Liever twee stukken simpele code die iets vergelijkbaars doen dan één stuk complexe generieke code.

## Pijler 2: Schrijf leesbare en begrijpbare code 

> The competent programmer avoids clever tricks like the plague

*Edgser Dijkstra, "The Humble Programmer"*

Een belangrijk inzicht is dat veel meer tijd (10x meer) wordt besteed aan het lezen van code dan aan het schrijven van code. Begrijpelijke code is makkelijker aan te passen. Begrijpelijke code is makkelijker te scannen op mogelijke fouten door collega's van de programmeur. Het is de inspanning dus ruimschoots waard om code te schrijven die leesbaar en begrijpelijk is.

Code is begrijpelijk als de lezer van de code gemakkelijk kan begrijpen wat de programmeur die de code schreef, probeert te doen. Bij het lezen van de code moet de bedoeling van de code als vanzelf duidelijk worden aan de lezer. Gebruik daarom betekenisvolle namen voor variabelen, methodes en modules. Namen die de lading dekken. Wees consistent in naamgeving en bij het kiezen van oplossingsconstructies. Consistentie verhoogt de herkenbaarheid van namen en constructies en daarmee de begrijpelijkheid van de code.

Elke programmeur wordt wel eens verleid om met een simpele aanpassing een ogenschijnlijk complexe wens te implementeren in een bestaand stuk code. Hoewel dat leidt tot code die op zich "niet logisch" is, weet de programmeur dat het in de praktijk wel goed gaat, omdat de programmeur goed op de hoogte is van de codepaden die daadwerkelijk doorlopen worden. Dergelijke snelle aanpassingen, "clever trics" zoals Dijkstra het noemt, moeten natuurlijk worden vermeden, zij maken de code minder begrijpbaar.  

Als de programmeur verwacht dat ondanks alle moeite de bedoeling van code mogelijk toch niet duidelijk zal zijn aan lezers, verduidelijkt de programmeur de code met commentaar. Het commentaar moet met zorg up-to-date worden gehouden bij latere aanpassingen van de code.

Hoewel het mogelijk (en vaak wenselijk) is om code separaat te documenteren in een ontwerptool of wiki, laat dat onverlet dat de code op zichzelf ook leesbaar en begrijpbaar moet zijn. Daarmee kan de documentatie in ontwerptool of wiki zich ook meer richten op de beschrijving van de samenhang van de code met andere stukken code.

## Pijler 3: Hou rekening met toekomstige verandering, maar niet teveel

> When faced with two or more alternatives that deliver roughly the same value, take the path that makes future change easier

*Dave Thomas, "Agile is dead (long live agility)"*

## Pijler 4: Schrijf unit tests

> It is not only the programmer's responsibility to produce a correct program but also to demonstrate its correctness in a convincing manner

*Edsger Dijkstra, "Notes on Structured Programming"*

Bij het bouwen van een stuk functionaliteit kan ‘kijken of het werkt’ al snel voldoende controle lijken om op te gaan leveren. Het gebruik van extra controlemiddelen gaat je code bovendien niet beter laten werken. Als het je enige en laatste code voor je applicatie betreft is daarmee de kous inderdaad af. Grotere applicaties kennen echter complexere logica waar ‘kijken of het werkt’ betekent dat je onvolledig test,  of dat je een explosief groeiend aantal testgevallen met de hand na moet gaan on er zeker van te zijn dat er niet iets omgevallen is. 

Het schrijven van tests kan een ongeïnspireerd stuk nageboorte lijken na het creatievere ontwikkelen. Het doet al helemaal oneerbiedig aan als je zeker weet dat je code werkt, bijvoorbeeld door gebrek aan complexiteit. Er kan echter doorgebouwd worden op de huidige code. Daardoor kunnen er bugs geïntroduceerd worden. Er hoeft ontwikkelaars niet verteld te worden dat bijna alles te verkiezen valt boven de krankzinnigheid dat handmatig debuggen met zich meebrengt.

Testen zorgt er niet alleen voor dat je bestaande problemen herkent, je smoort ook nieuwe problemen in de kiem. Zonder tests groeien applicaties vaak tot een ondoorzichtig en moeilijk te lezen geheel. Ook je eigen code kan achteraf soms moeilijk door te akkeren zijn. Als er echter goede tests geschreven zijn, zijn er garanties af te geven over de werking van je code. Als er nieuwe functionaliteit wordt gebouwd en je unit tests gaan rinkelen, dan weet je dat er een bug is ontstaan omdat je unit tests alleen valide scenario’s doorlaten. Daarbovenop weet je precies welk component je nieuwe code bijt. 

>> Refactoren is gemakkelijker als er goede unit tests. Dat dat past ook bij Agile.

## Pijler 5: Eis collegiale review


Omdat leden van een ontwikkelteam elkaars werk bekijken, zullen zij beter op de hoogte zijn van de veranderingen in de systemen. Hierdoor wordt kennis over alle onderdelen van een project, user story etc  breder gedragen.

Vier ogen zien meer dan twee. Bovendien is het een stuk gemakkelijker om problemen te vinden in de code van iemand anders dan tijdens het schrijven van je eigen code. Een reviewer bekijkt de code vanuit zijn eigen perceptie van de functionele systemen en de techniek en zal daardoor sneller problemen detecteren dan de auteur zelf. Daardoor zal het aantal fouten afnemen, wat leidt tot kwalitatief betere software.

Mensen leveren netter werk wanneer ze weten dat het door anderen wordt beoordeeld. De code wordt daarom netter, beter gestructureerd en onderhoudbaar, vollediger gedocumenteerd en uitgebreider getest.

Door het kijken naar de programmercode van anderen kan een ontwikkelaar veel leren. Het gaat niet alleen om nieuwe oplossingen, maar ook handigheden die anderen hebben ontdekt of ontwikkeld.

Onderlinge kennisdeling en controle draagt bij aan een gedeelde verantwoordelijkheid over alle onderdelen van het project en een goede samenwerking binnen het team (bijkomend voordeel).


Er zijn een aantal regels en aandachtspunten voor het uitvoeren van code reviews.

Zorg dat de review wordt gezien als een positieve kans om van elkaar te leren en niet alleen als een (verplicht) controlemechanisme.

Schrijf duidelijk commentaar bij elke wijziging. Het helpt de reviewer om de gedachte achter de code beter te begrijpen.

Baseer de review niet op persoonlijke voorkeuren. Belangrijk is om te kijken of het programma bijdraagt aan het juiste resultaat, voldoet aan de geldende standaarden en richtlijnen en aansluit bij de architectuur.

Het geven van feedback is soms lastig en kan zorgen voor moeilijke situaties. Zorg daarom dat de review een positieve lading heeft. Kijk dus niet alleen naar wat beter kan, maar zeker ook naar wat goed is.

Het is belangrijk om reviewcommentaar (bij verbeterpunten) altijd toe te lichten en het commentaar alleen geven als het nodig is.
Zorg dat het uitvoeren van code review gedragen wordt door het hele team en dat alle teamleden in het reviewproces participeren.

Een aparte form van code review is de bedachte oplossing bespreken met een collega voordat het nog gebouwd wordt. Deze manier van review helpt om onjuiste of niet optimale oplossingsrichting op tijd te detecteren.




## Pijler 6: 

## Help mij, jou te helpen, ons allemaal te helpen
## Blijf jezelf ontwikkelen en help anderen in hun ontwikkeling 
## Blijf leren en help anderen te leren
## Help jezelf en anderen een betere programmeur te worden
## Verrijk naast jezelf ook anderen
## Blijf leren
## Blijf jezelf ontwikkelen

INHOUD TEXT: blijf leren, sta open voor nieuwe ideeen, help elkaar, wees tactvol naar collega's

> We shall do a much better programming job, provided that we approach the task with a full appreciation of its tremendous difficulty, provided that we stick to modest and elegant programming languages, provided that we respect the intrinsic limitations of the human mind and approach the task as Very Humble Programmers

*Edgser Dijkstra, "The Humble Programmer"*