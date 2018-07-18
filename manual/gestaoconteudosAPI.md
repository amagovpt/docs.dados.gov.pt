# Gestão de Conteúdos com a API (ADMIN)

O dados.gov disponibiliza uma API do tipo REST com a qual é possivel interagir para efectuar praticamente qualquer acção permitida pela plataforma, de forma a perceber facilmente estas interacções siga a documentação presente no site (dados.gov.pt/apidoc/), a informação está agrupada por tipo de acção e inclui os “endpoints” a utilizar para cada pedido GET/PUT/POST/DELETE.

- [Interação com o Insomnia](#interação-com-o-insomnia)
- [Pedidos GET](#pedidos-get)
- [Pedidos PUT](#pedidos-put)
- [Pedidos POST](#pedidos-post)
- [Pedidos DELETE](#pedidos-delete)
 
## Interação com o Insomnia

O Insomina é um cliente REST em ambiente gráfico que além de ser extramamente prático e intuitivo permite facilmente interagir com a API do dados.gov, descarregue o insomnia aqui (https://insomnia.rest/).

## Pedidos GET

Um pedido GET permite efectuar operações de consulta à API, na qual é possível especificar parâmetros de pesquisa ou filtros, para obter o detalhe ou os filtros que podem ser utilizados, consulte na apidoc a especificação do pedido GET pretendido. 

*Exemplo: obter todos os datasets de uma determinada organização*

```python
import requests

# Insira a sua API_KEY (para mais detalhes consulte a seguinte documentação: https://dados.gov.pt/pt/apidoc/)
headers = {
   'x-api-key': "<YOUR_API_KEY>"
}

url = "https://dados.gov.pt/api/1/datasets/"

querystring = {
    # Número de datasets a aparecer por página
    "page_size":"100",
    # ID da organização
    "organization":"5b06d347acac33199b8c7bb5"
}

# Pedido GET
response = requests.request("GET", url, headers=headers, params=querystring)

print(response.text)
```

##	Pedidos PUT

Um pedido PUT permite realizar operações de actualização de dados, na sua representação técnica é um envio de uma resposta JSON obtida com um pedido GET alterando o valor dos campos pretendidos. 


*Exemplo: atualizar as zonas geográficas de um conjunto de datasets*

```python

import requests

# Conteúdo a ser atualizado
payload =
{
    "spatial":{
        "zones": "pt:concelho:1106"
    }
}

headers = {
   'x-api-key': "<YOUR_API_KEY>"
   'content-type': "application/json"
}

# Lista de datasets que pode ser obtida através de um pedido GET
datasets = [
    '5b06d49eacac3351a85f5df8',
    'c3351a85f5df85b06d49eaca',
    (...)
]

# Ciclo que percorre a lista de datasets
for dataset in datasets:
    url = "https://dados.gov.pt/api/1/datasets/" + dataset + "/"
    # Pedido PUT
    response = requests.request("PUT", url, data=payload, headers=headers)
    print(response.text)
```

## Pedidos POST

Um pedido POST permite criar novos dados, é utilizado enviando um pedido POST ao servidor no endoint respectivo e enviando em formato JSON os campos obrigatórios para a criação de novos dados.

*Exemplo: adicionar um dataset a uma determinada organização*

```python

import requests

payload =
{
   "title":"Dataset",
   "description":"description",
   "frequency":"unknown",
   "license":"cc-by",
   "organization":{
      "id":"5b0596c1acac334356038198"
   },
   "private":false,
   "slug":"dataset"
}

headers = {
   'x-api-key': "<YOUR_API_KEY>"
   'content-type': "application/json"
}

url = "https://dados.gov.pt/api/1/datasets/"

# Pedido POST
response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```


## Pedidos DELETE

Um pedido DELETE serve para eliminar dados, atenção que qualquer pedido DELETE enviado pela API é irreversível. 

*Exemplo: eliminar um determinado dataset*

```python 
import requests

headers = {
   'x-api-key': "<YOUR_API_KEY>"
}

# URL do dataset a ser eliminado
url = "https://172.31.204.12/api/1/datasets/<ID_DATASET>/"

# Pedido DELETE
response = requests.request("DELETE", url, headers=headers, params=querystring)

print(response.text)
```
