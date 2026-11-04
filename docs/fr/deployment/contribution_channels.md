# Appel à la contribution de Shimera

Ce document explique pourquoi l'équipe Shimera fait appel à des contributions externes, comment ces appels sont faits, et sur quelles plateformes. Il détaille les phases 2 et 3 de la [Stratégie de diffusion](./diffusion_strategy.md).

## 1. Pourquoi faire appel à des contributions

- **L'open source vit grâce à sa communauté** : Shimera est entièrement open source sous licence GPL 3.0. Une librairie graphique bas niveau gagne en valeur et en confiance grâce à la relecture par des pairs et aux contributions externes, pas seulement grâce au travail de son équipe d'origine.
- **Capacité limitée de l'équipe** : l'équipe est réduite et sa disponibilité baisse pendant les périodes d'examens et de stages. Les contributeurs externes aident à faire avancer le projet (backends, shaders, tests, documentation).
- **Couverture matérielle et logicielle** : une librairie graphique se comporte différemment selon le GPU, le driver et le système d'exploitation. Les contributeurs qui utilisent leur propre configuration aident à trouver des bugs et des problèmes de portabilité que l'équipe ne peut pas reproduire sur ses propres machines.
- **Retours sur l'API** : les développeurs qui intègrent Shimera dans leurs propres projets nous montrent ce qui est flou, manquant ou difficile à utiliser.
- **Crédibilité** : des contributeurs externes et une communauté active aident le projet à être perçu comme un outil sérieux plutôt que comme un projet étudiant.

## 2. Comment faire appel à des contributions

### Avant de publier

Un appel à contributions ne fonctionne que si les nouveaux venus peuvent démarrer rapidement. Avant toute publication, le dépôt doit avoir :

- Un README clair (présentation, exemples de code, captures d'écran ou GIFs de démos de shaders).
- Un `CONTRIBUTING.md` expliquant comment compiler, tester et proposer des modifications.
- Un fichier `LICENSE` (GPL 3.0).
- Des issues ouvertes avec les labels `good first issue` et `help wanted`, pour que les nouveaux venus sachent par où commencer.
- Une release taguée avec un changelog.

### Contenu de chaque publication

- Ce qu'est Shimera, en une ou deux phrases.
- L'état actuel du projet (ce qui fonctionne, ce qui est en cours).
- Le type d'aide recherché, avec les liens vers les issues correspondantes.
- Un visuel (capture d'écran ou GIF d'un effet de shader).
- Un lien vers le dépôt GitHub et vers le `CONTRIBUTING.md`.

### Règles de publication

- **Lire d'abord les règles de chaque communauté** : beaucoup de communautés limitent l'autopromotion ou l'autorisent seulement à un endroit précis (salon de présentation de projets, fil hebdomadaire, flair).
- **Adapter le message au public** : une communauté de programmation graphique s'intéresse au rendu et aux shaders, une communauté de développement de jeux s'intéresse à l'intégration avec son moteur ou son framework.
- **Ne pas spammer** : publier une seule fois par communauté, éviter de poster le même message partout le même jour, et espacer les publications de suivi (par exemple, une par release majeure).
- **Rester présent après la publication** : répondre rapidement aux commentaires et aux questions, surtout pendant les premiers jours.
- **Publier au nom de l'équipe** : les publications sont faites depuis le compte d'un membre de l'équipe, qui indique clairement faire partie de l'équipe Shimera.

### Après la publication

- Répondre rapidement aux nouvelles issues et pull requests des nouveaux venus, car une première réponse lente est la principale raison pour laquelle les contributeurs abandonnent.
- Suivre des indicateurs simples après chaque publication (stars, forks, nouvelles issues, nouveaux contributeurs) pour voir quels canaux fonctionnent le mieux.

## 3. Plateformes et emplacements

### Reddit

| Emplacement | Public | Notes |
|---|---|---|
| [r/GraphicsProgramming](https://www.reddit.com/r/GraphicsProgramming/) | Programmeurs graphiques et spécialistes du rendu | Cible Reddit principale. Centrer la publication sur la partie rendu/shaders de Shimera et inclure des visuels. |
| [r/raylib](https://www.reddit.com/r/raylib/) | Utilisateurs de Raylib | Centrer la publication sur le backend Raylib et montrer comment ajouter des effets Shimera à un projet Raylib. |
| [r/sfml](https://www.reddit.com/r/sfml/) | Utilisateurs de SFML | Centrer la publication sur le backend SFML et montrer comment ajouter des effets Shimera à un projet SFML. |

### Discord

| Serveur | Public | Notes |
|---|---|---|
| Epitech et Epitech Toulouse | Étudiants développeurs | Publier dans le salon que le serveur réserve à la présentation de projets ou à l'autopromotion, en respectant ses règles. |

### GitHub

| Emplacement | Public | Notes |
|---|---|---|
| Topics du dépôt et labels des issues | Développeurs qui cherchent sur GitHub des projets auxquels contribuer | Ajouter des topics (`opengl`, `glsl`, `raylib`, `sfml`, `cpp`, `shader-library`) et garder des issues avec les labels `good first issue` / `help wanted`. GitHub les utilise pour recommander des projets. |
| [goodfirstissue.dev](https://goodfirstissue.dev/) | Personnes qui contribuent à l'open source pour la première fois | Les projets ne sont pas ajoutés automatiquement : nous devons demander l'ajout de Shimera sur le site, en respectant ses conditions de référencement. Une fois référencé, le site affiche nos issues `good first issue`. |
| GitHub Discussions | Utilisateurs et contributeurs de Shimera | Activer les Discussions sur le dépôt pour que les contributeurs puissent poser des questions et proposer des idées sans ouvrir d'issues. |
| Listes « Awesome » (ex. awesome-opengl, awesome-cpp, awesome-raylib) | Développeurs qui cherchent des librairies dans un écosystème donné | Ouvrir une pull request sur chaque liste pour y ajouter Shimera, en respectant les règles de contribution de chaque liste. |

### Autres

| Plateforme | Public | Notes |
|---|---|---|
| [Bluesky](https://bsky.app/) | Développeurs de jeux et programmeurs graphiques | Publier de courtes mises à jour avec des visuels (GIFs d'effets de shaders) et des hashtags pertinents comme `#gamedev` et `#graphicsprogramming`. |
