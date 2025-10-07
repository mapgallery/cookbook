---
title: "Vlakken"
---

# {{ config.site_name }}

Vlakken
---
Voor de handleiding over de styling van punten is gebruik gemaakt van de [dataset suizen](https://nationaalgeoregister.nl/geonetwork/srv/dut/catalog.search#/metadata/35f04ee9-6499-4fef-837e-12b81b6374b5). Deze is te vinden in o.a. het nationaal georegister van PDOK.
Aan de hand van deze dataset zullen enkele voorbeelden gegeven worden van de stylingsmogelijkheden. Alle voorbeelden zijn onderdeel van de “genereer style” functie in MapGallery.

### Simpel vlak
```
{
  "name": "",
  "rules": [
    {
      "name": "Sluizen",
      "filter": ["==", "$type", "Polygon"],
      "symbolizers": [
        {
          "kind": "Fill",
          "color": "#47bea3",
          "opacity": 1,
          "outlineColor": "black",
          "outlineWidth": 2,
          "outlineOpacity": 1
        }
      ]
    }
  ]
}
```
![title](foto_simpel_vlak.png)

De code hierboven is het resultaat van het genereren van een eenvoudige vlak weergave in MapGallery. Binnen __rules__ zijn de stylingsregels beschreven. In de __filter__ is gekozen voor alle geometrieën van het type vlak.

- Het type symbool is __fill__, ofwel een vlak op de kaart. 
- De __kleur__ "#47bea3" in hex notatie, de code begint met # gevolgd door 6 tekens, bestaande uit drie paren, die respectievelijk de intensiteit van rood, groen en blauw (RGB) weergeven. Maar de basiskleuren worden ook herkend zoals red, green, indigo ect. 
-	De __opacity__ bepaald de transparantie van het vlak. 
-	De __outlineColor__, ofwel de omlijning is zwart. Hierbij kan je gebruik maken van de zelfde kleur opties als bij de kleur van de punt. 
-	De __outlineWidth__ bepaald de dikte van de omlijning.
-	De __outlineOpacity__ bepaald de transparantie van de omlijning.
 
