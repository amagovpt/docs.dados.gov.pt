# Gestão de Conteúdos com a API (ADMIN)

O dados.gov disponibiliza uma API do tipo REST com a qual é possivel interagir para efectuar praticamente qualquer acção permitida pela plataforma, de forma a perceber facilmente estas interacções siga a documentação presente no site (dados.gov.pt/apidoc/), a informação está agrupada por tipo de acção e inclui os “endpoints” a utilizar para cada pedido GET/PUT/POST/DELETE.
 
## Interação com o Insomnia

O Insomina é um cliente REST em ambiente gráfico que além de ser extramamente prático e intuitivo permite facilmente interagir com a API do dados.gov, descarregue o insomnia aqui (https://insomnia.rest/).

## Pedidos GET

Um pedido GET permite efectuar operações de consulta à API, na qual é possível especificar parâmetros de pesquisa ou filtros, para obter o detalhe ou os filtros que podem ser utilizados, consulte na apidoc a especificação do pedido GET pretendido.

##	Pedidos PUT

Um pedido PUT permite realizar operações de actualização de dados, na sua representação técnica é um envio de uma resposta JSON obtida com um pedido GET alterando o valor dos campos pretendidos.

## Pedidos POST

Um pedido POST permite criar novos dados, é utilizado enviando um pedido POST ao servidor no endoint respectivo e enviando em formato JSON os campos obrigatórios para a criação de novos dados.


## Pedidos DELETE

Um pedido DELETE serve para eliminar dados, atenção que qualquer pedido DELETE enviado pela API é irreversível.
