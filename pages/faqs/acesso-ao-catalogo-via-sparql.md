# Consultar o Catálogo do dados gov com SPARQL


## O que é o SPARQL?

O **SPARQL** (SPARQL Protocol and RDF Query Language) é uma linguagem de interrogação desenvolvida para consultar dados estruturados em grafos, normalmente representados no formato **RDF** (Resource Description Framework).
Esta linguagem permite a formulação de consultas complexas e expressivas, facilitando a extração, filtragem e combinação de informação proveniente de diversas fontes interligadas.


## Para que serve no dados gov? 

No contexto do portal **dados.gov.pt**, o SPARQL é utilizado para aceder e explorar os **metadados dos conjuntos de dados abertos** disponibilizados.
Através desta linguagem, é possível:
- Consultar títulos, descrições, datas de publicação e de atualização dos conjuntos de dados;
- Filtrar conjuntos de dados por organização ou por etiquetas;
- Integrar dados com outras fontes externas compatíveis com RDF;
- Automatizar a recolha de informação para aplicações e análises.

Este acesso semântico promove a **interoperabilidade, a reutilização da informação pública** e a criação de soluções inovadoras baseadas em dados abertos. 


## Como consultar os dados do catálogo?

O portal **data.europa.eu** disponibiliza um endpoint **SPARQL** (data.europa.eu/data/sparql) onde é possível consultar dados de vários catálogos europeus, incluindo o catálogo português **dados.gov.pt**. 
A plataforma atualiza regularmente os dados publicados em Portugal, permitindo que estes possam ser pesquisados via SPARQL. 


### Exemplo de uma consulta SPARQL para o catálogo dados gov

A consulta seguinte permite obter as informações acerca dos conjuntos de dados publicados no catálogo português [**dados.gov.pt**](https://dados.gov.pt/), com o título, a descrição e a entidade responsável pela sua publicação (limitada a 10 conjuntos de dados): 


```sparql
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX foaf: <http://xmlns.com/foaf/0.1/>
PREFIX fo: <http://www.w3.org/1999/XSL/Format#>
PREFIX dct: <http://purl.org/dc/terms/>
PREFIX dcat: <http://www.w3.org/ns/dcat#>
PREFIX dcterms: <http://purl.org/dc/terms/>

SELECT ?dataset ?title ?description ?publisher
WHERE {
  <http://data.europa.eu/88u/catalogue/dados-gov-pt> dcat:dataset ?dataset .
  ?dataset dct:title ?title ;
           dct:description ?description ;
           dct:publisher ?publisher .
  FILTER(lang(?title) = '') .
  FILTER(lang(?description) = '') .
}
LIMIT 10
```


## Como realizar esta interrogação? 

1. Aceder ao endpoint e editor SPARQL em data.europa.eu/data/sparql ; 

2. Colar a consulta no editor; 

3. Executa a pesquisa.

4. Os resultados serão apresentados numa tabela com os conjuntos de dados encontrados, limitada aos primeiros 10. Este limite pode ser ajustado alterando o valor na instrução LIMIT 10, ou removendo-a para obter todos os resultados disponíveis. 

É também possível **exportar os resultados** em formatos como **CSV, JSON ou XML**, para posterior utilização em sistemas externos ou análises. 


### Saiba mais

Para mais informações, consultar a documentação sobre data.europa em https://data.europa.eu/en/about/sparql no portal europeu.