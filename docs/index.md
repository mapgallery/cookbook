---
title: "Introductie"
---

# {{ config.site_name }}

Het MapGallery GeoStyler kookboek bestaat uit verschillende 'recepten' voor de styling van de kaarten. We hopen dat deze handleiding je helpt om het meeste uit MapGallery te halen. Veel succes met het ontdekken van de wereld van geografische informatie!

Het MapGallery Team

Styling van kaartlagen
---
Bij sommige services, zoals WMS, is de styling van de laag al inbegrepen en ook niet aan te passen.
Bij het gebruik van services waarbij de features apart worden opgehaald, zoals WFS/GEOJSON/REST/TileJSON, is er nog geen style inbegrepen en deze kan naar wens aangepast worden. 
Een style word gedefinieerd aan de hand van een styling format. Er zijn veel verschillende formats in gebruik zoals bijvoorbeeld: SLD, QGIS, Mapbox. MapGallery maakt gebruik van het [GeoStyler](https://geostyler.org/) format. Dit format is gecreëerd om goed leesbaar te zijn en om makkelijk over en weer te kunnen converteren naar de andere bestaande formats. 
Vector features bestaan uit punten, lijnen of polygonen. Deze handleiding zal voor ieder van deze features de stylingsmogelijkheden behandelen, met daarbij voorbeelden van de bijbehorende GeoStyler code.  


Stylen binnen MapGallery
---
Ga naar beheer > kaartlagen en kies een geschikte kaartlaag of voeg er zelf een toe. Als je de kaartlaag selecteerd, zorg dan dat bij het tabje “Velden” het aanpassen van velden is aangevinkt, dit is nodig om geavanceerde styling mogelijk te maken. 
Het stylen zelf gebeurt bij het tabje “Style”. Zorg dat “Style aanpassen” is aangevinkt. 
Hierdoor verschijnt er een veld voor de code die de style definieert, met daarnaast de legenda met de styling van de features. 
De knop “genereer style” is het makkelijkst om een begin te maken wanneer je blanco begint. 
Onder het kopje extra is het ook mogelijk om een bestaande style in SLD of Json formaat te importeren, dan wel je huidige style te exporteren.

### Style genereren

Binnen het genereren van een style zijn er enkele opties:

-   Ten eerste is het belangrijk het juist geometry type van de betreffende kaartlaag te kiezen (punt, lijn, vlak)
-	Bij punten is het mogelijk om te kiezen voor een symbool of afbeelding (via hyperlink).
-	Kies voor “Weergave op categorie” voor het gebruik van meerdere categorieën/symbolen. Kies hierbij het veld dat gebruikt moet worden voor categorisatie.
-	Kies voor “Labels tonen” en het veld wat als label moet dienen voor het gebruik van labels op de kaart. Deze hebben op zichzelf ook weer styling opties. 

### Gebruik van een tekst / code editor

Een style maken kan direct binnen MapGallery, maar het kan handig zijn om te werken met een tekst editor, zoals word of kladblok, zodat je een plek hebt om te experimenteren of om stukken code te bewaren. Een aanrader is het gebruik van een speciale code editor zoals Visual Studio Code, door toepassing van kleur wordt de code beter leesbaar.

### Geostyler Demo 

Handig gereedschap voor het maken van een style is de demo van GeoStyler. Hier kunnen verschillende styling opties verkend worden voor punten, lijnen en polygonen. Bij de code editor aan de rechterkant kan gelijk de bijbehorende code bekeken worden.
