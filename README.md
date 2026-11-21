[README.md](https://github.com/user-attachments/files/35222095/README.md)
# 🌳 La forêt des projets

**Suivre un projet de recherche dans la durée, d'un seul coup d'œil.**

La forêt des projets est un outil de visualisation imaginé pour la plateforme **Neuraxess** (neuroimagerie fonctionnelle et neuromodulation, CHU de Besançon / Université de Franche-Comté). Chaque projet y devient un arbre, et tous les projets de la plateforme forment une forêt.

Tout tient dans **un seul fichier HTML**, sans logiciel à installer, sans serveur et sans compte. On l'ouvre dans un navigateur, on le remplit, on l'enregistre.

\---

## Pourquoi cet outil ?

Un projet de recherche vit souvent dix ans ou plus. Il commence par une idée, quelques références et un premier financement. Puis viennent les inclusions, une thèse, des stagiaires, des recrutements, des publications, des communications, des projets dérivés…

Au fil des années, ces informations se dispersent entre des tableaux, des rapports, des CV et des mails. Au moment de faire un bilan, de répondre à un appel à projets ou de présenter la plateforme, il faut tout reconstituer.

La forêt des projets garde cette mémoire et la rend lisible : on voit immédiatement quand un projet a été le plus actif, ce qu'il a fait naître et ce qu'il a produit.

\---

## La métaphore

|Élément de l'arbre|Ce qu'il représente|
|-|-|
|Racines|Les références qui ont nourri le projet, regroupées par thème|
|Tronc|La frise du temps du projet|
|Cernes du tronc|Les jalons ; les **étapes clés** sont nommées dans la colonne de droite|
|Branches|Les projets dérivés, qui peuvent eux-mêmes se ramifier|
|Feuillage en bout de branche|La fin d'un projet dérivé (plus clair s'il est encore en cours)|
|Fruits|Les publications scientifiques|
|Feuilles|Les communications|
|Fleurs|Les autres informations (prix, brevets, événements…)|
|Oiseaux|Les stagiaires|
|Animaux|Le personnel recruté|
|Mousse sur l'écorce|Les périodes financées|
|Épaisseur du bois|L'activité (financements, valorisations, recrutements)|
|Feuillage d'automne|Un projet sans mise à jour depuis plus de deux ans et sans branche en cours|

Les dates de fin peuvent être dans le futur : la partie prévisionnelle est voilée, au-dessus d'un repère « Aujourd'hui ».

\---

## Fonctionnalités

### La forêt

* Une vue d'ensemble avec un arbre miniature par projet : sa hauteur indique la durée du projet, et son tronc l'activité.
* Un clic sur un arbre ouvre sa vue détaillée.
* Les projets peuvent être **masqués** sans être supprimés, puis réaffichés.
* « Ajouter des projets… » importe des fichiers d'arbre (`.html`) ou leurs données (`.json`). Un projet qui porte le même titre qu'un projet existant le remplace.

### L'arbre détaillé

* **Survol** d'un élément : sa fiche apparaît. **Clic** : son détail s'affiche dans le panneau de droite.
* **Filtres « Afficher »** : on coche ou décoche les thèmes, les références, les branches, les jalons, les financements, les valorisations et les recrutements.
* **Branches une à une** : décocher une branche la masque avec tout ce qu'elle porte (financements, valorisations, stagiaires, personnel, étapes) et ses ramifications. Le bouton « seule » n'affiche qu'une branche.
* Les branches sont placées automatiquement sans se chevaucher. Leur épaisseur suit l'activité et peut être réglée à la main.

### L'éditeur intégré

* Le bouton **« Modifier le projet »** ouvre un formulaire par onglets : projet, thèmes, références, branches, jalons, financements, valorisations, recrutement.
* **Enregistrer** télécharge la page complète avec ses données à jour : c'est ce fichier qu'on conserve et qu'on partage.
* Les données peuvent aussi être exportées ou importées au format JSON.

### L'apparence

La roue crantée **« Apparence »** propose quatre ambiances :

|Ambiance|Arbre|Fruits|Fleurs|Stagiaires|Personnel|Financements|
|-|-|-|-|-|-|-|
|Forêt tempérée (par défaut)|Arbre feuillu|Pommes|Fleurs des champs|Mésanges|Écureuils|Mousse et lichen|
|Désert|Cactus|Figues de barbarie|Fleurs de cactus|Cardinaux|Suricates|Coulée de sève|
|Savane|Baobab|Fruits du baobab|Hibiscus|Perroquets|Makis cattas|Mousse et lichen|
|Jardin anglais féérique|Rosier|Bourgeons de rose|Pensées|Abeilles|Fées|Guirlande de perles|

