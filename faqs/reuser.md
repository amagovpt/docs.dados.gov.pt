---
title: Découvrir l'OpenData en tant que réutilisateur
subtitle: Que faire avec les données ? Avec quels outils ?
label: En tant que réutilisateur
summary: Que faire avec les données ? Avec quels outils ?
---

# Découvrir l'OpenData en tant que réutilisateur


Cette default contient :

- [la transformation des données](#transform)
- [les outils pour les datavisualisations](#dataviz)
- [l'explication des OpenDataCamps](#opendatacamps)

<span id="transform"></span>
## Qu'est ce qu'une réutilisation des données publiques ?
Depuis 2005, la loi relative à la liberté d'accès aux documents administratifs
et à la réutilisation des informations publiques,
prévoit la possibilité de réutiliser les informations publiques à d’autres fins
que celles pour lesquelles elles sont détenues ou élaborées.
Si leur obtention occasionne un coût pour l’administration (recherche, traitement automatisé...),
ou si elle souhaite obtenir une rémunération de ses droits de propriété intellectuelle,
celle-ci peut demander le paiement d’une redevance après avoir conclu une licence de réutilisation
(préalable obligatoire).

En conformité au principe général de réutilisation libre,
facile et gratuite fixé par les circulaires du Premier ministre du 26 mai 2011 et du 13 septembre 2013
relatives à l’ouverture des données publiques,
Etalab est engagée à promouvoir la réutilisation des données publiques ouvertes par le biais d’actions spécifiques.

Exemples :

- Le concours [Dataconnexions][], organisé par [Etalab][],
  qui récompense les projets les plus innovants réutilisant des données publiques
- La plateforme « [data.gouv.fr][] » qui héberge 1299 réutilisations

### L’intérêt de réutiliser des données publiques ouvertes
La diversité des champs d’application de la politique d’ouverture des données est assez large. En réutilisant des jeux de données publiques, tout le monde peut créer des applications, des services ou des visualisations de données interactives. Ces réutilisations permettent, par exemple, d’améliorer l’action d’un service public ou de résoudre un problème.

Exemples :

- [Open Food Facts](https://www.data.gouv.fr/fr/datasets/produits-alimentaires-ingredients-nutrition-labels/)
  est une base de données ouverte sur les produits alimentaires du monde entier.
  Elle permet de décrypter les étiquettes (ingrédients, codes des additifs comme E150d, huile de palme, allergènes)
  et de comparer facilement les produits entre eux (apports nutritionnels, provenance et circuits de fabrication…).
  Il suffit de scanner le code barre avec l’app iPhone, Android ou Windows Phone
  pour obtenir les informations sur un produit ou en ajouter de nouveaux.
- [Medica.io](https://www.data.gouv.fr/fr/reuses/medicatio/)
  a pour but d'améliorer l'accessibilité des informations liées aux médicaments disponibles en vente,
  afin d'accompagner le consommateur dans sa démarche préliminaire
  et de l'aider à mieux s'informer avant d'en discuter avec son pharmacien ou médecin.
  En réutilisant la « base de données publique des médicaments »
  et « le Fichier national des établissements sanitaires et sociaux (FINESS) »,
  la plateforme propose tout un ensemble de services qui visent à répondre aux différentes interrogations
  pouvant être soulevées durant cette démarche :
  Peut-on associer certains médicaments entre eux sans risque ?
  Où trouver une pharmacie de garde cette nuit ?
- **City** est un projet de représentation de la ville en 3D sur le Web. Les applications sont multiples:
  permettre de communiquer le plan local d'urbanisme aux citoyens,
  cartographier les sous-sols pour faire des travaux plus efficaces,
  représenter les transports publics en temps réel, proposer une modification de sa maison...
  Les modèles 3D urbains existent mais nécessitent des logiciels propriétaires et de grosses ressources.
  Le projet prouve qu'il est possible de mettre à disposition toute une métropole
  (ici la communauté urbaine de Bordeaux) à disposition dans le navigateur (Chrome, pour l'instant).

### Le format des réutilisations sur « [data.gouv.fr][] »
Les réutilisations publiées sur « [data.gouv.fr][] » peuvent être des fichiers téléchargées directement
(cartes, tableaux, graphiques, etc) sur le site web ou des liens qui redirigent le visiteur à voir
la réutilisation (vers le site web de start-ups, l’AppStore, GooglePlay, etc).

## Comment transformer les données ?
La donnée brute est souvent de qualité moyenne (informations manquantes, libellés à harmoniser ..),
ou doit être enrichie (par exemple en transformant un code postal en coordonnées GPS),
ou encore jointe à d'autres données (par exemple en divisant le tonnage de déchêts par le nombre d'habitants),
avant de pouvoir la traiter, notamment au travers d'un [outillage pour les datavisualisations](#dataviz).
Parfois, elle doit être extraite de documents fermés, et nécessite par exemple
d'[extraire des données PDF](http://www.open-contracting.org/exploring_senegal_public_procurements_how_we_turned_pdf_files_into_browsable_data)
ou d'[extraire des données tabulaires à partir de defaults Web](http://tools.daemonservices.com/html_to_csv/).

Une fois dans un format tabulaire (tableur, fichier texte, etc.) ou dans un format structuré (XML, JSON, RDF, ..),
[OpenRefine][] est un outil gratuit qui vous permettra de réaliser des transformations complexes
dans vos séries de données.

***Note :*** si vous travaillez sur des bases de données de plusieurs dizaines de Mo,
effectuez le [paramétrage suivant](https://github.com/OpenRefine/OpenRefine/wiki/FAQ%3A-Allocate-More-Memory).

### Fusionner plusieurs fichiers en une seule base de données
Les données se présentant souvent en séries incomplètes, par année, par département,
la première opération consiste à fabriquer un fichier complet.
Cette opération est facilitée par [OpenRefine][].
Lancer l'outil et "créer un nouveau projet".
Dans la boîte de dialogue "sélectionner les fichiers",
sélectionner tous les fichiers que vous souhaitez concaténer et que vous aurez préalablement téléchargés,
qu'il y en ait 10 ou 100.
[OpenRefine][] va automatiquement ajouter une colonne qui permettra de distinguer les différentes sources
(par exemple une colonne "département" ou "année").
Une fois vérifié, sélectionner "Export" et exporter votre base fusionnée au format CSV ou XLS.

### Travailler à plusieurs sur une même base de données
Il existe des tableurs en ligne qui permettent un travail collaboratif sur une seule et unique base de données.
Notons notamment ces outils gratuits : [Framacalc][], [Google Docs][] ou [Zoho Docs][].
Une fois votre travail terminé, vous pouvez l'exporter dans un fichier tableur classique,
ou simplement utiliser son URL, en veillant à limiter les droits d'édition à vous seul.

### Géocoder des adresses
La [Base Adresse Nationale (BAN)][ban] propose un outil permettant de géocoder rapidement des données au format CSV.

[Le formulaire disponible en ligne][ban-csv] permet d'envoyer un fichier pour géocodage
avec une limite d'approximativement 10000 adresses maximum.

Une [API publique][ban-api] permet de géocoder les adresses une à une ou en lot
([voir documentation de l'API][ban-api]).

L'IGN propose par ailleurs [un logiciel Windows gratuit](http://logiciels.ign.fr/?-Visualiseur-d-adresses-)
permettant de visualiser des données adresse,
de les géocoder avec une précision à la plaque adresse grâce à la [BD Adresse][].
Le résultat peut être imprimé ou exporté au format kml pour une exploitation dans
de nombreux outils de visualisation.

Les conditions d'utilisation sont adaptées à l'exploitation des données de « [data.gouv.fr][] »
puisque le résultat du géocodage de fichiers est librement réutilisable dès lors que les fichiers
résultants sont republiés sous [Licence ouverte][lool].

### Transformer des données géographiques en fichiers texte ou kml
L'IGN propose [IGN Map][], un logiciel gratuit permettant de visualiser des fichiers disponibles
dans l'un des nombreux formats géographiques proposés sur « [data.gouv.fr][] ».
Pour traiter un fichier shapefile (.shp), il faut choisir `Fichier/Importer/Import d'un fichier Shapefile`.
Pour un flux WMS, il faut choisir `Fichier/Importer/Connexion WMS`.

Les fichiers, une fois ouverts, peuvent être inspectés,
prévisualisés et exportés au format kml en vue d'être facilement exploités dans des outils de visualisation.
IGN Map assure également la reprojection des données depuis des projections
telles que le Lambert-93 vers des latitudes et longitudes.

### Transcoder des codes postaux en codes INSEE
Cas classique : un fichier de données se présente en codification "Code Postal",
alors que le système de visualisation en carte attend des [codes INSEE][cog].
Pour transcoder des codes postaux en code INSEE
(issu du [tutorial OpenRefine](https://github.com/OpenRefine/OpenRefine/wiki/Fetching-URLs-From-Web-Services)) :

- Add column by fetching URL, avec l'expression
  (diminuer l'intervalle entre 2 requêtes à 30 ms, par défaut il est réglé à 5 secondes) :
  ```
  "http://ou.comarquage.fr/api/v1/territory?kind=CommuneOfFrance&postal_code="+value
  ```
- Puis `Edit Cell -> Transform`, pour extraire le code INSEE du flux JSON avec l'expression
  ```javascript
  if(value.parseJson()["data"]["items"][0]["code"] != null, value.parseJson()["data"]["items"][0]["code"], value.parseJson()["data"]["code"])
  ```

### Transformer des noms de commune en coordonnées latitude-longitude
Là encore, même procédure en sélectionnant la colonne "nom de la commune" :

- Add column by fetching URL, avec l'expression
  (diminuer l'intervalle entre 2 requêtes à 30 ms, par défaut il est réglé à 5 secondes) :
  ```
  "http://ou.comarquage.fr/api/v1/autocomplete-territory?&term="+escape(value, "url")
  ```
- Puis `Edit Column -> Add column based this column`, avec l'expression
  ```javascript
  if(value.parseJson()["data"]["items"][0]["latitude"] != null, value.parseJson()["data"]["items"][0]["latitude"], value.parseJson()["data"]["latitude"])
  ```
- Puis `Edit Column -> Add column based on this column`, avec l'expression
  ```javascript
  if(value.parseJson()["data"]["items"][0]["longitude"] != null, value.parseJson()["data"]["items"][0]["longitude"], value.parseJson()["data"]["longitude"])
  ```

### Géocoder précisément des adresses
Dans [OpenRefine][], sélectionner la colonne "Adresse" de votre fichier :
`Add column by fetching URL`, avec l'expression
(diminuer l'intervalle entre 2 requêtes à 30 ms, par défaut il est réglé à 5 secondes) :

- Si il existe une colonne `CP` contenant le code postal:
  ```
  "http://ou.comarquage.fr/api/v1/geocode?postal_code="+cells["CP"].value+"&street_address="+escape(value, "url")
  ```
- Si il existe une colonne `INSEE` contenant le code INSEE:
  ```
  "http://ou.comarquage.fr/api/v1/geocode?code="+cells["INSEE"].value+"&street_address="+escape(value, "url")
  ```

### Transformer des données Shape (SHP) en GeoJSON
Les fichiers des outils géomatiques ne s'ouvrent pas aisément dans l'univers Internet,
il faut les convertir en [GeoJSON][].
Un convertisseur en ligne, [OGRE][] permet simplement cette conversion.
Utiliser EPSG:4326 comme système de projection cible (Target SRS).
Le GeoJSON obtenu peut ensuite être intégré sur une carte OpenStreet Map
grâce à l'outil [uMap][] en cliquant sur le bouton en forme de flèche "Importer des données" à droite.

### Transformer les fichiers électoraux du ministère de l'Intérieur
Lorsque l'offre électorale n'est pas similaire sur l'ensemble du territoire,
les fichiers de résultats électoraux diffusés par le Ministère de l'Intérieur ne sont pas tabulaires.
Joël Gombin a développé [un package sous R](https://github.com/joelgombin/LireMinInterieur/)
pour transformer ces fichiers en données tabulaires, en agrégeant les résultats par nuance politique.

<span id="dataviz"></span>
## Quels outils pour les datavisualisations ?
Une série de données peut souvent faire l'objet d'une représentation graphique, sous différentes formes, que nous détaillons ici. Avant d'utiliser un de ces moteurs de rendus, vous devrez peut-être transformer des données pour les nettoyer ou les enrichir.

### Des graphiques simples

![Évolution du nombre d'opérateurs bio](/img/faq/outils/800px-Evolutionbio.png)
*Exemple : évolution du nombre d'opérateurs bio*

Les tableurs du marché (**OpenOffice Calc**, **Excel**, **Google Spreadsheet**...)
permettent de réaliser rapidement des graphiques classiques,
comme des histogrammes ou des camemberts.
Voir par exemple le
[Nombre d'acteurs engagés dans l'agriculture bio](http://www.data.gouv.fr/fr/datasets/agriculture-biologique-2008-2011-nombre-d-operateurs-engages-en-agriculture-biologique-30378896/).

Une fois votre graphique réalisé dans votre tableur,
cliquez avec le bouton droit et sélectionner "Enregistrer en tant qu'image".
Publiez cette image sur un site Web, comme un blog, ou un dossier Public.
Des outils strictement en ligne comme [DataWrapper][]
vous permettent également de partager en quelques clics un graphique en ligne.
Il suffit de se créer un compte et de copier/coller les données issues du tableur ...

Vous pouvez alors créer un **Elément lié** dans le jeu de données concerné par votre visualisation.
N'oubliez pas de renseigner un titre concis et clair,
et une description permettant aux Internautes de découvrir votre travail.

### Des cartes
Des cartes synthétiques par commune, département, région

![Carte de France de l'intensité des aides PAC par département](/img/faq/outils/PAC2012.jpg)
*Exemple : Carte de France de l'intensité des aides PAC par département*

[FranceO3][] permet de réaliser des cartes interactives et de les publier gratuitement.
Cette solution charge **une valeur par niveau d'agrégation**
(par exemple une dépense par commune, un nombre de naissance par département ou par région).

En haut à droite, cliquer sur "Charger", puis "Charger des données personnelles".
Sélectionner le niveau de granularité souhaité
(commune avec arrondissements des grandes villes, département, région)
et adaptez vos données sources aux exigences indiquées.
Attention, au niveau commune, le moteur attend des codes INSEE, pas de codes postaux.
Au niveau département, le moteur attend des numéros, pas des noms (et des '01, '09 pour les premiers départements).
Enfin, supprimer tout formatage de type %, ne laisser que les chiffres.

Ensuite, copiez-collez-les depuis votre tableur.
Exportez votre résultat sous forme d'image A3, ou mieux, sous forme de carte interactive :
avant la visualisation, sélectionner "Sauvegarder mon travail au format TJS",
et déposez le fichier généré (XML) sur un site Web, un blog ou un répertoire partagé.
L'URL de votre dataviz est alors
`http://franceo3.geoclip.fr/index.php?tjs_file=http://monsite.fr/toto.xml`.

Il est aussi possible de charger des données ponctuelles,
à partir de fichiers de points localisés par leurs coordonnées géographiques.
La procédure d'import par copier-coller est similaire à celle de l'import de données localisées
à partir d'un code géographique (code commune, code postal, code département...)

Plus de détails :
[toute la documentation Geoclip](http://geoclip.fr/aide/o3/fr/geoclip_o3_utilisateur.htm).

### Des cartes affichant des points d'intérêt

Il s'agit d'afficher des points géocodés par adresse ou coordonnées latitude-longitude.
Plusieurs solutions sont disponibles.

![Carte des immeubles protégés 1/2](/img/faq/outils/800px-CartePOI.png)
*Exemple : carte des immeubles protégés 1/2*

[Batchgeo][] est une solution rapide et efficace pour copier/coller jusqu'à 250 points
(un compte pro est nécessaire pour aller au-delà), en disposant simplement de leur adresse.
Explorer les options avancées vous permet notamment de regrouper les points à forte densité,
ou selon une de vos données (par exemple l'année de construction).
Prenez le temps de travailler sur un échantillon pour valider le géocodage de vos données
avant de lancer la totalité.

![Carte des immeubles protégés 2/2](/img/faq/outils/800px-TileMill.png)
*Exemple : carte des immeubles protégés 2/2*

[MapBox][] permet de publier des cartes simplement.
Pour importer de nombreux points, il faudra installer [TileMill][], un outil Mac/PC/Linux gratuit.
Ajouter une "layer" (menu en bas à gauche) qui va utiliser votre source de données
(elle doit contenir une colonne latitude et une colonne longitude) et cliquer sur "Save & Style".
Attention utiliser l'option `encoding="cp1252"` dans l'import si vous exportez un fichier TXT Windows
depuis Excel par exemple.
Dans le menu en bas à gauche, sélectionner la "main" permet d'ajouter des labels sur vos points,
en mode Rollover et au clic.
Une fois votre travail terminé, le sauvegarder (attention à la taille du fichier)
et l'exporter vers votre compte MapBox pour la diffuser,
comme [cet exemple](https://a.tiles.mapbox.com/v3/ppezziardi.z982gldi/default.html?secure=1#2/0/0).

### Des cartes affichant des points, des zones

![Périmètres des monuments historiques Haut-Rhin](/img/faq/outils/800px-OSM-cadastre.png)
*Périmètres des monuments historiques Haut-Rhin*

[uMap][] permet de créer des cartes personnalisées sur des fonds OpenStreetMap en un instant.
[uMap][] offre également la possibilité d'afficher votre carte sur votre site.
Après avoir créé une carte pour votre projet,
vous pourrez importer votre jeu de données depuis un fichier (formats supportés : geojson, csv, gpx, kml, osm),
personnaliser les options d'affichage et sauvegarder votre carte dans un espace personnel.
En particulier, il est très simple de changer de fonds de carte, y compris ceux distribués par l'IGN.

Pour obtenir le fond de carte cadstral par exemple, dans "Editer les paramètres", "Fonds de carte Custom" : indiquer l'URL `http://wxs.ign.fr/rmd2sk63vgo9ohhx0n2m0h3u/geoportail/wmts?SERVICE=WMTS&REQUEST=GetTile&VERSION=1.0.0&LAYER=CADASTRALPARCELS.PARCELS&STYLE=normal&TILEMATRIXSET=PM&TILEMATRIX={z}&TILEROW={y}&TILECOL={x}&FORMAT=image%2Fpng`
(il est possible de remplacer CADASTRALPARCELS.PARCELS par
un des [fonds de carte IGN](http://api.ign.fr/tech-docs-js/fr/webmaster/layers.html).
*Attention à penser à modifier l'extension de image/png de l'exemple en image/jpeg pour les couches ortho et scan*).

[uMap][] est aussi un logiciel libre,
et vous pouvez donc installer votre propre instance sur vos serveurs et la personnaliser.

Exemples d'utilisation :
[périmètres des monuments historiques Haut-Rhin](http://umap.openstreetmap.fr/fr/map/perimetres-monuments-historiques-sur-fond-cadastra_8355#11/48.0934/7.3193),
[carte de dommages aux cultures](http://www.fao.org/emergencies/crisis/philippines-typhoon-haiyan/crop-damages-map/en/),
[bureaux de vote de la commune d'Oullins](http://umap.openstreetmap.fr/fr/map/bureaux-de-vote-oullins_4039#16/45.7135/4.8042)

![répartition des salons de coiffure à Paris](/img/faq/outils/Heatmap-salons-coiffure-paris-opendatasoft.png)
*Exemple : répartition des salons de coiffure à Paris*

Un outil de création de cartes interactives mis à disposition par [OpenDataSoft][]
est disponible sur les portails de
[la Région Île-de-France](http://data.iledefrance.fr/map),
[la Mairie de Paris](http://opendata.paris.fr/map),
[la Ville d'Issy-les-Moulineaux](http://data.issy.com/map),
[la Collectivité Territoriale de Corse](http://data.corse.fr/map),
[le Ministère de l'Enseignement Supérieur et de la Recherche](http://data.enseignementsup-recherche.gouv.fr/map)
et [SNCF](http://ressources.data.sncf.com/map).
Il permet de superposer différents jeux de données avec une configuration fine
(pictogrammes, clusters, heatmap...).
Une fois terminée, pour diffuser votre carte, il suffit de copier-coller l'URL indiqué sous "Partager".

*Exemple de réutilisation:*
[carte des hôtels classés en Île-de-France](http://data.iledefrance.fr/map/embed/?layers=W3sidGl0bGUiOiJI9HRlbHMgMSDpdG9pbGUgZW4gSURGIiwicGljdG8iOiJvZHNwaWN0by1zdGFyLTEiLCJjb2xvciI6IiM0NTJCNzIiLCJhY3RpdmVEYXRhc2V0cyI6W3siZGF0YXNldGlkIjoibGVzX2hvdGVsc19jbGFzc2VzX2VuX2lsZS1kZS1mcmFuY2UiLCJjb2xvciI6IiM0NTJCNzIiLCJwaWN0byI6Im9kc3BpY3RvLXN0YXItMSIsImNsdXN0ZXJNb2RlIjoicG9seWdvbiIsImZ1bmMiOiJDT1VOVCIsIm1hcmtlciI6dHJ1ZSwic2VhcmNoUGFyYW1ldGVycyI6eyJyZWZpbmUuY2xhc3NlbWVudCI6IjEg6XRvaWxlIn0sImV4cHIiOiJkZXB0In1dLCJkaXNwbGF5ZWQiOnRydWUsImRlc2NyaXB0aW9uIjoiU291cmNlOlxuaHR0cDovL2RhdGEuaWxlZGVmcmFuY2UuZnIvZXhwbG9yZS9kYXRhc2V0L2xlc19ob3RlbHNfY2xhc3Nlc19lbl9pbGUtZGUtZnJhbmNlLz90YWI9bWV0YXMifSx7InRpdGxlIjoiSPR0ZWxzIDIg6XRvaWxlcyBlbiBJREYiLCJwaWN0byI6Im9kc3BpY3RvLXN0YXItMiIsImNvbG9yIjoiIzEyN0E5NyIsImFjdGl2ZURhdGFzZXRzIjpbeyJkYXRhc2V0aWQiOiJsZXNfaG90ZWxzX2NsYXNzZXNfZW5faWxlLWRlLWZyYW5jZSIsImNvbG9yIjoiIzEyN0E5NyIsInBpY3RvIjoib2RzcGljdG8tc3Rhci0yIiwiY2x1c3Rlck1vZGUiOiJwb2x5Z29uIiwiZnVuYyI6IkNPVU5UIiwibWFya2VyIjp0cnVlLCJzZWFyY2hQYXJhbWV0ZXJzIjp7InJlZmluZS5jbGFzc2VtZW50IjoiMiDpdG9pbGVzIn0sImV4cHIiOiJkZXB0In1dLCJkaXNwbGF5ZWQiOnRydWUsImRlc2NyaXB0aW9uIjoiU291cmNlOlxuaHR0cDovL2RhdGEuaWxlZGVmcmFuY2UuZnIvZXhwbG9yZS9kYXRhc2V0L2xlc19ob3RlbHNfY2xhc3Nlc19lbl9pbGUtZGUtZnJhbmNlLz90YWI9bWV0YXMifSx7InRpdGxlIjoiSPR0ZWxzIDMg6XRvaWxlcyBlbiBJREYiLCJwaWN0byI6Im9kc3BpY3RvLXN0YXItMyIsImNvbG9yIjoiIzEzODgwOCIsImFjdGl2ZURhdGFzZXRzIjpbeyJkYXRhc2V0aWQiOiJsZXNfaG90ZWxzX2NsYXNzZXNfZW5faWxlLWRlLWZyYW5jZSIsImNvbG9yIjoiIzEzODgwOCIsInBpY3RvIjoib2RzcGljdG8tc3Rhci0zIiwiY2x1c3Rlck1vZGUiOiJwb2x5Z29uIiwiZnVuYyI6IkNPVU5UIiwibWFya2VyIjp0cnVlLCJzZWFyY2hQYXJhbWV0ZXJzIjp7InJlZmluZS5jbGFzc2VtZW50IjoiMyDpdG9pbGVzIn0sImV4cHIiOiJkZXB0In1dLCJkaXNwbGF5ZWQiOnRydWUsImRlc2NyaXB0aW9uIjoiU291cmNlOlxuaHR0cDovL2RhdGEuaWxlZGVmcmFuY2UuZnIvZXhwbG9yZS9kYXRhc2V0L2xlc19ob3RlbHNfY2xhc3Nlc19lbl9pbGUtZGUtZnJhbmNlLz90YWI9bWV0YXMifSx7InRpdGxlIjoiSPR0ZWxzIDQg6XRvaWxlcyBlbiBJREYiLCJwaWN0byI6Im9kc3BpY3RvLXN0YXItNCIsImNvbG9yIjoiI0ZGNzUxOCIsImFjdGl2ZURhdGFzZXRzIjpbeyJkYXRhc2V0aWQiOiJsZXNfaG90ZWxzX2NsYXNzZXNfZW5faWxlLWRlLWZyYW5jZSIsImNvbG9yIjoiI0ZGNzUxOCIsInBpY3RvIjoib2RzcGljdG8tc3Rhci00IiwiY2x1c3Rlck1vZGUiOiJwb2x5Z29uIiwiZnVuYyI6IkNPVU5UIiwibWFya2VyIjp0cnVlLCJzZWFyY2hQYXJhbWV0ZXJzIjp7InJlZmluZS5jbGFzc2VtZW50IjoiNCDpdG9pbGVzIn0sImV4cHIiOiJkZXB0In1dLCJkaXNwbGF5ZWQiOnRydWUsImRlc2NyaXB0aW9uIjoiU291cmNlOlxuaHR0cDovL2RhdGEuaWxlZGVmcmFuY2UuZnIvZXhwbG9yZS9kYXRhc2V0L2xlc19ob3RlbHNfY2xhc3Nlc19lbl9pbGUtZGUtZnJhbmNlLz90YWI9bWV0YXMifSx7InRpdGxlIjoiSPR0ZWxzIDUg6XRvaWxlcyBlbiBJREYiLCJwaWN0byI6Im9kc3BpY3RvLXN0YXItNSIsImNvbG9yIjoiI0JGMEM0MyIsImFjdGl2ZURhdGFzZXRzIjpbeyJkYXRhc2V0aWQiOiJsZXNfaG90ZWxzX2NsYXNzZXNfZW5faWxlLWRlLWZyYW5jZSIsImNvbG9yIjoiI0JGMEM0MyIsInBpY3RvIjoib2RzcGljdG8tc3Rhci01IiwiY2x1c3Rlck1vZGUiOiJwb2x5Z29uIiwiZnVuYyI6IkNPVU5UIiwibWFya2VyIjp0cnVlLCJzZWFyY2hQYXJhbWV0ZXJzIjp7InJlZmluZS5jbGFzc2VtZW50IjoiNSDpdG9pbGVzIn0sImV4cHIiOiJkZXB0In1dLCJkaXNwbGF5ZWQiOnRydWUsImRlc2NyaXB0aW9uIjoiU291cmNlOlxuaHR0cDovL2RhdGEuaWxlZGVmcmFuY2UuZnIvZXhwbG9yZS9kYXRhc2V0L2xlc19ob3RlbHNfY2xhc3Nlc19lbl9pbGUtZGUtZnJhbmNlLz90YWI9bWV0YXMifV0%3D&viewport=48.206371336358906,0.8184814453125,49.15656228453343,4.3341064453125)
([Fiche du jeu de données](https://www.data.gouv.fr/dataset/la-carte-des-hotels-classes-en-ile-de-france-idf))

[Tutoriel vidéo](https://vimeo.com/84581978)

[GEOPLAY.FR][] est une application d'illustration cartographique en ligne.

![Inventaire Poitou-Charentes](/img/faq/outils/800px-Inventaire_du_patrimoine_Poitou-Charentes.png)
*Exemple : Inventaire Poitou-Charentes*

L'utilisation de la version 1.0 est gratuite et fourni les fonctionnalités suivantes:

- Edition de lignes, de polygones et de formes.
- Edition html simplifiée des marqueurs et légendes.
- Intégration de points par .csv, .xls, .json, .kml ou placement direct.
- Intégration d'itinéraires via .kml, .json.
- Fonds Open Street Map, scriptable (.js), exports autonomes ou .pdf.
- Géo-localisation des adresses postales via le module bano.
- Permet de gérer plusieurs milliers de points d'intérêts.
- Interface graphique et publication instantanée.
- Multiples vues pour une même carte.
- Définition des zooms par vues et par marqueurs.
- Cartes hors ligne totalement indépendantes.
- Cartes exportables sous forme d'archives.

![Inventaire Poitou-Charentes](/img/faq/outils/800px-Inventaire_du_patrimoine_vecteurs.png)
*Exemple : Inventaire Poitou-Charentes*

### Des infographies animées

![Exemple : graphique à bulles](/img/faq/outils/Dependencies.png)
*Exemple : graphique à bulles*

Certaines données correspondent à des séries temporelles qu'il est intéressant de visualiser dynamiquement,
par exemple [L'intensité des aides de la PAC par année, par département](https://www.google.com/publicdata/explore?ds=z58rtgk6fal3a4_&ctype=b&strail=false&bcs=d&nselm=s&met_y=Concentration&scale_y=lin&ind_y=false&met_x=Exploitations&scale_x=lin&ind_x=false&met_s=Total_aide&scale_s=lin&ind_s=false&idim=Departement:Martinique:Reunion:Guadeloupe:Paris:Val-de-Marne:Guyane:Cotes+d%27Armor:Ille-et-Vilaine:Finistere:Maine-et-Loire&ifdim=Departement&ind=false&icfg&iconSize=0.5&draft).

[Google Public Data][] est un outil gratuit permettant de réaliser de telles animations.

Installez l'utilitaire [DSPLGen](https://developers.google.com/public-data/docs/dsplgen)
sur votre Mac ou votre PC.

A partir de vos données, générez votre fichier dataset.xml et ses ressources tel qu'explicité dans le guide.
Dans le fichier généré dataset.xml,
prenez soin de remplacer les différentes lignes `*** INSERT PROVIDER NAME ... ***`,
`*** INSERT CONCEPT NAME ... ***` par vos informations.

Ensuite, téléchargez une archive des fichiers générés dans
[votre espace personnel Public Data](https://www.google.com/publicdata/directory),
en sélectionnant "Mes ensembles de données" dans le menu de gauche, en bas.
Une fois le chargement réussi, et la visualisation testée
(attention, vérifiez bien que l'URL fonctionne quand votre navigateur n'est pas connecté à Google),
n'oubliez pas de la rendre publique en cliquant sur "Sharing Settings" dans le jeu de données.

### Des Treemaps, des diagrammes en bulle, diagrammes alluviaux

![Exemple : diagramme alluvial](/img/faq/outils/Alluvial.png)
*Exemple : diagramme alluvial*

L'outil RAW par Densitydesign permet de copier/coller très simplement des données issues d'un tableur,
et de sélectionner son type de graphique.

Le resultat peut être intégré ensuite à une default Web, par copier/coller.

<span id="opendatacamps"></span>
## Qu'est-ce qu'un Open Data Camps ?
Des passionnés de la donnée se retrouvent une journée entière
pour améliorer les données de la plate-forme « [data.gouv.fr][] », c’est à dire les mettre en formats ouverts,
fusionner des fichiers, détecter des erreurs, produire des visualisations et de nouvelles interprétations.
Les travaux engagés aboutiront sur des résultats concrets,
donc réalisables et démontrables sur la plate-forme à la fin de la journée.

Vous êtes les acteurs de cette journée :
producteurs de données issus de l'administration, datascientists, chercheurs, codeurs,
designers, associations, experts du réseau Etalab,
et toutes sortes de bonnes volontés travailleront ensemble dans des ateliers qu’ils auront choisis.
Si vous possédez un ordinateur portable, n’oubliez pas de venir avec !

### Règles du jeu
- Les personnes présentes sont les bonnes personnes : 3 participants, c'est cool, 100 participants, c'est cool.
- Notre **BUT** :
  - produire ou référencer de nouveaux jeux de données
  - améliorer un jeu de données existant : fusionner des fichiers, enrichir, nettoyer, géocoder, etc.
  - produire et référencer une réutilisation : un site web, un page de blog, une datavisualisation,
    un mini-site Web, une application mobile qui prouve son utilité ..
- Chacun peut proposer une **Formation** (démonstration d'un outil, ..)
  ou un **Atelier** (sourcer des données, fabriquer un nouveau jeu de données,
  créer une application exploitant des données)
- Chacun choisit les ateliers ou les formations auxquels il participe,
  il en change à tout moment (on vote avec ses pieds)
- Toute personne est une ressource potentielle pour un atelier, accueillez-la avec bienveillance
- Si vous n'êtes pas d'accord, ne faites pas l'un **ou** l'autre, faites l'un **et** l'autre
- C'est **cool**

[Voir la vidéo](http://www.modernisation.gouv.fr/ladministration-change-avec-le-numerique/par-louverture-des-donnees-dans-les-administrations/video-un-open-data-camp-c-est-quoi)


[data.gouv.fr]: https://www.data.gouv.fr
[Etalab]: https://www.etalab.gouv.fr
[Dataconnexions]: https://www.data.gouv.fr/fr/dataconnexions
[OpenRefine]: http://openrefine.org/
[Framacalc]: https://framacalc.org/
[Google Docs]: https://docs.google.com/
[Zoho Docs]: https://www.zoho.com/docs/
[ban]: https://adresse.data.gouv.fr/
[ban-csv]: https://adresse.data.gouv.fr/csv/
[ban-api]: https://adresse.data.gouv.fr/api/
[BD Adresse]: https://professionnels.ign.fr/bdadresse
[lool]: https://www.etalab.gouv.fr/licence-ouverte-open-licence
[IGN Map]: https://logiciels.ign.fr/?-IGNMap,12-
[cog]: https://www.insee.fr/fr/methodes/nomenclatures/cog/
[OGRE]: http://ogre.adc4gis.com/
[GeoJSON]: http://geojson.org/
[uMap]: https://umap.openstreetmap.fr/fr
[DataWrapper]: https://www.datawrapper.de/
[FranceO3]: https://franceo3.geoclip.fr/
[Batchgeo]: https://www.batchgeo.com/fr/
[MapBox]: https://www.mapbox.com/
[TileMill]: https://tilemill-project.github.io/tilemill/
[OpenDataSoft]: https://www.opendatasoft.com/
[GEOPLAY.FR]: https://geoplay.fr
[Google Public Data]: https://www.google.com/publicdata/directory
