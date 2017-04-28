# Codekwaliteitsbeleid

<!-- TOC depthFrom:2 -->

- [Inleiding](#inleiding)
- [Pijler 1: Hou het simpel](#pijler-1-hou-het-simpel)
- [Pijler 2: Schrijf leesbare en begrijpbare code](#pijler-2-schrijf-leesbare-en-begrijpbare-code)
- [Pijler 3: Programmeer agile, één stap tegelijk](#pijler-3-programmeer-agile-één-stap-tegelijk)
- [Pijler 4: Schrijf unit tests (en refactor)](#pijler-4-schrijf-unit-tests-en-refactor)
- [Pijler 5: Eet exceptions niet op](#pijler-5-eet-exceptions-niet-op)
- [Pijler 6: Eis collegiale review](#pijler-6-eis-collegiale-review)
- [Pijler 7: Meet de kwaliteit van de code](#pijler-7-meet-de-kwaliteit-van-de-code)
- [Pijler 8: Houd het vak in leven](#pijler-8-houd-het-vak-in-leven)
- [Toegift](#toegift)

<!-- /TOC -->

## Inleiding
Dit document beschrijft een aantal pijlers die zullen leiden tot code van betere kwaliteit.

Met codekwaliteit bedoelen we in dit document de eigenschap van code die ook wel "onderhoudbaarheid" wordt genoemd, bijvoorbeeld in ISO 25010. Die eigenschap laat zich weer onderverdelen in: modulariteit, herbruikbaarheid, analyseerbaarheid, wijzigbaarheid en testbaarheid.

De termen "codekwaliteit" en "onderhoudbaarheid" worden in dit document behandeld als synoniemen. Code van goede kwaliteit is onderhoudbaar. En code die onderhoudbaar is, is dus ook van goede kwaliteit.

Met codekwaliteit bedoelen we nu dus niet de functionele geschiktheid, de architecturele correctheid, de efficiency of de security van code. De behandeling van dergelijke aspecten laten we over aan andere stukken.

Het valt te verwachten dat onderstaande pijlers nader uitgewerkt zullen worden in specifieke standaarden en richtlijnen, voor de specifieke programmeertalen die van toepassing zijn.

## Pijler 1: Hou het simpel

> Simple is better than complex
>
> Complex is better than complicated

*Tim Peters, "The Zen of Python"*

> Simplicity is prerequisite for reliability

*Edsger Dijkstra, "How do we tell truths that might hurt?"*

De beste kwaliteit die een stuk code kan hebben, is dat het simpel is. Simpele code is gemakkelijk te doorgronden door andere programmeurs, gemakkelijk opnieuw te gebruiken, gemakkelijk te testen en gemakkelijk te wijzigen.

Het schrijven van simpele code vereist grote vaardigheid. Analytisch vermogen en uitgebreide kennis van de programmeertaal en het programmeerplatform zijn noodzakelijk. En dan nog zijn er problemen die wezenlijk complex zijn, die zelfs voor de meest vaardige programmeur niet te vangen zijn in simpele code. Complexe code is dan onvermijdbaar, maar onderneem alle moeite om die complexiteit zoveel mogelijk te beteugelen.

Code simpel houden is een kunst maar er zijn vuistregels die helpen:

* Schrijf korte stukken code. Knip grotere stukken code op in kleine simpele delen. Een code-eenheid (bijv. een methode) moet te lezen zijn zonder te scrollen.

* Ga niet verder dan 2 niveaus van geneste blocks als if-statements en loops.

* Zorg dat elke code-eenheid maar 1 ding doet, 1 duidelijke verantwoordelijkheid heeft.

Generieke codeconstructies lijken in het kader van herbruikbaarheid van code vaak mooi, maar ze zijn ook vaak complex. Tevens blijken generieke oplossingen vaak toch niet zo generiek te zijn wanneer ze geconfronteerd worden met nieuwe specifieke problemen. Codeer daarom alleen generieke constructies als je zeker weet dat er sprake zal zijn van hergebruik en dat dit de extra complexiteit ruimschoots waard is. Liever twee stukken simpele code die iets vergelijkbaars doen, dan één stuk complexe generieke code.

## Pijler 2: Schrijf leesbare en begrijpbare code

> “Good code is its own best documentation. As you’re about to add a comment, ask yourself, "How can I improve the code so that this comment isn’t needed?" Improve the code and then document it to make it even clearer

*Steve McConnell, "Code Complete"*

> The competent programmer avoids clever tricks like the plague

*Edgser Dijkstra, "The Humble Programmer"*

Een belangrijk inzicht is dat veel meer tijd (10x meer) wordt besteed aan het lezen van code dan aan het schrijven van code. Begrijpelijke code is makkelijker aan te passen. Begrijpelijke code is makkelijker te scannen op mogelijke fouten door collega's van de programmeur. Het is de inspanning dus ruimschoots waard om code te schrijven die leesbaar en begrijpelijk is.

Code is begrijpelijk als de lezer van de code gemakkelijk kan begrijpen wat de programmeur die de code schreef, probeert te doen. Gebruik daarom betekenisvolle namen voor variabelen, methodes en modules. Namen die de lading dekken. Wees consistent in naamgeving en bij het kiezen van oplossingsconstructies. Consistentie verhoogt de herkenbaarheid van namen en constructies en daarmee de begrijpelijkheid van de code.

Elke programmeur wordt wel eens verleid om met een "slimmige" aanpassing een ogenschijnlijk complexe wens te implementeren in een bestaand stuk code. Hoewel dat leidt tot code die op zich "niet logisch" is, denkt de programmeur te weten dat het in de praktijk wel goed gaat. De programmeur is immers goed op de hoogte van de codepaden die doorlopen worden. Vermijd dergelijke "clever trics" zoals Dijkstra het noemt, want die maken de code minder begrijpbaar.  

Als je verwacht dat ondanks alle moeite de bedoeling van je code mogelijk toch niet duidelijk zal zijn aan lezers, verduidelijk de code dan met commentaar. Het commentaar moet met zorg up-to-date worden gehouden bij latere aanpassingen van de code.

Hoewel het wenselijk kan zijn om code separaat te documenteren in een ontwerptool of wiki, laat dat onverlet dat de code op zichzelf ook leesbaar en begrijpbaar moet zijn. Daarmee kan de documentatie in ontwerptool of wiki zich ook meer richten op de beschrijving van de samenhang van de code met andere stukken code.

## Pijler 3: Programmeer agile, één stap tegelijk

> When faced with two or more alternatives that deliver roughly the same value, take the path that makes future change easier

*Dave Thomas, "Agile is dead (long live agility)"*

> Be mindful of the future, but not at the expense of the moment

*Qui-Gon Jinn, "Star Wars: Episode I - The Phantom Menace"*

Codeer niet meer dan wat de huidige user story vraagt. Als je de oplossing op meerdere manieren kunt coderen, kies dan de manier die later het gemakkelijkst aan te passen zal zijn.

Vele programmeurs zijn met de beste bedoelingen in de valkuil gestapt om code te generiek en te herbruikbaar op te zetten, om er later achter te komen dat het geen herbruikbare oplossing was. Of met mindere bedoelingen in de andere valkuil, om snelle code te schrijven die nu werkt maar latere aanpassingen van het systeem moeilijk zullen maken.

Het heeft geen zin om "nu" generieke/herbruikbare oplossingen te maken als dat veel meer tijd kost dan "nu" coderen wat "nu" nodig is. Neem in plaats daarvan "later" de ruimte om code te refactoren; op het moment dat "dan" blijkt dat zo'n generieke/herbruikbare opzet wenselijk is.

## Pijler 4: Schrijf unit tests (en refactor)

> It is not only the programmer's responsibility to produce a correct program but also to demonstrate its correctness in a convincing manner

*Edsger Dijkstra, "Notes on Structured Programming"*

Codeer niet alleen "de code zelf" maar codeer ook unit tests: stukjes code die jouw code testen. Door het schrijven van unit tests denk je beter na over je code en overtuig je jezelf en collega's van de correctheid van die code. De unit tests moeten eenvoudig en snel herhaalbaar zijn, zodat bij volgende aanpassingen kan worden vastgesteld dat eerder gerealiseerde code nog steeds werkt zoals jij toen voor ogen had. Draai alle unit tests (liefst automatisch) van het stuk code dat onder handen is bij aanpassingen van de code.

Bij het bouwen van een stuk functionaliteit kan 'kijken of het werkt' al snel voldoende controle lijken om op te gaan leveren. Echter, serieuze applicaties kennen complexere logica waar 'kijken of het werkt' betekent dat je onvolledig test, of dat je een explosief groeiend aantal testgevallen met de hand na moet gaan on er zeker van te zijn dat er niet iets omgevallen is. Dat is natuurlijk onwenselijk; unit tests bieden hierin uitkomst.

Fouten detecteren en oplossen met unit tests is goedkoper dan zonder unit tests. Unit tests moeten een goede dekking van het systeem bieden. Ze moeten eenvoudig opgesteld zijn, zodat ze makkelijk te begrijpen, te onderhouden en te repareren zijn.

In elke serieuze applicatie die langer mee gaat, moet bestaande code geregeld worden gerefactord. Bij het refactoren kunnen onbedoeld nieuwe bugs worden geïntroduceerd. Met goede unit tests komen die bugs direct aan het licht en kunnen meteen worden verholpen. Unit tests geven daarmee het vertrouwen om bestaande code te kunnen refactoren.

## Pijler 5: Eet exceptions niet op

> I truly wish we didn't even support WHEN OTHERS. 
>
> You should only catch the exceptions you are expecting and can do something about. Let the others propagate out so you can detect them (so you see them)

*Tom Kyte, "asktom.oracle.com"*

Schrijf alleen foutafhandeling voor specifieke fouten die je van te voren al verwacht en die je gepast kunt afhandelen. Dat laatste kan per definitie alleen voor fouten die je verwacht. Laat voor andere gevallen de exception omhoog propageren naar aanroepers zodat zij er niet omheen kunnen dat er iets mis is gegaan - en er dus ook over na moeten denken hoe ze ermee omgaan.

Vermijd het gebruik van generieke foutafhandeling als "catch all" en "exception when others". Zij eten fouten op en verhullen dat er sprake was van een exception: een recept voor obscure bugs.

Alleen in de buitenste lagen van het systeem (scherm, batchjob, publieke API) zijn "catch all"-achtige constructies soms niet te vermijden. Die voorkomen dat een individueel foutgeval het hele programma doet crashen. Generieke foutafhandeling kan dan worden toegepast zodat jouw team en jij op de hoogte worden gesteld van de "bug", mits er aan logging wordt gedaan.

## Pijler 6: Eis collegiale review

> It's not at all important to get it right the first time. It's vitally important to get it right the last time

*Andrew Hunt and David Thomas, "The Pragmatic Programmer"*

> Om te leren van fouten moet je eerst weten dat je fouten maakt

*Philo van Alexandrië*

Laat code die je hebt geschreven altijd reviewen door een collega. Vier ogen zien meer dan twee, twee hersens zijn slimmer dan één. Bovendien kan het een stuk gemakkelijker zijn om problemen te vinden in de code van iemand anders, dan tijdens het schrijven van je eigen code. Een reviewer bekijkt de code vanuit zijn eigen kennis en ervaring en zal daardoor mogelijk problemen detecteren waar de auteur zelf niet aan dacht.

Mensen leveren beter werk wanneer ze weten dat het door anderen wordt gereviewd. Een programmeur die weet dat de geschreven code niet veel later wordt gereviewed, zal een elegant stuk code willen schrijven. Het is leuk om trots te zijn bij het tonen van de code aan de reviewer.

Hoewel code review als primaire doel heeft om de kwaliteit van het stuk code dat onder handen is te verhogen, heeft review ook andere bijkomende voordelen. Als leden van een ontwikkelteam elkaars werk reviewen, zullen zij beter op de hoogte zijn van de veranderingen in de systemen. Door het kijken naar de code van anderen kan een ontwikkelaar veel leren. Het gaat niet alleen om nieuwe oplossingen, maar ook handigheden die anderen hebben ontdekt of ontwikkeld. Onderlinge kennisdeling en controle draagt bij aan een gedeelde verantwoordelijkheid en een goede samenwerking binnen het team. De programmeur die code schrijft is niet eigenaar van de code, het team is eigenaar. Elk teamlid moet zich verantwoordelijk voelen voor de kwaliteit van alle code uit het team.

Reviewen is niet slechts een taak achteraf, als de code al geschreven is. Hoewel de review achteraf het 'formele' reviewmoment is, moet ook vooraf en tijdens de programmeertaak worden gereviewed. Vooraf, om te toetsen wat jouw collega van je oplossingsidee vindt. Tijdens, om te toetsen of jouw collega ook denkt dat je code de juiste kant op gaat. Doe de reviewer en jezelf een plezier en confronteer de reviewer niet met code waarvan de reviewer denkt "o jee wat onhandig, dit had beter helemaal anders opgezet kunnen worden, had hij/zij maar even overlegd".

Peer programming, waarbij programmeur en reviewer samen tegelijk de code schrijven achter één computer, is de hoogste vorm van samenwerking en review.

Er zijn een aantal aandachtspunten voor het uitvoeren van code reviews.

* Het belangrijkst is te kijken naar de opzet van de code. Richt je daarna pas op de "hygiëne"-aspecten (als bijv. naamgevingsconventies).

* Kies een reviewer die genoeg expertise heeft om kritisch naar jouw code te kijken

* Zorg dat de review wordt gezien als een positieve kans om van elkaar te leren en niet alleen als een (verplicht) controlemechanisme.

* Doe liefst een face-to-face overdracht van de code naar de reviewer. Blijf kritisch als reviewer.

* Baseer de review niet op persoonlijke voorkeuren. Belangrijk is om te kijken of het programma bijdraagt aan het juiste resultaat, voldoet aan de geldende standaarden en richtlijnen en aansluit bij de architectuur.

* Kijk niet alleen naar wat beter kan, maar zeker ook naar wat goed is.

* Zorg dat het uitvoeren van code review gedragen wordt door het hele team en dat alle teamleden in het reviewproces participeren.

## Pijler 7: Meet de kwaliteit van de code

> Computer Says No

*David Walliams (Carol Beer), "Little Britain"*

> Leave the campground cleaner than you found it

*Boyscout Rule*

Veel kwaliteitsaspecten van code kunnen automatisch worden gemeten, door tools als SonarQube, PyLint, TSLint.

Bijvoorbeeld:

* Teveel regels code binnen een code-eenheid

* Teveel nesting van if-statements

* Gedupliceerde code

* Veelgemaakte programmeerfouten in de betreffende taal

* "Code smells" - code die een grote kans heeft een bug te bevatten

* Ontbreken van unittests, of verlaging van de coverage door unit tests sinds de vorige run

Dergelijke tools zijn in staat om het verschil tussen runs te rapporteren. Zo kan bijvoorbeeld worden gehandhaafd dat code die al technical debt bevat, bij een volgende commit niet nog slechter wordt.

Gebruik dergelijke tools tijdens coderen en reviewen en werk de gerapporteerde issues weg. Pas de boyscout rule toe; werk ook eens issues weg die eerder door anderen zijn veroorzaakt.

## Pijler 8: Houd het vak in leven

> Je kan een mens niets leren; je kan hem alleen helpen het zelf te ontdekken in zichzelf

*Galileo Galilei*

> De beste manier om iets te leren is er les in te geven

*Seneca*

Het verbeteren van de kwaliteit van de code begint bij een goede opleiding maar vooral bij voortdurend leren. Er zijn veel mogelijkheden om te leren en je vaardigheden te verbeteren.

* Sta stil bij reviews van jouw eigen code. Mogelijk ontdek je bepaalde patterns die je in de toekomst beter kan vermijden.

* Documenteer je ontwerpbeslissingen met hun rationale (liefst bij de code zelf). Dit helpt om je keuzes achteraf te beoordelen.

* Refactor code waar je niet blij mee bent en probeer het te verbeteren.

* Probeer verschillende soorten aanpak.

* Lees boeken en artikelen over software design patterns.

* Ontwikkel een gewoonte voor het schrijven van code van goede kwaliteit. Vermijd "quick and dirty", want dat leidt tot slechte gewoontes.

* Probeer niet alle code te tunen, alleen indien het nodig is.

* Vermijd te weinig, maar ook te veel commentaar te schrijven. 

* Begeleid collega’s met minder ervaring.

* Draag kennis over naar anderen. Dit is een goede manier om zelf te leren.

* Bezoek conferenties, congressen en seminars. Ze wakkeren de passie aan. Ze vergroten een motivatie om te willen blijven leren, en geven ook een richting op basis van de laatste ontwikkelingen. 

* Bezoek en/of neem deel aan communities op software vakmanschap gebied.

* Leer verschillende tools, talen, technologieën. Daardoor verbeter je je kennis en begrip van softwareontwikkeling.

* Vervul (af en toe) een andere rol. Een kijk vanuit een ander perspectief of een ander aandachtsgebied helpt om nieuwe vaardigheden te leren.

* "Beter goed gejat dan slecht bedacht"; vind het wiel niet zelf uit maar laat je inspireren door bestaande code.

## Toegift

Een Nederlands stuk over codekwaliteit zou niet af zijn, als het niet werd afgesloten met een quote van Edsger Dijkstra, de eerste programmeur van Nederland en de enige Nederlandse winnaar van de Turing Award, de Nobelprijs voor de informatica.

> We shall do a much better programming job, provided that we approach the task with a full appreciation of its tremendous difficulty, provided that we stick to modest and elegant programming languages, provided that we respect the intrinsic limitations of the human mind and approach the task as Very Humble Programmers

*Edgser Dijkstra, "The Humble Programmer"*