Chaque élément peut aussi être réglé séparément. Le choix est enregistré dans le fichier, la légende s'adapte toute seule, et dans une forêt l'ambiance s'applique à tous les arbres.

Le mode sombre suit le réglage du système.

\---

## Démarrer

1. Téléchargez `foret-des-projets.html`.
2. Ouvrez-le dans un navigateur récent (Chrome, Edge, Firefox, Safari).
3. Explorez le projet d'exemple **NEUROTIN**. Ses données sont **entièrement fictives**.
4. Créez votre projet avec « Nouveau projet », ou importez les vôtres avec « Ajouter des projets… ».
5. Cliquez sur « Enregistrer la forêt » pour obtenir une nouvelle version du fichier qui contient vos données.

> Le navigateur ne peut pas réécrire le fichier ouvert : chaque enregistrement télécharge une nouvelle copie. Pensez à remplacer l'ancienne.

\---

## Format des données

Les données sont rangées dans le fichier HTML lui-même, dans un bloc `<script type="application/json" id="projet">`. Les dates s'écrivent au format `AAAA-MM`. Une fin vide signifie « en cours ».

Un projet a la forme suivante :

```json
{
  "projet": {"titre": "…", "porteur": "…", "debut": "2016-01", "maj": "2026-10", "resume": "…"},
  "themes": \[{"id": "t1", "nom": "Électrophysiologie"}],
  "references": \[{"id": "r1", "theme": "t1", "court": "Laurent 2009", "titre": "…", "auteurs": "…", "annee": 2009, "revue": "…", "poids": 2}],
  "branches": \[{"id": "b1", "nom": "Pilote fNIRS", "titre": "…", "cote": "gauche", "debut": "2018-02", "fin": "2021-06", "parent": null}],
  "jalons": \[{"date": "2017-04", "titre": "Avis favorable du CPP", "mot": "CPP", "etape": true, "sur": "tronc"}],
  "financements": \[{"nom": "…", "financeur": "…", "montant": "…", "debut": "2017-01", "fin": "2019-12", "sur": "tronc"}],
  "valorisations": \[{"type": "article", "date": "2021-11", "titre": "…", "auteurs": "…", "lieu": "…", "sur": "tronc"}],
  "recrutements": \[{"type": "stagiaire", "nom": "…", "date": "2018-03", "fin": "2018-08", "titre": "…", "sur": "tronc"}]
}
```

Repères :

* `sur` rattache un élément au tronc (`"tronc"`) ou à une branche (son `id`).
* `parent` fait partir une branche d'une autre branche ; `cote` vaut `"gauche"` ou `"droite"` pour les branches du tronc.
* `poids` (1 à 3) règle l'épaisseur d'une racine de référence.
* `type` d'une valorisation : `article`, `communication` ou `autre`. Celui d'un recrutement : `stagiaire` ou `personnel`.
* `etape: true` affiche le jalon dans la colonne des étapes clés, avec le texte de `mot`.

Une forêt réunit plusieurs projets : `{"foret": {"titre": "…", "resume": "…"}, "projets": \[ … ], "apparence": {"ambiance": "foret"}}`.

Il n'est pas nécessaire d'écrire ce JSON à la main : l'éditeur intégré le produit.

\---

## Confidentialité

* Les données restent dans le fichier et sur votre ordinateur. Rien n'est envoyé à un serveur.
* La page charge seulement ses polices de caractères depuis Google Fonts. Sans connexion, elle s'affiche avec les polices du système, sans autre différence.
* Un fichier enregistré contient toutes les données saisies : vérifiez son contenu avant de le partager.

\---

## Technique

* HTML, CSS et JavaScript, sans bibliothèque ni dépendance.
* Dessins entièrement vectoriels (SVG) générés par le code : aucune image externe.
* Placement des branches sans chevauchement, avec un hasard reproductible : un même fichier donne toujours le même arbre.

\---

## Auteur

Conçu par **Damien Gabriel**, coordonnateur de la plateforme Neuraxess (CHU de Besançon, Université de Franche-Comté).

