# 🎖 Quizzer — Quiz Editor Formation Militaire

> Éditeur de quiz interactif pour formations militaires. Interface sombre, export PDF, gestion par catégories, images dans les questions, aperçu carte en temps réel.

**Version actuelle : v1.0.3**  
🔗 **[Accéder à l'application](https://paulsenecal.github.io/Quizzer/)**

---

## Fonctionnalités

- **Éditeur de questions** avec aperçu carte en temps réel
- **8 catégories** : SIT, ISTC, NRBC, ARMEMENT, RENS, TOPO, TRANS, CYBER SÉCU (personnalisables)
- **Image par question** (JPG, PNG, GIF, WEBP — stockée en base64)
- **Réponses multiples** — jusqu'à 6 réponses par question, mode QCM activable
- **Sidebar scrollable** — navigation dans les questions sans perdre l'éditeur
- **Filtre par catégorie** dans la liste
- **Export / Import JSON** — sauvegarde complète du quiz
- **Génération PDF** — cartes de quiz formatées pour l'impression
- **Persistance locale** — les données sont sauvegardées dans le navigateur (localStorage)
- **Interface 100% hors-ligne** — aucun serveur requis, un seul fichier HTML

---

## Utilisation

### Démarrage rapide

1. Ouvrir l'application via le lien ci-dessus (ou le fichier `quiz_editor.html` en local)
2. Cliquer sur **+ Nouvelle question** pour créer une question
3. Renseigner la catégorie, la question, les réponses et cocher la bonne
4. L'aperçu carte se met à jour en temps réel à droite

### Sauvegarder / Charger

- **Sauvegarder JSON** → exporte toutes les questions dans un fichier `.json`
- **Charger JSON** → importe un fichier précédemment sauvegardé
- La sauvegarde automatique dans le navigateur est active à chaque modification

### Générer un PDF

Cliquer sur **Générer PDF** pour lancer l'impression. Les cartes sont formatées automatiquement, avec couleur de catégorie, lettres de réponse et indication de la bonne réponse.

### Ajouter une image à une question

Dans l'éditeur, cliquer sur la zone **Image (optionnelle)** pour uploader une image. Elle s'affiche dans la carte entre la question et les réponses. Cliquer à nouveau pour changer, ×️ pour supprimer.

### Gérer les catégories

Cliquer sur **Sujets** dans le header pour accéder au gestionnaire de catégories : ajouter, renommer, changer la couleur.

---

## Structure du projet

```
Quizzer/
├── quiz_editor.html    # Application complète (fichier unique autonome)
└── README.md
```

Toute la logique (HTML, CSS, JavaScript) est contenue dans un seul fichier. Aucune dépendance externe, aucun build nécessaire.

---

## Format JSON

Les données exportées suivent ce format :

```json
{
  "categories": [
    { "id": "sit", "label": "SIT", "color": "#3b82f6" }
  ],
  "questions": [
    {
      "id": 1,
      "category": "sit",
      "question": "Quelles sont les 5 fonctions de la défense ?",
      "image": null,
      "multiCorrect": false,
      "answers": [
        { "text": "Anticiper, prévenir, dicter, progresser, informer", "correct": false },
        { "text": "Connaître/anticiper, prévenir, dissuader, protéger, intervenir", "correct": true }
      ]
    }
  ]
}
```

---

## Changelog

### v1.0.3
- Affichage du numéro de version dans le header

### v1.0.2
- Sidebar indépendante avec scroll isolé — navigation dans les questions sans perdre l'éditeur

### v1.0.1
- Ajout du support image par question (base64, optionnel)
- Indicateur 🖼 dans la sidebar pour les questions avec image

### v1.0.0
- Version initiale : éditeur, catégories, export JSON, génération PDF

---

## Licence

Projet personnel — usage interne formation militaire.
