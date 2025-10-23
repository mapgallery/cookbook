---
title: "FAQ"
---

# {{ config.site_name }}

FAQ
---
Op deze pagina worden de Frequently Asked Questions (FAQ) bedantwoord: 


??? info "Waarom zie ik geen categorieën als ik een stijl genereer in MapGallery?"

    Als er geen velden zichtbaar zijn in het dropdownmenu van “Categorie veld”, controleer dan of in het tabblad “Velden” de optie “Aanpassen van velden” is aangevinkt.


??? info "Waarom werkt mijn Vector Tiles stijl niet?"

    Een Vector Tiles-laag kan meerdere datalagen bevatten binnen één kaartlaag. Daarom moet in de stijl worden aangegeven voor welke specifieke laag de styling bedoeld is. De telling van de lagen begint bij nul. In dit voorbeeld verwijst `[0]` dus naar de eerste laag binnen de Vector Tiles. Als je in MapGallery automatisch een stijl laat genereren, wordt deze informatie automatisch toegevoegd, je hoeft dit dus niet handmatig te doen.  

    ```json
    {
    "rules": [
        {
        "name": "3D pand",
        "symbolizers": [
            {
            "kind": "Fill",
            "color": "#cfc5b8",
            "height": { "args": ["hoogte"], "name": "property" },
            "opacity": 0.7,
            "fillOpacity": 0.62
            }
        ]
        }
    ],
    "metadata": {
        "mapbox:ref": {
        "sources": {},
        "sourceLayerMapping": {
            "pand": [0]
        }
        }
    }
    }
    ```