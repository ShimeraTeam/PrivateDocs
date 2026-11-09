# Périmètre open source

Ce document liste **ce que Shimera ouvre, sous quelle licence, et ce qui reste
privé**. C'est le complément opérationnel de la
[Stratégie de protection juridique](/fr/legal/legal_protection_strategy) (pourquoi
et comment nous protégeons le projet) et de la
[Stratégie de diffusion](/fr/deployment/diffusion_strategy) (pourquoi nous avons
choisi l'open source). À utiliser avant toute publication : une release, un
déploiement de documentation, un nouvel asset, ou un changement de visibilité d'un
dépôt.

## 1. Résumé

Shimera ouvre **deux choses** : l'intégralité du dépôt `Shimera` et la
documentation publique (`ShimeraTeam/Docs`). Tout le reste reste privé.

| Élément | Statut | Licence | Emplacement |
|---|---|---|---|
| Code source de la librairie (`src/`) | **Ouvert** | `GPL-3.0-only` | `ShimeraTeam/Shimera` |
| Sources des shaders (`res/shader/**/*.slang`, `.frag`, `.vert`) | **Ouvert** | `GPL-3.0-only` | `ShimeraTeam/Shimera` |
| Images d'exécution (`res/imgs/`) | **Ouvert** | `GPL-3.0-only` | `ShimeraTeam/Shimera` |
| Exemples (`examples/`) | **Ouvert** | `GPL-3.0-only` | `ShimeraTeam/Shimera` |
| Scripts de build (`xmake.lua`, `.run/`) | **Ouvert** | `GPL-3.0-only` | `ShimeraTeam/Shimera` |
| Fichiers de gouvernance (`LICENSE`, `AUTHORS.md`, `CONTRIBUTING.md`, `README.md`) | **Ouvert** | n/a (métadonnées du projet) | `ShimeraTeam/Shimera` |
| Binaires de release (`.a`, `.so`, headers) | **Ouvert** | `GPL-3.0-only` | GitHub Releases |
| Documentation utilisateur et contributeur (`user/`, `contributor/`) | **Ouvert** | `CC-BY-4.0` (voir 3.3) | `ShimeraTeam/Docs`, GitHub Pages |
| Documentation interne (ce site) | **Privé** | Tous droits réservés | `ShimeraTeam/PrivateDocs` |
| Dépôt e-Soleau, PDF du plan d'action, livrables scolaires | **Privé** | Tous droits réservés | Mainteneurs uniquement |
| Le nom « Shimera » et le logo | **Non licencié** | Non couvert par la GPL | Assets de marque |
| Secrets CI, configuration du runner, identifiants | **Privé** | n/a | Paramètres GitHub |

La règle générale : **tout ce qui est nécessaire pour compiler, utiliser, étudier
et modifier la librairie est ouvert. Tout ce qui relève de la stratégie interne,
des preuves, de la marque ou de l'infrastructure reste privé.**

## 2. Ce qui est ouvert, et pourquoi

### 2.1 L'intégralité du dépôt de la librairie (`ShimeraTeam/Shimera`)

Tout le contenu suivi du dépôt est public et sous licence **GPL-3.0-only**, sans
exception :

- `src/` : le cœur (`Context`, `EffectPipeline`), la couche OpenGL (`GL/`), les
  effets, matériaux, scène, uniforms, et les adaptateurs hôtes (`hosts/` : GLFW,
  SFML, raylib, SDL).
- `res/shader/` : les sources Slang et GLSL de chaque effet et matériau. C'est le
  cœur de la valeur du projet, ouvert volontairement : le copyleft de la GPL est
  ce qui empêche un produit fermé de les réutiliser en silence.
- `res/imgs/` : images utilisées par les exemples.
- `examples/` : programmes autonomes par librairie hôte.
- `xmake.lua` et `.run/` : configuration de build.
- L'historique Git complet, qui fait aussi partie de notre preuve d'antériorité
  (voir la [Stratégie de protection juridique](/fr/legal/legal_protection_strategy),
  section 5.2).

Non publiés (exclus par `.gitignore`) : `build/`, `.xmake/`,
`compile_commands.json`, et `res/shader/generated/` (le GLSL produit par le
pipeline Slang au build ; il dérive des sources Slang et peut toujours être
régénéré).

**Pourquoi tout ouvrir :** la GPL exige que quiconque distribue Shimera puisse
fournir le *code source correspondant complet*, scripts de build compris. Garder
une partie du dépôt privée rendrait nos propres releases non conformes et
casserait l'argument de confiance de la [Stratégie de diffusion](/fr/deployment/diffusion_strategy).

### 2.2 Binaires de release

Les binaires publiés sur GitHub Releases (par exemple
`shimera-X.Y.Z-sfml-windows-x64.zip`) sont des distributions d'une œuvre sous GPL.
Chaque archive **doit** contenir :

- `LICENSE` (texte complet de la GPL-3.0) ;
- `AUTHORS.md` ;
- un `README.md` qui pointe vers le tag source exact (par exemple `v0.3.6`) de
  `ShimeraTeam/Shimera`.

Publier le source sur le même projet GitHub, au tag correspondant au binaire,
satisfait l'obligation de mise à disposition du source (GPL-3.0 section 6).

### 2.3 Documentation publique (`ShimeraTeam/Docs`)

La documentation utilisateur (`user/`) et contributeur (`contributor/`) vit dans
son propre dépôt, `ShimeraTeam/Docs`, et est construite et déployée sur GitHub
Pages par son workflow `Documentation`. Elle est ouverte car les utilisateurs en
ont besoin pour adopter la librairie, et les contributeurs pour suivre le flux de
contribution référencé par `CONTRIBUTING.md` (standards de code, workflow git,
guide de tests).

Ouvrir la documentation signifie ouvrir aussi ses **sources**, pas seulement le
site généré. C'est pour cela que la documentation publique a été séparée de ce
dépôt privé (voir la section 4).

## 3. Choix de licence par élément

### 3.1 Code et shaders : `GPL-3.0-only`

Justifié dans la [Stratégie de protection juridique](/fr/legal/legal_protection_strategy),
section 4. Chaque fichier source (`.cpp`, `.hpp`, `.h`, `.inl`, `.slang`, `.frag`,
`.vert`) doit commencer par l'en-tête standard :

```cpp
// SPDX-License-Identifier: GPL-3.0-only
//
// Shimera: a simple way to add visual effects without using any GPU knowledge
// Copyright (C) 2025-2026 The Shimera Authors
//
// This program is free software: you can redistribute it and/or modify
// it under the terms of the GNU General Public License as published by
// the Free Software Foundation, version 3 of the License.
//
// This program is distributed in the hope that it will be useful,
// but WITHOUT ANY WARRANTY; without even the implied warranty of
// MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
// GNU General Public License for more details.
//
// You should have received a copy of the GNU General Public License
// along with this program.  If not, see <https://www.gnu.org/licenses/>.
```

L'en-tête ne crée pas la licence (le fichier `LICENSE` s'en charge déjà), mais il
garde la licence attachée au fichier quand celui-ci est copié hors du dépôt, ce
qui est exactement ce qui arrive avec les shaders.

