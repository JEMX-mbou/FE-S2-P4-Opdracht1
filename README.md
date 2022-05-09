Onderwijs Online Module: https://mboutrecht.onderwijsonline.nl/elearning/lesson/AN7XEkyb

**Ondertussen weten jullie hoe jullie wat simpele dingen kunnen afhandelen met JavaScript. Zo hebben we elementen leren selecteren en EventListeners ingezet. Maar er is onwijs veel mogelijk met JavaScript. Tegenwoordig worden ook sommige games gebouwd met JavaScript, bijvoorbeeld.**

**Nu is het zo dat er heel veel programmeurs met JavaScript (en andere talen) werken en bepaalde functionaliteiten gaan bundelen en online zetten. Dit noemen we libraries, deze libraries kunnen we importeren in ons project en de code gebruiken die anderen hebben geschreven. Dit scheelt ons erg veel tijd, want we hoeven niet per sé nieuwe technieken te leren en we hoeven ook alle functionaliteiten niet meer te programmeren. We hebben al eens zoiets ingezet om sass te compilen. NPM is ook een goede bron voor dit soort libraries.**

In deze opdracht gaan we aan de slag met zo'n library, en deze library wordt gebruikt om grafieken te tekenen met JavaScript. 

**In te leveren:**
- script.js

# Opdracht A: Organisatie
Als de onderstaande punten niet op te lossen zijn. Ga dan naar de uitleg in de bijlage van deze Onderwijs Online module (onder de opdrachten). 

1. In de FE-S2-P4 folder, run het clone commando op de GitHub repository die is aangemaakt toen je op de link klikte. 
2. Als de Clone methode niet werkt, maak een nieuwe map aan en gebruik de Init methode. 

# Opdracht B: Cijfer Grafiek
**We gaan gebruik maken van Chart.js. Met deze library kunnen we vrij gemakkelijk en snel grafieken tekenen op onze website!**
**Check deze pagina: https://www.chartjs.org/docs/latest/ voor de documentatie over deze library.**

1. We gaan net zoals bij het opzetten van de sass-compiler gebruik maken van NPM. 
  Daarom moet je eerst **het commando ```npm init``` uitvoeren in de opdracht map via de terminal.** 
  En daarna kan je eigenlijk op "enter" blijven drukken tot je "yes" ziet verschijnen. 

2. Als dat is gebeurt moet je het commando ```npm i chart.js --save-dev``` uitvoeren. 
  Hiermee wordt de chart.js library geinstalleerd in de node_modules map. 

