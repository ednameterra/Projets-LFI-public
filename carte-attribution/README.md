# Carte d'attribution des territoires — 3ᵉ circonscription de l'Aude

Carte interactive pour répartir les territoires d'action entre les groupements
LFI de la 3ᵉ circonscription de l'Aude, avec agenda des actions.

**Adresse officielle : https://ednameterra.github.io/Projets-LFI-public/carte-attribution/**

> Le dépôt a été renommé (`carte-circo3-aude` → `Projets-LFI-public`) :
> mettez à jour vos favoris avec l'adresse officielle ci-dessus.

Fonctionne sur navigateur (ordinateur et téléphone), sans installation ni
compte. Page unique autonome : Leaflet, contours communaux via geo.api.gouv.fr,
fond de carte OpenStreetMap.

## Règles d'utilisation

> **Chacun modifie sa propre copie ; les données voyagent uniquement par liens envoyés au coordinateur, qui détient la version de référence.**

### 1. L'adresse officielle
- Une seule adresse (ci-dessus) — mettez-la en favori.
- Ne partagez jamais l'adresse copiée depuis la barre d'adresse après avoir ouvert un lien reçu : utilisez toujours le bouton **« Partager par lien »**.
- Les liens de partage sont **compressés** (sans aucune perte de données) : environ deux fois plus courts qu'avant. Les anciens liens restent compatibles.

### 2. Où sont vos données
- Vos attributions et votre agenda sont enregistrés **dans votre navigateur, sur votre appareil**. Recharger la page ou fermer l'onglet ne perd rien ; changer d'appareil, de navigateur ou d'ordinateur = copie vide.
- Pour passer d'un appareil à l'autre : « Partager par lien » vers vous-même, ou « Exporter (JSON) » puis « Importer ».

### 3. Qui envoie quoi à qui
- Les contributeurs (GA) envoient leurs liens **uniquement au coordinateur** — pas entre eux, pour éviter les versions divergentes.
- Un lien est un **instantané** : après chaque nouvelle modification, **regénérez un lien** et renvoyez-le. Un ancien lien ne contiendra jamais vos changements récents.

### 4. Côté coordinateur
- Ouvrir chaque lien reçu → confirmer la fusion → lire le récapitulatif (« Fusion effectuée : +X communes, +Y groupements, +Z actions »).
- En cas de conflit (commune déjà attribuée chez vous), **votre version prime** et le conflit est compté ; tranchez si un contributeur conteste.
- Après intégration, votre carte devient la référence : regénérez votre propre lien et renvoyez-le à ceux qui en ont besoin.

### 5. Les groupements
- **⏸ désactive** un groupement (GA inactif) : son territoire redevient libre, ses données sont conservées.
- **✕ supprime** définitivement — seulement pour une vraie erreur de création.
- **Ces deux statuts se propagent par les liens** : le destinataire verra le GA retiré ou désactivé chez lui, et un rechargement ne le ré-ajoutera pas.
- Pour rétablir un GA : bouton « Ajouter » dans la liste « GA d'Action Populaire » (panneau de gauche, section repliable).
- Ne pas renommer les 12 GA officiels d'Action Populaire : leurs noms servent à reconnaître les données d'un lien à l'autre.
- Une commune = un seul groupement actif, toujours (anti-doublon automatique).

### 6. En cas de doute
- Un message en haut de la carte explique toujours ce qui vient de se passer (fusion effectuée, rien de nouveau, lien illisible, fusion annulée).
- Si un lien « ne remonte rien » : vérifiez que l'expéditeur l'a **regénéré après** ses modifications.
- **« Tout effacer »** est irréversible — faites d'abord un « Exporter (JSON) ».

## Caractéristiques techniques

- Découpage : 292 communes (291 entières + la partie de Carcassonne en 3ᵉ circo : quartiers Saint-Jacques, Le Viguier, Grèzes, Salvaza) ; Limoux découpée en 3 secteurs, un par GA limouxin.
- Liens de partage : format binaire compact (`#b=`), compatible avec les anciens formats (`#d=`, `#z=`, `#c=`).
- Mode abstention : le bouton « Abstention » (panneau de gauche) colore chaque commune selon son taux d'abstention aux législatives 2022 et 2024, T1 et T2 (sélecteur à quatre tours, classes adaptées à chaque année, légende dynamique affichée sur la carte). Données officielles du Ministère de l'Intérieur (résultats par commune agrégés depuis les bureaux de vote de la 3ᵈ circo, data.gouv.fr), embarquées dans la page — aucun fetch supplémentaire.
- Score LFI : bouton « Colorer la carte · score LFI 2022-2024 » (onglet « Abstention & score LFI ») colore chaque commune selon le score du candidat insoumis·e aux législatives — J. Adda--Netter (NUP) en 2022, P. Andrieu (UG/NFP) en 2024 — en % des suffrages exprimés, classes < 20 / 20–30 / 30–40 / 40–50 / ≥ 50 %, sélecteur à quatre tours partagé avec l'abstention. Données officielles du Ministère de l'Intérieur (résultats définitifs, associés par commune depuis les bureaux de vote de la 3ᵈ circo, data.gouv.fr), embarquées dans la page.
- Résultats par parti : en mode votes, un sélecteur (« LFI · NUPES 2022 / NFP 2024 », RN, Renaissance, LR (uniquement en 2024), UDI, Divers gauche (2022), Reconquête, Réserves de voix LFI) colore chaque commune selon le score du parti aux 4 tours (J. Adda--Netter/J. Rancoule en 2022, P. Andrieu/J. Rancoule en 2024). Les partis sans candidat séparé (PS, PCF, EELV : accords NUPES 2022 / NFP 2024) sont intégrés au score insoumis·e ; les éliminés au 1ᵉʳ tour apparaissent en gris. « Réserves de voix » = delta T2−T1 du score insoumis·e (recul en rouge, gain en violet).
- Encadrés à deux modes : le panneau « Abstention / votes par territoire » et les infos au survol commutent automatiquement entre abstention (4 tours, pondérées par inscrits) et votes (4 tours du parti affiché, pondérées par exprimés ; en mode réserves : delta 2022 et delta 2024). Les partis sans candidat séparé (PS, PCF, EELV : accords NUPES 2022 / NFP 2024) sont intégrés au score insoumis·e ; les éliminés au 1ᵉʳ tour apparaissent en gris. Limoux sectorisée est comptée intégralement dans chaque groupement détenant un de ses secteurs (note affichée).
- Bandeau repliable : « Groupements » (en tête de bandeau), « Abstention par territoire », « Répartition », « Agenda des actions » et « Sauvegarde » se plient/déplient (chevron) ; la recherche de commune reste toujours visible.
- Surbrillance : au survol ou à la sélection d'un groupement, son territoire est cerclé d'un liseré double uniforme (halo charbon + trait crème), visible sur tous les fonds et dans tous les modes (attribution, abstention, votes) — même contour partout, pas de mélange noir/blanc. « Territoires libres » ne surligne rien.
- Membres actifs : chaque GA du panneau affiche son nombre de membres actifs et le ratio « habitants par membre actif » (population des territoires attribués ÷ membres actifs) ; le bandeau de statistiques affiche le total et le ratio global. Valeurs relevées en novembre 2025 sur les pages publiques des groupes sur actionpopulaire.fr, puis modifiables d'un clic sur la ligne « N actif·es » du panneau (la valeur modifiée reste personnelle, comme le reste des attributions).
- Données stockées localement (localStorage), aucune donnée transmise à un serveur.