### 3.2 Exemples

Les exemples sont sous GPL comme le reste du dépôt. C'est cohérent : tout
programme construit sur Shimera et distribué est déjà soumis à la GPL, donc une
licence plus permissive sur les seuls exemples ne donnerait pas plus de liberté
aux utilisateurs.

### 3.3 Documentation publique : `CC-BY-4.0`

La documentation publique (`ShimeraTeam/Docs`) est sous licence **Creative
Commons Attribution 4.0 International**. Sans licence, elle aurait été « tous
droits réservés » : on aurait pu la lire, mais pas légalement la réutiliser, la
traduire ou la corriger.

**Ce que permet la CC BY 4.0 :** chacun peut partager et adapter la
documentation, pour tout usage, y compris commercial, à condition de citer The
Shimera Authors, de donner un lien vers la licence et d'indiquer ses
modifications. C'est une licence permissive : une version adaptée peut être
publiée sous une autre licence.

**Pourquoi la CC BY 4.0 et pas la GPL ou la CC BY-SA :**

- La GPL est écrite pour du logiciel (code source, code objet) et s'applique mal
  à un site de documentation. La GFDL est lourde, peu utilisée, et autorise des
  sections invariantes.
- La valeur du projet, et ce que protège le copyleft, ce sont le code et les
  shaders. La documentation publique ne contient **aucun source de shader**,
  seulement des exemples d'utilisation de l'API publique : une licence permissive
  n'ouvre donc aucune faille.
