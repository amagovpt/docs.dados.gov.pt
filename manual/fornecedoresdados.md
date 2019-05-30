# Guia integração no dados.gov para entidades públicas

No dados.gov as entidades fornecedoras possuem controlo e autonomia relativa à forma como gerem e disponibilizam a informação. As entidades poderão criar conta de utilizador, carregar datasets e gerir os conteúdos associados às respetivas páginas sem necessidade de intervenção da AMA. Mais informações em na página [Publicar Dados na área de documentação do portal](https://dados.gov.pt/pt/docs/publish/).

Através destas funcionalidade é possível carregar manualmente, efetuando upload, conjuntos de dados e respestivos recursos (ficheiros associados). O carregamento de datasets é apenas recomendado apenas para entidades que não possuam infrastruturas de alojamento de dados.

**A AMA recomenda que os dados estejam alojados nos sistemas das entidades fornecedoras, seja através de ficheiros, serviços ou portais de dados, sem nessidade de os duplicar no dados.gov. Neste cenário, o portal nacional indexa apenas a metainformação dos dados e não os dados em si**.

Existem várias diferentes maneiras de otimizar a integração dados com o dados.gov.

* carregar automaticamente através da API
* utilizar ligações permanentes para indexar datasets
* expôr a informação de catálogo para que seja indexada (através de um _harverster_) pelo dados.gov

## Carregar automaticamente através da API

Utilizar a API para criar rotinas automáticas de carregamento e atualização de dados no portal. Mais informação na página de [documentação da API](https://dados.gov.pt/pt/apidoc/).

## Utilizar ligações permanentes para indexar datasets

Para entidades que disponibilizem poucos conjuntos de dados, e no caso dos recursos de um conjunto de dados estarem sempre associados um URL que não altere à medida que esses dados forem atualizados, só será necessário publicar o conjunto uma primeira vez no dados.gov.

## Expôr a informação de catálogo para que seja indexada

A forma mais eficiente de assegurar a catalogação e indexação de conjuntos de dados publicados por outras entidades (nas suas plataformas ou portais) é através do obtenção desses catálogos através da criação de um mecanismo de _harvesting_ no dados.gov.

Para que esse mecanismo seja criado, é necessário que as entidades exponham a informação relativa ao seu catálogo num ponto web. Essa informação deverá conter os elementos principais de metainformação relativo aos datasets, para que possam ser indexados e apresentados no dados.gov. 

Exemplos de catálogos:

* [Catálogo do dados.gov](https://dados.gov.pt/catalog)
* [Catálogo do Portal Turismo Portugal - Dados Abertos](http://dadosabertos.turismodeportugal.pt/data.json)
* [Catálogo do portal da Transparência SNS](https://transparencia.sns.gov.pt/api/v2/catalog/exports/rdf) 

As plataformas mais comuns para partilha de dados abertos (ex. CKAN, DKAN, OpenDataSoft, uDATA, entre outros) já disponibilizam esta informação por defeito, sendo facilmente integráveis com o dados.gov.

Nalguns casos, em que exista já outro tipo de catálogo, a equipa da AMA poderá estudar o desenvolvimento de um _harvester_ à medida.

Nos casos em que exista interesse em construir este mecanismo de catálogo, deverá ser utilizado o standard [DCAT Application Profile for data portals in Europe (DCAT-AP)](https://joinup.ec.europa.eu/solution/dcat-application-profile-data-portals-europe), concebido especificamente para este tipo de interoperabilidade e que pode ser integrado em diferentes formatos.

Para mais informações, contacte dados@ama.pt. 
