# Publicar Dados

Esta secção explica alguns princípios básicos sobre publicação e acesso às funcionalidades de **carregamento de conjuntos de dados abertos no portal**. 

Para processos de carregamento e integração automática com o portal, consulte a documentação da [API](/apidoc/).

## Quem pode publicar dados em dados.gov?

O dados.gov é um portal vocacionado para a abertura de dados por parte de organismos e entidades da Administração Pública, conforme caracterizadas pelo [art. 4º da Lei n.º26/2016, de 22 de Agosto](http://www.pgdlisboa.pt/leis/lei_mostra_articulado.php?nid=2591&tabela=leis&ficha=1&pagina=1&so_miolo= "Lei nº26/2016 de 22 de Agosto"), **mas qualquer cidadão ou organização pode registar-se no portal e carregar, ou referenciar, dados que considere de interesse público**.


## Como publicar conjuntos de dados em dados.gov

Para publicar um conjunto de dados neste portal é necessário criar uma conta de utilizador, ou, no caso de já estar registado, efetuar a autenticação. Depois de criada uma conta e de entrar com registo no portal, basta escolher a opção "Contribuir". Pode também carregar no ícone "+" a partir da zona de administração (backoffice).

De seguida deverá selecionar ou criar uma organização para publicar os dados. Poderá também fazê-lo em nome individual (não recomendado para organismos públicos).

Depois deverá caracterizar o conjunto de dados e carregar o(s) recurso(s) associado(s), ou indicar o link onde se encontram os dados.


## Conjuntos de dados e recursos

**No dados.gov, um único conjunto de dados pode ter vários recursos (ficheiros) associados**.

Por exemplo, podemos criar um conjunto específico que disponibiliza a mesma informação em formatos diferentes (para que se adeque a diferentes tipos de reutilização):

![Exemplo](https://raw.githubusercontent.com/amagovpt/docs.dados.gov.pt/master/img/ex%20dataset%20recursos.JPG)

Ou podemos criar um conjunto de dados relativo a um período temporal definido (i.e. ano, mês, outro) e carregar uma série de recursos sequenciais:

![Exemplo recursos sequenciais](https://raw.githubusercontent.com/amagovpt/docs.dados.gov.pt/master/img/ex%20dataset%20recursosv21.JPG)


## Carregar dados ou indexar?

A opção de carregar ou indexar (_linkar_) os dados está totalmente do lado do organismo fornecedor. 

A AMA recomenda que organismos que possuam as suas próprias páginas ou portais web alojem os ficheiros nesses portais, e passem a referenciá-los através da indicação do URL (ou de uma API, caso exista) em dados.gov. Nesta situação, o organismo fornecedor preocupa-se apenas com a gestão dos dados na sua fonte de origem, sendo a indexação no dados.gov feita automaticamente ao longo do tempo.

No caso do organismo não possuir uma infraestrutura web que considere adequada para disponibilizar e manter dados, poderá carregá-los diretamente através do backoffice ou da API do dados.gov.

No caso de organismos que possuam os seus próprios portais ou catálogos de dados abertos, o processo de publicação poderá ser feito através de um _harvester_, que recolhe a metainformação sobre esses conjuntos de dados de forma regular e completamente automatizada. A configuração do _harvester_ é feita pela AMA, com a colaboração da entidade, se necessário.


## Certificação de organismos públicos

De modo a diferenciar os conjuntos de dados provenientes de fontes oficiais do Estado, as organizações e entidades da Administração Pública serão certificadas com um selo de "Fornecedor Oficial". A certificação pode ser pedida através do e-mail dados@ama.pt.