- La CC BY garde toutes les trajectoires futures ouvertes (double licence GPL +
  commerciale, ou MPL-2.0) : les licenciés commerciaux peuvent utiliser la
  documentation, et une future documentation commerciale peut la reprendre sans
  contrainte. La CC BY-SA aurait imposé à toute documentation adaptée, y compris
  les contributions d'auteurs externes, de rester sous CC BY-SA.
- Une licence permissive facilite les traductions, tutoriels et articles de blog,
  tout en gardant les auteurs crédités.

**Comment elle est appliquée dans `ShimeraTeam/Docs` :**

- `LICENSE` : le texte juridique officiel et complet de la CC BY 4.0.
- `README.md` : la mention de licence, la ligne de crédit attendue, et ce qui est
  exclu (le code de la librairie sous `GPL-3.0-only`, le nom et le logo).
- Une mention en bas de chaque page du site (thème VitePress personnalisé, slot
  `doc-footer-before`), en anglais et en français.
- `CONTRIBUTING.md` : la même cession de droits que le dépôt de la librairie, y
  compris le droit pour les mainteneurs de changer la licence des contributions.

**Les exemples de code** de la documentation sont eux aussi sous CC BY 4.0.
Copier un court extrait d'utilisation comme `fx.add<shimera::Distortion>()` ne
pose aucun problème pratique, puisqu'un programme qui l'utilise est de toute façon
soumis à la GPL de la librairie. Si la documentation contient un jour du code plus
long et réutilisable, envisager de placer les blocs de code sous une licence sans
obligation de citation comme `MIT-0`.

**Images :** seules des images créées par l'équipe (captures des exemples
Shimera) peuvent être ajoutées. Une capture qui montre une texture ou une image
tierce doit être remplacée, ou sa propre licence doit être vérifiée et indiquée à
côté.

### 3.4 Nom et logo : non licenciés

La GPL couvre le code, pas la marque. Le nom « Shimera », le logo
(`shimera_logo_v2.1.png`) et l'affiche (`affiche.png`) ne sont **pas** placés sous
GPL. Un fork peut réutiliser le code mais ne doit pas se présenter comme le
Shimera officiel (voir [Stratégie de protection juridique](/fr/legal/legal_protection_strategy),
section 7). Si le logo est utilisé dans la documentation publique ou le README,
indiquer à côté qu'il est exclu de la licence de la documentation.

## 4. Ce qui reste privé, et pourquoi

