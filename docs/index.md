---
title: "Introductie"
---

# {{ config.site_name }}

Het MapGallery GeoStyler Kookboek bevat diverse ‘recepten’ voor het stylen van kaartlagen binnen MapGallery. Deze handleiding is bedoeld om gebruikers te ondersteunen bij het optimaal benutten van de mogelijkheden binnen het platform. Veel succes met het ontdekken van de wereld van geografische informatie!

– Het MapGallery Team

Styling van kaartlagen
---

Bij bepaalde services, zoals WMS, is de stijl van de kaartlaag vooraf ingesteld en niet aanpasbaar. Bij gebruik van services waarbij de features afzonderlijk worden opgehaald, zoals WFS, GeoJSON, REST of TileJSON is standaard geen stijl aanwezig, waardoor een eigen stijl kan worden toegepast.

De stijl wordt vastgelegd in een zogenaamd styling-formaat. Er bestaan verschillende formaten, zoals SLD, QGIS en Mapbox. MapGallery maakt gebruik van het [GeoStyler](https://geostyler.org/) formaat, dat is ontworpen voor leesbaarheid en eenvoudige conversie naar andere stijlvormen. Vectorfeatures bestaan uit punten, lijnen of vlakken. Deze handleiding behandelt per featuretype de stylingsmogelijkheden, met voorbeelden.


Stylen binnen MapGallery
---
- Ga naar Beheer → Kaartlagen en selecteer een bestaande laag of voeg een nieuwe toe.
- In het tabblad "Velden", moet de optie "Velden aanpassen" worden ingeschakeld om geavanceerde styling toe te staan.
- Open het tabblad "Style" en vink "Style aanpassen" aan.
- Er verschijnt een veld voor het invoeren van de code, met daarnaast een legenda waarin de toegepaste stijl zichtbaar is.
- Gebruik de knop "Genereer style" om een basisstijl aan te maken.
- Onder het kopje "Extra" is het mogelijk om een bestaande stijl in SLD- of JSON-formaat te importeren of de huidige stijl te exporteren.

### Style genereren

Bij het genereren van een stijl zijn de volgende keuzes van belang:

- Selecteer het juiste geometrie-type van de kaartlaag: punt, lijn of vlak.
    - Voor punten kan worden gekozen tussen een symbool of een afbeelding via een hyperlink.
- Bij keuze voor "Weergave op categorie" kan een veld worden geselecteerd waarop de symbolisatie wordt gebaseerd.
- Het is mogelijk om labels weer te geven. Hierbij wordt een veld gekozen dat als label dient, ook labels kunnen afzonderlijk gestyled worden.

### GeoStyler structuur
GeoStyler gebruikt JSON om vast te leggen hoe geografische objecten (punten, lijnen of vlakken) op een kaart worden weergegeven. 

- `name`: Hiermee begint een GeoStyler-stijl. Dit is een optioneel onderdeel en dient als titel in de legenda.
- `rules`: Dit is het belangrijkste onderdeel van de stijl. De regels bepalen wanneer en hoe objecten worden gevisualiseerd. Binnen een regel kunnen drie onderdelen voorkomen:
    - `name`: De naam van de specifieke regel, bijvoorbeeld `"Watermolen"`. Zo blijven de verschillende categorieën herkenbaar in de legenda.
    - `filter`: Hiermee wordt bepaald op welke objecten in de dataset de regel van toepassing is. Met `["==", "$type", "Point"]` worden bijvoorbeeld alleen de punten gestyled. Filters kunnen ook gebaseerd zijn op attribuutwaarden, zoals `["==", "CATEGORIE", "windmolen"]`. In dat geval geldt de stijl alleen voor objecten waarvan het veld `CATEGORIE` de waarde *windmolen* heeft.
    - `symbolizers`: Dit is een lijst van stijlelementen die bepaalt hoe het object eruitziet, bijvoorbeeld de kleur, grootte, omlijning of vorm. Afhankelijk van het type symbool (`"Mark"`, `"Line"`, `"Fill"` of `"Text"`) kunnen hier verschillende eigenschappen worden ingesteld.



### Gebruik van een tekst/code editor

Het is mogelijk om stijlen direct binnen MapGallery op te stellen, maar voor meer overzicht of het bewaren van codefragmenten kan gebruik worden gemaakt van een teksteditor zoals Kladblok of Word. Een betere optie is een gespecialiseerde code-editor, zoals Visual Studio Code. Dankzij kleurcodering wordt de stijlcode beter leesbaar en overzichtelijker.

### Geostyler demo 

Een handig hulpmiddel voor het maken van een style is de [demo van GeoStyler](https://demo.geostyler.org/). Hier kunnen verschillende styling opties verkend worden voor punten, lijnen en vlakken. In de code-editor aan de rechterkant is direct de bijbehorende code te bekijken en de toegepaste stijl op de kaart te zien. Dit maakt het eenvoudig om te experimenteren met stijlen en direct het effect van aanpassingen te zien. Bovendien kunnen bestaande stijlen, zoals SLD, eenvoudig worden omgezet naar het GeoStyler-formaat.

### Geostyler Documentatie
Naast de GeoStyler-demo kan ook de [documentatie](https://geostyler.github.io/geostyler-style/docs/master/index.html) van GeoStyler van pas komen. Daar worden de verschillende mogelijkheden van GeoStyler uitgebreid toegelicht voor meer verdieping. 
