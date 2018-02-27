---
title: Découvrir l'OpenData en tant que producteur
subtitle: Que faut-il savoir avant de publier des données ?
label: En tant que producteur
summary: Que faut-il savoir avant de publier des données ?
---
# Découvrir l'OpenData en tant que producteur

## Qui est considéré comme producteur de données ?
Le producteur d'une base de données, entendu comme la personne qui prend l'initiative
et le risque des investissements correspondants,
bénéficie d'une protection du contenu de la base lorsque la constitution,
la vérification ou la présentation de celui-ci atteste d'un investissement financier,
matériel ou humain substantiel.

Cette protection est indépendante et s'exerce sans préjudice de celles résultant du droit d'auteur
ou d'un autre droit sur la base de données ou un de ses éléments constitutifs.

Source [Legifrance][legifrance-producer]

## Les services publics certifiés
Les organisations inscrites sur la plateforme « [data.gouv.fr][] » estimant assurer une mission de service public
peuvent effectuer une demande en ligne pour être reconnue comme tel.
Une organisation certifiée bénéficie d’un meilleur référencement.

Pour devenir un service public certifié, inscrivez-vous sur le site en tant qu’organisation,
puis effectuez la demande en envoyant un mail à l'adresse suivante : [certification@data.gouv.fr][].
Une vérification par email ou courrier vous sera demandée.
Vous pouvez néanmoins commencer à publier vos jeux de données avant d’obtenir le badge de certification.

## Qu'est qu'un jeu de données ?
Un jeu de données peut contenir plusieurs ressources (fichiers de données, fichiers d'explications, API, lien...)
qui constituent un lot cohérent sur un thème donné.

Par exemple «[La Réserve Parlementaire][]», contiendra plusieurs ressources, typiquement un fichier par année.

### Les jeux de données «à la une»
Les jeux de données à la une changent périodiquement.
Etalab, en tant qu’administrateur et éditeur de la plateforme « [data.gouv.fr][] »,
fait une analyse exhaustive des jeux de données hébergés sur la plateforme afin de mettre en avant ceux qui,
d’après l’actualité française, pourraient être utiles aux visiteurs de la plateforme.

## Comment en tant que producteur, puis-je publier des jeux de données ?
Créez un compte sur « [data.gouv.fr][] ».
Dès que vous serez inscrit, vous pourrez «contribuez» et «publier un jeu de données».

Un jeu de données peut être publié simplement avec un titre et une ressource.
Pour autant, il sera mieux référencé s'il contient des informations supplémentaires qui le décrivent :
période couverte, fréquence de mise à jour, territoire couvert, thématiques…

## Que signifient les différents champs d'une fiche de jeu de données ?

### Titre (obligatoire)
Le titre est "l'accroche" éditoriale de votre contenu, son sujet. Pensez-y.
Il doit être clair, précis et le plus court possible.
Ne pas mettre d'indications temporelles ou de couverture géographique dans le titre,
mais dans les champs prévus à cet effet.

**Exemples** :

- Impôts locaux
- Impact environnemental des sociétés minières

**Contre exemples** :

- Impôts locaux en Lorraine pour l'année 2012
- Impact environnemental des société minières dans le cadre de la campagne de réactualisation
  des faits opérés par la DATAR pour le compte de l'Institut.

### Description
C'est ici qu'il faut mettre en avant le jeu de données, en citant les faits, les mots-clés qu'il recouvre,
les sources et la méthodologie utilisée...
Pour écrire une bonne description, il faut raisonner comme un moteur de recherche :
quelles questions posées par les Internautes devraient mener à ce jeu de données ?
*Exemple :* pour l'impact environnemental, citer les mots-clés tonne-carbone, externalité environnementale,
principaux facteurs négatifs et positifs de l'impact des mines sur l'environnement, etc.

### Licence
Sélectionner la licence Open Data sous laquelle vous publiez le jeu de données.
Dans la plupart des cas, l'[Open Licence / Licence Ouverte][lo].
Seuls les réutilisations publiées dans un jeu de données peuvent être sous licence fermée.
Par exemple, un jeu de données Open Data «Annuaire des associations», et une réutilisation fermée,
voire payante, permettant de consulter les adresses des dirigeants des associations.

### Fréquence de mise à jour
La fréquence indique le niveau de détail temporel à l'intérieur de cette période :
indiquer "mois" si votre fichier détaille des évolutions mois par mois.
Si votre flux d'information est mis à jour annuellement, indiquer «année».

### Couverture temporelle
A l'image de la couverture géographique,
la couverture temporelle permet de référencer correctement la période couverte.
S'il s'agit d'une seule année, indiquez la même année pour le début et la fin.
S'il s'agit d'une année scolaire, n’hésitez pas à indiquer 1/9/2013 au 31/6/2014 par exemple.

### Couverture spatiale
C'est dans ce champs qu'il convient de décrire le territoire couvert et permettra d'être correctement géo-référencé.

### Granularité spatiale
Préciser la granularité permet de préciser s'il s'agit d'un jeu de donnée très agrégé (par exemple couverture = France, granularité = France), ou au contraire très détaillé (couverture = région, granularité = commune, voire même point d'intérêt au niveau adresse).