| Élément | Pourquoi il reste privé |
|---|---|
| `ShimeraTeam/PrivateDocs` (ce site) | Stratégie interne : protection juridique, security map (notre propre surface d'attaque), POC, plan d'action, veille technologique. |
| Archive et accusé de dépôt e-Soleau | Preuve d'antériorité : sa valeur vient du fait qu'elle est scellée et conservée par nous. Seuls son existence et sa date sont mentionnées. |
| `plan_d_action_shimera.pdf` et livrables scolaires | Documents de planification internes, sans utilité pour les utilisateurs. |
| Secrets CI, tokens, configuration du runner self-hosted | Sécurité. Jamais dans aucun dépôt, public ou privé. |
| Conditions commerciales (futur dual-license) | Information commerciale, à rédiger seulement si le dual-licensing est activé. |

::: warning Garder les deux dépôts de documentation séparés
La documentation publique vit dans `ShimeraTeam/Docs` et la documentation interne
dans `ShimeraTeam/PrivateDocs`. Ne jamais déplacer ni copier une page de
`PrivateDocs` vers `Docs` : une fois poussée sur un dépôt public, elle reste dans
l'historique Git même si elle est supprimée ensuite. `PrivateDocs` doit rester
privé.
:::

## 5. Composants tiers

Shimera n'embarque aucun code source tiers : toutes les dépendances sont
récupérées par xmake au build (`add_requires`). Les archives de release ne
contiennent que la librairie statique ou partagée de Shimera et ses headers.
Toutes les dépendances sont compatibles avec la GPL-3.0.

| Composant | Version | Usage | Licence | Compatible GPL-3.0 |
|---|---|---|---|---|
| GLEW | 2.2.0 | Exécution (lié) | BSD modifiée + MIT | Oui |
| GLM | 1.0.1 | Exécution (header-only) | MIT | Oui |
| GLFW | 3.4 | Exemples / hôte GLFW | zlib | Oui |
| SFML | 3.0.1 | Hôte SFML (optionnel) | zlib | Oui |
| raylib | 5.5 | Hôte raylib (optionnel) | zlib | Oui |
| SDL3, SDL_image | non figée | Hôte SDL (optionnel) | zlib | Oui |
| SPIRV-Cross | 1.3.268 | Build uniquement | Apache-2.0 | Oui (avec la GPL-3.0) |
| Compilateur Slang (`slangc`) | installé par l'utilisateur | Build uniquement | Apache-2.0 avec exception LLVM | Oui |

Règles :

- Si une future release **embarque** une dépendance (par exemple des DLL GLEW
  dans une archive Windows), ajouter un `THIRD_PARTY_NOTICES.md` avec le texte de
  licence de chaque composant embarqué.
- **Ne jamais importer de code ou de shader depuis une source à licence
  incompatible.** Pièges courants en graphisme : Shadertoy (CC BY-NC-SA 3.0 par
  défaut, incompatible GPL), le code de LearnOpenGL (CC BY-NC 4.0, incompatible
  GPL), des extraits de blog sans licence. Réimplémenter à partir de la technique
  ou de la publication d'origine, et la citer en commentaire.

## 6. Checklist avant publication

Avant chaque release ou déploiement de documentation :

- [ ] Chaque fichier source a l'en-tête `SPDX-License-Identifier: GPL-3.0-only`.
- [ ] `LICENSE`, `AUTHORS.md`, `README.md` sont présents à la racine et dans l'archive de release.
- [ ] `AUTHORS.md` liste chaque contributeur dont le travail est mergé.
- [ ] Aucun code ou shader tiers à licence incompatible ou inconnue (section 5).
- [ ] Aucun secret, token, document interne ou élément e-Soleau dans l'arborescence publique ou son historique.
- [ ] Rien de `ShimeraTeam/PrivateDocs` copié dans un dépôt public.
- [ ] `ShimeraTeam/Docs` a toujours son `LICENSE` (CC BY 4.0) et chaque nouvelle image qu'il contient a été créée par l'équipe.
- [ ] Le tag de release correspond aux binaires publiés (disponibilité du source).

## Conclusion

Shimera ouvre **l'intégralité du dépôt de la librairie** (code, shaders, exemples,
scripts de build, historique), **ses binaires** et **sa documentation publique** :
tout ce dont on a besoin pour utiliser, comprendre et améliorer la librairie. Il
garde **sa documentation interne, ses preuves, sa marque et son
infrastructure** privées. La partie ouverte est protégée par la GPL-3.0-only ; la
partie privée est ce qui permet à l'équipe de prouver la paternité, défendre le
nom, et conserver les options de licence futures décrites dans la
[Stratégie de protection juridique](/fr/legal/legal_protection_strategy).
