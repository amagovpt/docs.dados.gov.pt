---
title: Découvrir l'OpenData en tant que développeur
subtitle: Comment intéragir avec la plateforme ? Avec quelles API ?
label: En tant que développeur
summary: Comment intéragir avec la plateforme ? Avec quelles API ?
---

# Découvrir l’OpenData en tant que développeur

Cette default contient :

- [les informations relatives à l’API](#section-api)
- [le moissonnage des dépôts de données ouvertes](#section-moissonage)
- [le code source de la plateforme](#section-code)

<span id="section-api"></span>
## Informations relatives à l’API

Le site « [data.gouv.fr][] » propose différents moyen d'accéder au catalogue des données :

- une [API complète][API], documentée avec [Swagger][swagger]
- des dumps au format CSV, mis à jour en temps réel
  - catalogue des jeux de données: <https://www.data.gouv.fr/datasets.csv>
  - catalogue des ressources: <https://www.data.gouv.fr/resources.csv>
  - catalogue des organisations: <https://www.data.gouv.fr/organizations.csv>
  - catalogue des réutilisations: <https://www.data.gouv.fr/reuses.csv>
  - une liste des tags avec leur nombre d'occurences: <https://www.data.gouv.fr/tags.csv>
- des [statistiques de fréquentation anonymisées][piwik], mises à jour toutes les heures

L'intégralité des opérations réalisables depuis le site via votre navigateur peuvent être automatisées
(publication d'un jeu de données, création d'organisations, etc).
Veuillez consulter la documentation dédiée pour y accéder.

<span id="section-moissonage"></span>
## Moissonnage des dépôts de données ouvertes

« [data.gouv.fr][] » met à disposition une infrastructure de moissonnage,
permettant d’être automatiquement intégrée sur la plateforme.
Il est ainsi possible d’écrire son propre moissonneur en s’inspirant
du [code des moissonneurs existants][moissonneurs],
fournis en Open Source (comme tout le reste du site « [data.gouv.fr][] », distribué sous le nom [uData][]).

Aujourd'hui, les moissoneurs suivants sont disponibles :

- CKAN (générique)
- OpenDataSoft (générique)
- maaf (spécifique Ministère de l'Agriculture, de l'Agroalimentaire et de la Forêt)

Le moissonnage n’est pas le seul moyen de synchroniser des données avec « data.gouv.fr »,
il est possible (voir recommandé) d’utiliser l’[API][] pour pousser ses données.

<span id="section-code"></span>
## Le code source de la plateforme

L’intégralité du code de la plateforme est [gratuitement disponible en Open-Source][uData]
sous [licence AGPL3][agpl3].
Cet outil a été développé de façon modulaire pour permettre à tout un chacun de l’installer
et de le personnaliser pour son usage propre en marque blanche.
Nous avons par exemple développé les modules [udata-gouvfr][] pour le rendu
et [udata-piwik][] pour les statistiques.

Vous pouvez contribuer en suivant la documentation dédiée et en proposant des pull-requests.

[data.gouv.fr]: https://www.data.gouv.fr/
[API]: https://www.data.gouv.fr/api/
[swagger]: http://swagger.io/
[piwik]: https://stats.data.gouv.fr/
[moissonneurs]: https://github.com/opendatateam/udata/tree/master/udata/harvest/backends
[uData]: https://github.com/opendatateam/udata
[agpl3]: https://www.gnu.org/licenses/agpl-3.0.html
[udata-gouvfr]: https://github.com/etalab/udata-gouvfr
[udata-piwik]: https://github.com/opendatateam/udata-piwik
