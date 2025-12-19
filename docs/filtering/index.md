---
title: "Geavgeavanceerde filtering"
---

# {{ config.site_name }}

Geavgeavanceerde filtering
---

Met geavanceerde filters kun je in MapGallery objecten op de kaart weergeven op basis van specifieke eigenschappen. Door gebruik te maken van operators zoals AND (`&&`), OR (`||`) en vergelijkingsoperatoren zoals `==`, `<`, `>=`, kun je heel gericht bepalen welke objecten zichtbaar zijn en op welke manier. Op deze pagina leggen we uit hoe deze operators werken, met voorbeelden van hoe je filters kunt combineren om precies de data te tonen die je nodig hebt.

### Operators
Hieronder een overzicht van de verschilende operators:

| Operator | Betekenis |
|----------|-----------|
| `&&`     | Alle voorwaarden moeten waar zijn (AND) |
| `||`     | Minstens één voorwaarde moet waar zijn (OR) |
| `==`     | Gelijk aan |
| `<`      | Kleiner dan |
| `<=`     | Kleiner dan of gelijk aan |
| `>`      | Groter dan |
| `>=`     | Groter dan of gelijk aan |


### AND
```json
{
  "name": "",
  "rules": [
    {
      "name": "Bestaande vuurtorens",
      "filter": [
        "&&",
        ["<", "jaar_van_ingebruikstelling", 1960],
        ["==", "type", "vuurtoren"]
      ],
      "symbolizers": [
        {
          "kind": "Mark",
          "color": "#58a1c8",
          "radius": 7,
          "strokeColor": "gray",
          "strokeWidth": 2,
          "strokeOpacity": 1,
          "wellKnownName": "circle"
        }
      ]
    }
  ]
}
```
Door gebruikt te maken van twee ampersand symbolen (`&&`) moeten objecten aan twee voorwaarden voldoen (AND-operator). In dit geval moeten de objecten vóór 1960 in gebruik zijn genomen en moeten de object van het type "vuurtoren" zijn. Als ze hier niet aanvoldoen, worden ze niet zichtbaar op de kaart.

### OR
```json
{
  "name": "",
  "rules": [
    {
      "name": "PDOK - Molens",
      "filter": [
        "||",
        ["==", "HFDFUNCTIE", "koren-/industriemolen"],
        ["==", "HFDFUNCTIE", "koren-/zaagmolen"],
        ["==", "HFDFUNCTIE", "korenmolen"]
      ],
      "symbolizers": [
        {
          "kind": "Mark",
          "color": "#952bd8",
          "radius": 7,
          "strokeColor": "gray",
          "strokeWidth": 2,
          "strokeOpacity": 1,
          "wellKnownName": "circle"
        }
      ]
    }
  ]
}
```
    Door gebruik te maken van twee verticale strepen (`||`) hoeft een object maar aan één van de voorwaarden te voldoen (OR-operator). In dit geval wordt een object zichtbaar op de kaart als de HFDFUNCTIE koren-/industriemolen, koren-/zaagmolen of korenmolen is. Als geen van deze voorwaarden klopt, wordt het object niet weergegeven.

### AND/OR
```json
{
  "name": "",
  "rules": [
    {
      "name": "Autosnelwegen 1900-1970",
      "filter": [
        "&&",
        [">=", "opening", 1900],
        ["<=", "opening", 1970],
        ["||",
          ["==", "awegnummer", "A1"],
          ["==", "awegnummer", "A15"]
        ]
      ],
      "symbolizers": [
        {
          "kind": "Line",
          "color": "#319ed9",
          "width": 5,
          "opacity": 1
        }
      ]
    }
  ]
}
```
Door gebruik te maken van de AND-operator (`&&`) en de OR-operator (`||`) moet een object aan alle voorwaarden van de AND-lijst voldoen, en één van de voorwaarden van de OR-lijst kan voldoen. In dit geval wordt een autosnelweg zichtbaar op de kaart als deze tussen 1900 en 1970 is geopend én het nummer A1 of A15 heeft. Als de snelweg niet aan beide voorwaarden voldoet, wordt het object niet weergegeven.

### Categorieën
```json
{
  "name": "Nederland - Snelwegen per regio",
  "rules": [
    {
      "name": "Noord",
      "filter": [
        "||",
        ["==", "awegnummer", "A7"],
        ["==", "awegnummer", "A28"],
        ["==", "awegnummer", "A31"]
      ],
      "symbolizers": [
        {"kind": "Line", "color": "#3498db", "width": 4, "opacity": 1}
      ]
    },
    {
      "name": "West",
      "filter": [
        "||",
        ["==", "awegnummer", "A1"],
        ["==", "awegnummer", "A2"],
        ["==", "awegnummer", "A4"],
        ["==", "awegnummer", "A5"],
        ["==", "awegnummer", "A6"],
        ["==", "awegnummer", "A8"],
        ["==", "awegnummer", "A9"]
      ],
      "symbolizers": [
        {"kind": "Line", "color": "#2ecc71", "width": 4, "opacity": 1}
      ]
    },
    {
      "name": "Oost",
      "filter": [
        "||",
        ["==", "awegnummer", "A12"],
        ["==", "awegnummer", "A18"],
        ["==", "awegnummer", "A35"],
        ["==", "awegnummer", "A37"],
        ["==", "awegnummer", "A50"]
      ],
      "symbolizers": [
        {"kind": "Line", "color": "#f1c40f", "width": 4, "opacity": 1}
      ]
    },
    {
      "name": "Zuid",
      "filter": [
        "||",
        ["==", "awegnummer", "A16"],
        ["==", "awegnummer", "A27"],
        ["==", "awegnummer", "A58"],
        ["==", "awegnummer", "A59"],
        ["==", "awegnummer", "A67"],
        ["==", "awegnummer", "A73"],
        ["==", "awegnummer", "A76"]
      ],
      "symbolizers": [
        {"kind": "Line", "color": "#e74c3c", "width": 4, "opacity": 1}
      ]
    }
  ]
}
```
Door gebruik te maken van de OR-operator (`||`) binnen elke regel wordt een autosnelweg alleen aan de regio gekoppeld waarvoor zijn nummer is opgegeven. In dit geval wordt een autosnelweg zichtbaar op de kaart in de kleur van de regio waartoe hij behoort, bijvoorbeeld Noord, West, Oost of Zuid. Als het nummer van de snelweg niet voorkomt in de lijst van die regio, wordt het object niet weergegeven.