### Mots clés
Les mots-clés permettent des navigations transverses,
c'est à dire qu'un internaute naviguant sur un jeu de données ayant pour mots clés «mines»
sera susceptible de cliquer sur ce mot clé et de retrouver un autre jeu de données ayant le même mot clé.
Si vous remplissez ce champs,
la règle est donc d'utiliser des mots clés ayant déjà été utilisés par d'autres jeux de données.

### Visibilité
Sélectionner "privé" permet de sauvegarder un jeu sans qu'il soit visible.
Ce peut être utile lorsque vous souhaitez publier plusieurs jeux à une date donnée,
en ayant préparé leur publication en amont.

Si vous avez bien remplie la fiche et vous souhaitez que votre jeu de donnée soit visible sur le site,
ne cochez pas la case.

### Ressources (1 obligatoire)
Les ressources de votre jeu de données.
Si votre jeu concerne plusieurs départements, plusieurs années,
il est possible de publier autant de fichiers que vous le souhaitez.
Pour autant, sachez que du point de vue des réutilisateurs,
il est **toujours préférable de diffuser les fichiers les plus denses possibles** :
un fichier contenant en colonne 1 le département, en colonne 2 l'année et toutes les données ainsi classées,
plutôt que 100 fichiers par département, puis autant par année.

Chaque ressource possède un **titre**, dans lequel il convient surtout de **préciser les critères,
les unités, la granularité qui décrit le mieux la ressource**,
plutôt que de répéter le titre du jeu de donnée auquel il appartient. Par exemple :

- Fichier détaillé des personnes morales, par département et par an
- Fichier statistique par département, en k€ et en Tonne/Carbone
- Site web permettant de sélectionner les données par ville et par type de trajet

Une description de la ressource peut être ajoutée de manière optionnelle
pour exprimer des compléments d'informations sur la méthodologie (sondage, enquête, données fiscales ..),
des précisions sur les données en question (colonnes du fichiers ..),
ou tout autre information renforçant le titre.

### Télécharger un fichier ou saisir son URL ?
Si vous ne possédez pas de site Web et que la fréquence de mise à jour de vos données est faible,
« [data.gouv.fr][] » permet de télécharger des fichiers depuis votre ordinateur.
Néanmois, si vous possédez un site Web, il est préférable de référencer vos données,
évitant ainsi de devoir les mettre à jour régulièrement sur data.gouv.
Par exemple, référencer la ressource <http://monsite.fr/jeu_de_donnees_derniere_version.csv>
vous permet de déclarer une fois pour toutes une donnée avec une fréquence de mise à jour temps réel.

### Bureau, département ou service
Préciser ici, de manière optionnelle, les indications sur l'organisation effectivement productrice,
par exemple SGMAP/Service X.

### Courriel de contact
Préciser ici, de manière optionnelle, l'adresse mail du producteur,
par exemple *contact@agriculture.fr*,
si elle est différente de celle de l'utilisateur qui publie.
Lorsque vous publiez un jeu de données au nom d'une organisation,
tous les membres déclarés seront automatiquement notifiés d'éventuelles réutilisations sur la default
du jeu de données (par exemple, la publication d'une visualisation ou d'un commentaire).

### Thématique (groupes)
A l'image des mots clés, qui permettent d'accrocher votre jeu de données à d'autres dimensions,
des thématiques sont à votre disposition pour ancrer vos jeux dans les grandes catégories éditoriales présentées
à côté du moteur de recherche : Agriculture, Culture, Société, Territoires, etc.
À noter, des thématiques conjoncturelles permettent de raccrocher certains jeux à des sujets d'actualité
débattus sur « [data.gouv.fr][] » : égalité femmes-hommes, Grenelle de l'environnement, etc.
Un jeu de données peut appartenir à 0, 1 ou 2 thématiques.

## Qu'est-ce que la passerelle Inspire
La directive INSPIRE est la directive 2007/2/CE du Parlement européen et du Conseil du 14 mars 2007 établissant une infrastructure d'information géographique dans la Communauté européenne (INSPIRE).

INSPIRE s'applique à 34 domaines thématiques, se décomposant en trois groupes principaux :

