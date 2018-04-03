# Abrir e publicar Dados

Esta secção explica alguns príncipios básicos de abrir dados e o acesso às funcionalidades de carregamento de conjuntos de dados abertos no portal. 

Para processos de carregamento e integração automática com o portal, consulte a documentação da API.

## Quem pode publicar dados em dados.gov?

O dados.gov é um portal vocacionado para a abertura de dados por parte de organismos e entidades da Administração Pública, conforme caracterizadas pelo [art. 4º da Lei n.º26/2016, de 22 de Agosto](http://www.pgdlisboa.pt/leis/lei_mostra_articulado.php?nid=2591&tabela=leis&ficha=1&pagina=1&so_miolo= "Lei nº26/2016 de 22 de Agosto"), mas qualquer cidadão ou organização pode registar-se no portal e carregar, ou referenciar, dados que considere de interesse público.

## Certificação de organismos públicos

De modo a diferenciar os conjuntos de dados provenientes de fontes oficiais do Estado, as organizações e entidades da Administração Pública serão certificadas com um selo de "Fornecedor Oficial". A certificação pode ser pedida através do e-mail dados@ama.pt.

## O que é um "conjunto de dados"?

>Um conjunto de dados, publicados ou geridos por um único agente, e disponibilizado para acesso ou download atavés de um ou mais formatos.
>
>--W3C Data Catalogue Vocabulary ([DCAT](http://www.w3.org/TR/2014/REC-vocab-dcat-20140116/))

Conjuntos de dados, no contexto dos dados abertos públicos, são agrupamentos de dados em formato digital, dedicados a um tema específico. Uma lista de moradas de serviços de atendimento ao público, por exemplo, ou dados mensais sobre práticas de gestão ou contratação de um organismo público.

No dados.gov, um único conjunto de dados pode ter vários recursos associados.

Por exemplo, podemos criar um conjunto específico que disponibiliza a mesma informação em formatos diferentes (para que se adeque a diferentes tipos de reutilização):

![Exemplo](https://raw.githubusercontent.com/amagovpt/docs.dados.gov.pt/master/img/ex%20dataset%20recursos.JPG)

Ou podemos criar um conjunto de dados relativo a um período temporal definido (i.e. ano, mês, outro) e carregar uma série de recursos sequenciais:

![Exemplo recursos sequenciais](https://raw.githubusercontent.com/amagovpt/docs.dados.gov.pt/master/img/ex%20dataset%20recursosv21.JPG)

## Publicar conjuntos de dados em dados.gov

Para publicar um conjunto de dados neste portal é necessário criar uma conta de utilizador, ou, no caso de já estar registado, efetuar a autenticação, e escolher a opção "Contribuir". Pode também carregar no ícone "+" a partir da zona de administração (backoffice).

De seguida deverá seleccionar ou criar uma organização para publicar os dados. Poderá também fazê-lo em nome individual (não recomendado para organismos públicos).

Depois deverá caracterizar o conjunto de dados e carregar o(s) recurso(s) associado(s), ou indicar o link onde se encontram os dados - mais informação nos pontos seguintes.

## Carregar dados ou indexar?

A opção de carregar ou indexar (_linkar_) os dados está totalmente do lado do organismo fornecedor. 

A AMA recomenda que organismos que possuam as suas próprias páginas ou portais web alojem os ficheiros nesses portais, e passem a referenciá-los através da indicação do URL (ou de uma API, caso exista) em dados.gov. Nesta situação, o organismo fornecedor apenas preocupar-se-á com a gestão dos dados na sua fonte de origem, sendo a indexação no dados.gov feita automaticamente ao longo do tempo.

No caso do organismo não possuir uma infrastura web que considere adequada para disponibilizar e manter dados, poderá carregá-los diretamente através do backoffice ou da API do dados.gov.

No caso de organismos que possuam os seus próprios portais ou catálogos de dados abertos, o processo de publicação poderá ser feito através de um _harvester_, que recolhe a metainformação sobre esses conjuntos de dados de forma regular e completamente automatizada. A configuração do _harvester_ é feita pela AMA, com a colaboração da entidade, se necessário.

## Como identificar conjuntos de dados para publicação?

No caso de não existirem ainda vários conjuntos de dados delimitados e estruturados num organismo, que possam ser imediatamente abertos, podemos começar por abrir apenas um subconjunto desses dados.

Podemos começar por considerar disponibilizar informação que já está disponível ao público, seja sob a forma de conteúdos num site ou através de pedidos à organização, sob a forma menos "tratada" de conjuntos de dados. Aqui é patente a vantagem de disponibilizar dados em bruto, em formatos abertos e lidos por máquina, de forma a privegiar a sua reutilização de forma livre.

Regra geral, são especialmente apreciados pelos reutilizadores dados que privilegiem preocupações como:

*	Acesso às entidades, serviços disponíveis e pontos de atendimento;
*	Transparência das contas, atividades e recursos da entidade;
*	Monitorização de um tema, setor ou área de interesse público.

É muito importante estabelecer também um compromisso de manutenção e atualização dos dados. Nesse sentido, e embora o esforço inicial seja um pouco mais elevado, é recomendável a utilização de mecanismos automatizados (ex. API), para garantir que o processo decorra de forma regular.

### Dados com informação geográfica

Nos dados a abrir deverá ser dedicada uma atenção e esforço especiais à georreferenciação da informação, porque eleva significativamente o interesse e o potencial de utilização dos dados abertos. Ao enriquecer um conjunto de dados com campos de referência geográfica, a entidade está a abrir o potencial para o desenvolvimento de aplicações que permitem visualizar os dados sobre um mapa. E estas são aplicações bastante apreciadas quer por utilizadores finais quer pela comunidade de desenvolvimento, porque permitem navegar nos dados de forma mais intuitiva e agradável e porque impulsionam a criação apps para dispositivos móveis. 

### Interagir com os reutilizadores

A interação com a comunidade de reutilizadores poderá fornecer pistas preciosas sobre o tipo de dados a disponibilizar. 

O organismo poderá fazer algum tipo de consulta pública e perguntar aos seus interlocutores mais frequentes, ou a outras partes interessadas, a que tipo de dados gostaria de ter acesso.

A AMA também poderá ajudar neste processo, incluindo colaborar na organização de workshops / eventos com vista a promover estas interacções, contacte-nos em dados@ama.pt.










