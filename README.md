# Graphe des témoignages

Prototype de plateforme pour rassembler les témoignages et preuves de violences policières lors des mobilisations lycéennes et gilets jaunes depuis le 17 septembre 2026, et les regrouper par nature afin de préparer des actions collectives.

Facon https://www.mediapart.fr/studio/panoramique/allo-place-beauvau-cest-pour-un-bilan en 2019 mais automatise

> **Toutes les données du prototype sont fictives.** Aucun témoignage réel n'est stocké dans ce dépôt.

## Fonctionnalités

- **Graphe de connaissances** (D3.js) : chaque témoignage est relié à son type de violence, à l'arme, à la ville et à la journée de manifestation. Les témoignages se regroupent en clusters par type (LBD, grenades, matraques, gaz, nasses, interpellations, gardes à vue de mineurs, insultes).
- **Dossier de cluster** : cas vérifiés, gravité, certificats médicaux, répartition par ville, journée et profil, et indication de la solidité du dossier pour une action collective.
- **Interrogation du graphe** : une requête comme « LBD lycéens Paris » isole le sous-graphe correspondant.
- **Ajout d'un témoignage** : extraction des entités par mots-clés et rattachement au cluster.

## Lancer le prototype

Ouvrir `index.html` dans un navigateur. Aucune installation n'est nécessaire (D3 et les polices sont chargés depuis un CDN).

Pour le publier avec GitHub Pages : *Settings → Pages → Deploy from a branch → `main` / root*.

## Prochaines étapes

1. Extraction des entités et synthèse des clusters par un modèle de langage (approche GraphRAG).
2. Base de données sécurisée, conforme au RGPD (données de santé, mineurs), avec consentement et floutage.
3. Conservation des preuves : fichiers originaux, métadonnées et empreinte (hash) dès le dépôt.
4. Circuit de vérification (signalé → vérifié → documenté) en partenariat avec des associations habilitées.
5. Vue carte géographique.

## Points de vigilance

- Ne pas publier d'éléments permettant d'identifier des agents dans le but de leur nuire (art. 223-1-1 du Code pénal).
- Protéger l'identité des manifestants, en particulier des mineurs.
