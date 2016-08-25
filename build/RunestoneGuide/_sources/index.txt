=====================
Runestone Guide
=====================



1: Installera python och runestone
::::::::::::::::::::::::::::::::::

Det är lite olika hur runestone installeras beroende på vilket operativsystem vi kör. Lättast ska det vara till Unix och MacOS men det har jag inte testat utan jag kör windows och kommer bara förklara hur man gör till windows.

Här hittar vi mer info om installation och skapande av nytt projekt: http://reputablejournal.com/how-to-make-a-lab-in-three-easy-steps.html#.V73EwSiLSUk

Först och främst måste python vara installerat och då är det någon version av python 3 som gäller (jag kör på 3.5). Det kan vi ladda ner här: https://www.python.org/downloads/

När vi har det ska vi installera runestonepaketet som följer med python genom att i **kommandotolken** gå in i rätt mapp och köra ``pip install runestone``.

Adressen till min '*rätt mapp*' är ``C:\Users\Jonathan\AppData\Local\Programs\Python\Python35-32\Scripts``. Vi måste alltså hitta till var python är installerat och sedan mappen **Scripts**. Här kör vi ``pip install runestone``.

Om det går bra borde det nu finnas en fil i mappen **Scripts** som heter ``runestone.py``. Den kommer vi behöva strax.




2: Skapa nytt projekt
:::::::::::::::::::::

Kör du MacOS eller Unix borde denna länk förklara hur du skapar ett nytt projekt: http://reputablejournal.com/how-to-make-a-lab-in-three-easy-steps.html#.V73EwSiLSUk

För att skapa ett nytt projekt börjar vi med att skapa en ny mapp för projektet någonstans på vår dator. Till denna mapp måste vi nu kopiera in ``runestone.py`` från mappen **Scripts** som vi installerade runestone i.

Nu kan vi skapa ett nytt runestoneprojekt genom att i kommandotolken gå in i den nyskapade mappen och köra ``runestone init``. Då ställs några frågor om inställningar för projektet. Det går bra att använda default-inställningarna genom att bara klicka enter. Vi måste dock välja ett projektnamn och här finns det en viktig sak att tänka på.

**OBS! Man kanske inte kan använda å, ä, ö i projektnamn eller personnamn när man skapar nytt projekt.**

När vi klickat oss igenom alla frågor kommer ett nytt projekt att skapas och vi får de filer vi behöver till vår projektmapp som borde innehålla allt nedan.

::

	_static
	_sources
	_templates
	conf.py
	pavement.py

	runestone.py

* ``_static`` är för exempelvis bilder.
* ``_sources`` är där all kod för projektet ska vara. Det finns en index.rst till att börja med.
* ``_templates`` här finns alla styling för projektet.
* ``conf.py`` innehåller info med bland annat svar på de frågor som ställdes vi projektskapandet.
* ``pavement.py`` används när vi bygger projektet.




3: Redigera och skriva bok
::::::::::::::::::::::::::

All kod för att skapa en bok ska ligga i mappen ``_sources``. Till att börja med finns det en fil ``index.rst`` som innehåller en del exempelkod som kan hjälpa för att sätta igång.

Det går bra att dela upp projektet i flera filer och undermappar för att sedan koppla ihop dem med toctree.

En indexfil som kopplar allt skulle då kunna se ut såhär:

::

	.. toctree::
		:maxdepth: 2

		kap1.rst
		kap2.rst
		kap3/del1.rst
		kap3/del2.rst

Maxdepth bestämmer hur många nivåer av underrubriker som ska synas i innehållsförteckningen.


Det språk som används för att skriva kod är *reStructuredText* (rst) och här är det en viktig sak att komma ihåg. 

**Precis som i python spelar indentering roll.**

För att lära sig skriva böcker med runestone måste man förutom att lära sig rst-syntax även lära sig använda de komponenter som runestone har. Denna länk innehåller en översikt av de tillgängliga komponenter: http://interactivepython.org/runestone/static/overview/overview.html

Det finns även påbörjade dokumentation för författare på http://runestoneinteractive.org/build/html/index.html

Ett annat sätt att lära sig mer om hur man skriver böcker är att kolla på exempelkoden som kommer med i indexfilen när vi skapar ett nytt projekt.




4. Bygga och testa projekt
::::::::::::::::::::::::::

När vi har någon kod som vi vill testa kan vi bygga projektet så att vi får en fin html-version. Använd kommandotolken och gå in i huvudmappen för projektet och kör där kommadot ``runestone build``. Eventuella felmeddelanden eller varningar kommer då upp men förhoppningsvis blir det en *successful build*. Nu har en ny mapp ``build`` skapats i vårt projekt och inuti den hittar vi filen ``index.html`` som kan öppnas i en webbläsare och där ser vi vår bok!