3. Op dit moment staat er alleen nog maar een canvas element in het index.html bestand. 
  Nu moet je zorgen dat de juiste JavaScript bestanden worden ingeladen. 
  Zorg dat de onderstaande regels worden toegevoegd aan het einde van het body element in het index.html bestand. 
  
    ![opdr1-1](https://user-images.githubusercontent.com/51715045/167421943-94fd197b-783f-42e9-ac46-d3bacf162b9b.png)

  *Alle stappen die hierna volgen heb ik zelf uit de [documentatie](https://www.chartjs.org/docs/latest/) gehaald of met behulp van StackOverflow opgelost.*

4. Nu wordt het bestand ingeladen, maar gebeurt er eigenlijk nog helemaal niks. 
  Daarvoor moeten we de functionaliteit aanroepen in script.js.
  **Voeg de onderstaande regel toe aan script.js.**
   
    ![opdr1-2](https://user-images.githubusercontent.com/51715045/167422162-e06ae5f2-3dc3-4054-bb4e-2b62725b5c63.png)

5. Het canvas element wordt nu geselecteerd en hier kan de library straks in gaan "tekenen". 
  Wat wij nu moeten doen is de opties van de grafiek gaan definieren. En zorgen dat het in het juiste element verschijnt. 
  **Type het onderstaande voorbeeld over (Het commentaar mag overgeslagen worden dit is voor uitleg).**
  
    ![opdr1-3](https://user-images.githubusercontent.com/51715045/167422182-3f45f887-9fc7-406a-b049-2763c68970a0.png)

6. Nu komen de periodes al wel op de juiste plek te staan, maar is er nog maar 1 enkele lijn te zien waarbij de cijfers (hopelijk) niet kloppen. 
  **Zoek je cijfers op en neem ze over in script.js en zorg dat je het zo neer zet zoals het onderstaande voorbeeld.**
  
    ![opdr1-4](https://user-images.githubusercontent.com/51715045/167422235-a6b73a2c-2fc7-47f8-98bd-a1fe1fb59f3d.png)
  
    *Mocht je niet voor iedere periode een cijfer hebben gekregen voor een vak, dan kan je dus per periode aangeven welk cijfer je hebt gekregen (zie "fundamentals").*

7. Zoals je misschien ziet neemt de y-as de maximale en minimale waardes van de dataset over. 
  Het zou natuurlijk handiger zijn als we een maximale waarde van 10 zouden hebben en een minimale waarde van 0.
  **Type het onderstaande voorbeeld over onder de data. Let goed op de tekens!**
  
    ![opdr1-5](https://user-images.githubusercontent.com/51715045/167422299-d788433b-36eb-4398-a21d-3de14f5f4121.png)

8. Als dit is gelukt ziet je grafiek er als het goed is uit zoals het onderstaande voorbeeld.
  Je kan nu ook individuele vakken "uitzetten" door op de naam bovenin te klikken. 
  
    ![opdr1-6](https://user-images.githubusercontent.com/51715045/167422813-d3ce120b-fb2b-4793-8fc4-67b86a115025.png)


# Opdracht C: Kleuren toevoegen
**Zoals je hierboven ziet is de grafiek wel goed af te lezen, maar zijn de verschillende lijnen maar lastig van elkaar te onderscheiden. 
Ook is het niet helemaal duidelijk waar de grens "onvoldoende" en "voldoende" ligt.**

1. Eerst gaan we de kleuren per vak definieren en dat doen we door een variabele "color" aan te maken. 
  En deze te vullen met een JS object. Hierin kunnen we gemakkelijk per vak een "key" aanmaken en deze vullen met een waarde van een kleur. 
  **Maak een variabele "color" aan en vul deze met kleuren per vak zoals hieronder is weergegeven.**
  
    ![opdr1-7](https://user-images.githubusercontent.com/51715045/167422894-27fe1ca5-c40f-4064-b89a-3ac826d8fc28.png)
    
    *Let op!; Hier worden RGBA waardes gebruikt. De lengte is 8 karakters in plaats van 6. De laatste 2 karakters zijn voor de alpha. Dus kan je kleuren ook nog "doorzichtig" maken. *

2. Deze variabele doet op zichzelf nog helemaal niks. Daarvoor moeten we ze eerst nog toevoegen aan de datasets. 
  **Zorg dat ieder vak de kleur waarde krijgt die je in stap 1 hebt gedefinieerd zoals hieronder is weergegeven.**
  
    ![opdr1-8](https://user-images.githubusercontent.com/51715045/167422937-bf9c5e0f-7f21-4b0d-9ac3-7a8163698896.png)

3. De lijnen hebben nu mooie kleurtjes, maar het is nog niet echt te zien waar nou de grens voldoende-onvoldoende ligt.
  Hiervoor moeten we met JavaScript een rechthoek gaan "tekenen" voordat de grafiek getekend zal worden. 
  Daarom gaan we nu een "plugin" voor Chart.js schrijven. 
  **Type het onderstaande over in het Chart Object onder de options:**
  
    ![opdr1-9](https://user-images.githubusercontent.com/51715045/167422983-a8b9d157-ab6c-41cd-97fc-99d6d5b58028.png)
  
    *Deze functie word door Chart.js aangesproken voordat de grafiek getekend wordt. Op dit moment zijn dingen zoals afmetingen en posities wel al beschikbaar. Deze gaan wij gebruiken om de rechthoek te tekenen. *

4. Eerst moeten we een aantal variabelen gaan declareren die we moeten gebruiken voor de afmetingen en het tekenen van de rechthoek. 
  **Type het onderstaande voorbeeld over in de function uit de vorige stap:**
  
    ![opdr1-10](https://user-images.githubusercontent.com/51715045/167423013-0714ccfa-254b-4f38-83a5-836bb1c2b5dd.png)

5. Met de bovenstaande variabelen kunnen we er nu voor gaan zorgen dat we de afmetingen en de positie kunnen bepalen voor de rechthoek. 
  **Type het onderstaande over:**
    
    ![opdr1-11](https://user-images.githubusercontent.com/51715045/167423042-3b8f9146-c9d4-4b99-ac0f-64240fdad198.png)

6. Nu gaan we de daadwerkelijke rechthoek tekenen. 
  Hiervoor moeten we eerste de state van het canvas opslaan. Daarna de kleur instellen, de rechthoek tekenen en daarna weer de state herstellen. 
  **Type hiervoor het onderstaande over:**
  
    ![opdr1-12](https://user-images.githubusercontent.com/51715045/167423059-bad6ec8e-5815-4418-8410-b96c8ad53bcc.png)

7. Als alles is gelukt ziet je grafiek er nu ongeveer uit zoals het onderstaande voorbeeld:
  De kleuren van de lijnen kunnen eventueel verschillen.
  
    ![opdr1-13](https://user-images.githubusercontent.com/51715045/167423097-4ea76b9a-1bdd-4444-806d-7917e30c3c16.png)


# Extra Opdracht: Absentie toevoegen (Medium)
**Met Chart.js hebben we nu puur en alleen lijnen toegevoegd, maar het is ook mogelijk om samengestelde grafieken te maken. Dus bijvoorbeeld een staafdiagram met een lijngrafiek. **

1. Zoek de procenten van je absentie op en leg ze vast per periode. 
2. Zorg ervoor dat er een nieuwe dataset voor de absentie per periode wordt toegevoegd.
3. Nu is het de bedoeling dat de absentie wordt weergegeven als het type "bar" en de cijfers nog steeds als "line".
  https://www.chartjs.org/docs/latest/samples/other-charts/combo-bar-line.html
4. De absentie maakt natuurlijk gebruik van andere waardes dus er zal ook nog een andere y-as gedefinieerd moeten worden.
  https://www.chartjs.org/docs/latest/samples/line/multi-axis.html
