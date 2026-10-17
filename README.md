# Graphe des témoignages

Prototype de plateforme pour rassembler les témoignages et preuves de violences policières lors des mobilisations lycéennes et gilets jaunes depuis le 17 septembre 2026, et les regrouper par nature afin de préparer des actions collectives.

Facon https://www.mediapart.fr/studio/panoramique/allo-place-beauvau-cest-pour-un-bilan en 2019 mais automatise

> **Toutes les données du prototype sont fictives.** Aucun témoignage réel n'est stocké dans ce dépôt.

## Fonctionnalités

- **Graphe de connaissances** (D3.js) : chaque témoignage est relié à son type de violence, à l'arme, à la ville et à la journée de manifestation. Les témoignages se regroupent en clusters par type (LBD, grenades, matraques, gaz, nasses, interpellations, gardes à vue de mineurs, insultes).
- **Dossier de cluster** : cas vérifiés, gravité, certificats médicaux, répartition par ville, journée et profil, et indication de la solidité du dossier pour une action collective.
- **Interrogation du graphe** : une requête comme « LBD lycéens Paris » isole le sous-graphe correspondant.
- **Ajout d'un témoignage** : extraction des entités par mots-clés et rattachement au cluster.

## Lancer le site

Ouvrir `index.html` dans un navigateur (ou `python -m http.server`). Aucune ressource tierce n'est chargée : D3 est servi depuis `vendor/`, sans police Google.

Le site est publié avec GitHub Pages (*Settings → Pages → Deploy from a branch → `main` / root*). `index_v1.html` et `index_v2.html` sont les prototypes d'origine.

## Recueil des témoignages

Le site ne stocke rien. Les témoignages sont déposés via un formulaire CryptPad chiffré de bout en bout.

1. Créer le formulaire sur https://cryptpad.fr (compte de l'équipe, pas un compte personnel).
2. Copier le **lien de participation** (jamais le lien d'édition ou d'administration) dans `FORM_URL` dans `index.html`.
3. Tant que `FORM_URL` est vide, les boutons affichent « Formulaire bientôt disponible ».

## Prochaines étapes

1. Extraction des entités et synthèse des clusters par un modèle de langage (approche GraphRAG).
2. Base de données sécurisée, conforme au RGPD (données de santé, mineurs), avec consentement et floutage.
3. Conservation des preuves : fichiers originaux, métadonnées et empreinte (hash) dès le dépôt.
4. Circuit de vérification (signalé → vérifié → documenté) en partenariat avec des associations habilitées.
5. Vue carte géographique.

## Points de vigilance

- Ne pas publier d'éléments permettant d'identifier des agents dans le but de leur nuire (art. 223-1-1 du Code pénal).
- Protéger l'identité des manifestants, en particulier des mineurs.