1. Les données nécessaires au repérage sur le territoire, telles que :
   - systèmes de coordonnées,
   - unités adminsitratives,
   - réseaux de transport,
   - hydrographie,
   - parcellaire cadastral,
   - adresses et noms de lieux ainsi que des données relatives aux sites protégés.
2. Les données générales complémentaires telles que:
   - l'altimétrie,
   - l'occupation des terres,
   - la géologie et l'horto-imagerie
3. Les données thématiques telles que:
   - bâtiments,
   - vocation des sols,
   - santé et sécurité des personnes,
   - service d'utilité publique et services publics,
   - données sur l'environnement (nombreuses et variées),
   - installations industrielles, agricoles,
   - démographie,
   - périmètres de réglementation,
   - données météorologiques,
   - données maritimes,
   - sources d'énergie et ressources minérales.

Les standards de la géomatique ne sont pas ceux du Web et pourtant ils structurent l’immense capital
d’informations accumulé depuis plusieurs dizaines d’années.
D’un côté des normes comme Inspire, WFS, WCS, CSW, Shapefiles, GeoJSON, KML,
de l’autre des outils gratuits comme OpenStreetMap ou Google Earth.
La passerelle Inspire, en production depuis début 2015,
permet aux producteurs et aux réutilisateurs d’exploiter au mieux ces gisements de données colossaux,
en les rendant automatiquement disponibles dans les standards du Web.
Besoin d’une carte des zones d’inondation en Bourgogne ?
Cliquez sur le jeu de données et visualisez-le dans une carte OpenStreet Map n’a jamais été aussi simple.

Fin 2015, le moteur Inspire de « [data.gouv.fr][] » permettra surtout de réunir les données géographiques produites
au plus près du terrain par les collectivités dans des référentiels nationaux fédérés.
Ce dispositif permettra notamment d’élargir le périmètre de l’API Carto,
destiné à simplifier la création de démarches en ligne ayant une composante géographique
(déclaration de travaux, demande d’autorisation de ruchers,
action associative sur une zone Politique de la Ville, etc.).
API Carto sera quant à lui amené à diffuser de la donnée non-publique, soumise au consentement de l’usager,
comme des données cadastrales personnelles.
API Carto sera donc un distributeur des référentiels nationaux géographiques.

C’est une donnée géographique homogène qui permettra l’émergence d’algorithmes au service de
la transition énergétique, de la transparence des politiques d’aménagement, des politiques agricoles…

Enfin, l’intégration géographique permettra de projeter des jeux de données nationaux dans les territoires,
promesse de territoire « [data.gouv.fr][] ».
Pour une organisation inscrite sur « [data.gouv.fr][] », il suffira d’activer l’option,
puis de choisir les jeux de données nationaux qu’elle souhaite diffuser sur son compte:
comptabilité locale issue de la Direction Générale des Finances,
indicateurs socio-économiques INSEE, élections, etc.
En miroir, tout producteur national pourra suivre un guide simple pour rendre un jeu de données national
compatible avec territoire.data.gouv.fr.
Tout référentiel national est bien sûr naturellement intégré dans territoire.data.gouv.fr,
par exemple les collèges et lycées sur votre département ou votre région.

### Pour contribuer à la passerelle Inspire en tant qu’autorité locale géographique (DDT, DREAL, DDTM…) :

1. Adoptez le plan de nommage suivant pour les producteurs de l'administration déconcentrée :
   - `DR[xxx] [Nom de la région accents respectés, trait-d'union partout]`` :
     DRAC Bourgogne, DREAL Nord-Pas-de-Calais, DIRECCTE Bretagne...
   - `DD[xxx] [Numéro département] : DDT 77, DDPP 34, DDTM 22` ...
   - `Préfecture de [DOM/Nom Région/Nom Département]` : Préfecture de Mayotte, Préfecture de Poitou-Charentes, Préfecture de Saône et Loire ..
2. Rendez vos jeux de données INSPIRE accessibles depuis Internet.
   Si vous ne disposez pas de serveurs où les déposer, vous pourrez utiliser ceux de data.gouv.fr.



[data.gouv.fr]: https://www.data.gouv.fr
[certification@data.gouv.fr]: mailto:certification@data.gouv.fr
[La Réserve Parlementaire]: https://www.data.gouv.fr/fr/datasets/reserve-parlementaire/
[lo]: https://www.etalab.gouv.fr/licence-ouverte-open-licence
[legifrance-producer]: http://www.legifrance.gouv.fr/affichCode.do?idArticle=LEGIARTI000006279245&idSectionTA=LEGISCTA000006161660&cidTexte=LEGITEXT000006069414&dateTexte=20090613
