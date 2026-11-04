[# Départs Naolib — tram 3](https://cyprienv.github.io/Marie-tram/)

# Départs Naolib — tram 3

Le panneau affiche les prochains départs du tram 3 à Plaisance vers Neustrie,
puis à Bretagne vers Marcel Paul. `fetch_tan.py` génère `horaires.json` avec
les horaires théoriques GTFS et les données GTFS-RT lorsqu'elles sont
disponibles ; le panneau lit également le flux temps réel directement et
conserve les horaires théoriques en secours.

La ligne, l'arrêt et la destination se configurent dans `CARTES` en haut de
`fetch_tan.py`. Le script signale explicitement si l'arrêt ou la direction ne
correspond plus aux données GTFS.

Le workflow GitHub Actions `update_transit.yaml` régénère `horaires.json`
toutes les 5 minutes (un seul run à la fois, avec nouvelle tentative de push
en cas de conflit).
