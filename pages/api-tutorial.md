---
title: API Tutorial
keywords:
description: API Tutorial
reuses:
datasets:
---

API Tutorial
======================

Esta página descreve o comportamento da API do dados.gov.

Autenticação
----------------

Para executar operações de gravação, você deve primeiro ser autenticado e obter uma chave de API em suas configurações de perfil.

Essa chave deve ser fornecida em cada chamada no cabeçalho HTTP `X-API-KEY`.

Permissões
-------------

As chamadas de API estão sujeitas às mesmas permissões que a interface da Web.

Por exemplo, você deve ser membro da organização para modificar qualquer um de seus conjuntos de dados.

Paginação
----------

Alguns métodos são paginados e seguem o mesmo modelo de paginação. A lista de objetos é encapsulada em um objeto `Page`.

Você não precisa calcular as páginas anteriores e seguintes por conta própria, pois as URLs estão disponíveis na resposta dos atributos `previous_page` e `next_page`. Eles serão definidos como `null` se não houver nenhuma página anterior e/ou próxima.

Exemplo:

    {
                    "data": [{...}, {...}],
                    "page": 1,
                    "page_size": 20,
                    "total": 10,
                    "next_page": "https://dados.gov.pt/api/endpoint/?page=2",
                    "previous_page": null
                }


## Exemplos 

Os exemplos a seguir usam as seguintes ferramentas de linha de comando: [httpie](http://httpie.org) e [jq](http://stedolan.github.io/jq/). Pode, é claro, usar essa API com as ferramentas ou bibliotecas de sua escolha.

### Verifique se o httpie está funcionando

Uma vez que o httpie está instalado, você pode verificar se ele está funcionando conforme o esperado, digitando este comando em seu terminal:

    $ http 'https://dados.gov.pt/api/1/organizations/?page_size=1'

Isso deve retornar uma resposta como esta:

    
                HTTP/1.1 200 OK
                Access-Control-Allow-Credentials: true
                ... LOTS OF HEADERS ...
                
                {
                    "data": [
                        {
                
                            ... LOTS OF DATA ...
                
                            "name": "Stelareum",
                            "page": "https://dados.gov.pt/organizations/stelareum/",
                            "slug": "stelareum",
                            "uri": "https://dados.gov.pt/api/1/organizations/5cb1d1ed0f7fb0438df74602/",
                            "url": "https://www.stelareum.io/"
                        }
                    ],
                    "next_page": "https://dados.gov.pt/api/1/organizations/?page=2&page_size=1",
                    "page": 1,
                    "page_size": 1,
                    "previous_page": null,
                    "total": "10"
                }
                

Isso é muito detalhado e não precisamos de todas essas informações agora. É por isso que usamos jq.

### Verificando se jq está funcionando

Uma vez instalado o jq, você pode verificar se ele está funcionando digitando este comando em seu terminal:

    $ http 'https://dados.gov.pt/api/1/organizations/?page_size=1' | jq '.data[].name'

Isso deve retornar uma resposta como esta:

    "Stelareum"

Isso é muito melhor! Agora que tudo está funcionando bem, vamos reduzir um pouco o tamanho da nossa linha de comando:

    $ export API="https://dados.gov.pt/api/1/"

O comando anterior agora é equivalente ao comando mais legível (não se esqueça dos apóstrofos):

    $ http $API 'organizations/?page_size=1' | jq '.data[].name'

Esse é um bom começo, agora vamos mergulhar na API em si. Ainda não sabemos, mas já recuperamos nossa primeira organização.

### Navegação e recuperação de dados

Você pode recuperar uma lista de organizações (filtradas ou não) ou uma única organização. Ao recuperar um ponto de acesso, o número padrão de itens por página é 20. Vamos recuperar as primeiras 20 organizações por meio da API:

    $ http $API'organizations/' | jq '.data[].name'

    
                "Stelareum"
                "Department of Public Works - MMTP"
                "NEXXTLAB S.A."
                "Legato Team"
                Legato Team" "Legato Team
                "Service National de la Jeunesse" "OpenAgenda
                "OpenAgenda" "toto
                "toto
                "Portuguese Independent Broadcasting Authority" "Centro de gerenciamento de TI educacional
                "Centro de gerenciamento de TI educacional".
                
                

É bom ter essa lista, mas o que acontece se quisermos navegar pelas organizações devolvidas? Vamos pegar os 5 primeiros URIs das organizações.

    $ http $API 'organizations/?page_size=5' | jq '.data[].uri'

    
                "https://dados.gov.pt/api/1/organizations/5cb1d1ed0f7fb0438df74602/"
                "https://dados.gov.pt/api/1/organizations/5c403e1528c4b2621cd384e9/"
                "https://dados.gov.pt/api/1/organizations/5b5b26157676667aa7f57afe/"
                "https://dados.gov.pt/api/1/organizations/5953ebee111e9b2a8e7133bd/"
                "https://dados.gov.pt/api/1/organizations/5953d44c111e9b2a5fcb4b59/"
                
                

Agora podemos recuperar uma organização apenas por meio do URI retornado.

    $ http $API'organizations/5cb1d1ed0f7fb0438df74602/' | jq '.'

São muitos dados para analisar. Vamos refinar esses dados, se quisermos extrair apenas as métricas:

    $ http $API 'organizations/5cb1d1ed0f7fb0438df74602/' | jq '.metrics'

    
                {
                 "datasets": 0,
                 "members": 1,
                 "views": 0,
                 "followers": 0,
                 "reuses": 0,
                 "dataset_views": 0,
                 "reuse_views": 0,
                 "resource_downloads": 0,
                 
                }
                

Ou talvez apenas os nomes dos membros desta organização:

    $ http $API'organizations/5cb1d1ed0f7fb0438df74602/' | jq '.members[].user.last_name'

    
                "Crypto"
                
                
Cabe realmente a você recuperar os dados relevantes para o seu projeto. Sinta-se livre para consultar o [jq's tutorial](http://stedolan.github.io/jq/tutorial/) e [his manual](http://stedolan.github.io/jq/manual/) se você quiser navegar na API através da linha de comando em mais detalhes.

### Editando e excluindo dados

Cuidado, você está entrando em uma zona de perigo. As modificações e exclusões de dados por meio da API são finais e não fornecemos uma área restrita para testar antes de executá-las (ainda). Esteja ciente dessas responsabilidades antes de usar seus superpoderes.

Se você tentar modificar um recurso sem o token de autenticação, um erro 401 será retornado:

    $ http PUT $API'organizations/organization-uri-x/'

    
                HTTP/1.1 401 UNAUTHORIZED
                ... LOTS OF HEADERS ...
                
                {
                    "message": "Unauthorized",
                    "status": 401
                }
                

Deve especificar sua chave de API (veja acima) e usar o cabeçalho `X-API-KEY`. Se você tentar modificar um recurso que não controla, um erro 400 será retornado:

    $ http PUT $API'organizations/organization-uri-x/' X-API-KEY:your.api.key.here

    
                HTTP/1.1 401 UNAUTHORIZED
                ... LOTS OF HEADERS ...
                
                {
                    "message": "Invalid API Key",
                    "status": 401
                }
                

Esta é a mensagem que você receberá se tiver especificado a chave de API errada. Esta é outra mensagem de erro potencial que você pode encontrar.

    
                HTTP/1.1 403 FORBIDDEN
                ... LOTS OF HEADERS ...
                
                {
                    "message": "You do not have the permission to modify that object.",
                    "status": 403
                }
                

Isso acontece se você tentar acessar um recurso que não pode editar com suas credenciais. Se a sua chave é válida, você deve obter algo assim:

    
                HTTP/1.1 200 OK
                ... LOTS OF HEADERS ...
                
                {
                    ...
                }
                

Mas isso não muda tudo! É perfeitamente normal, esquecemos de especificar os dados certos para enviar ao servidor.

    $ http PUT $API'organizations/organization-uri-x/' X-API-KEY:your.api.key.here name="Lorem ipsum" description="The quick brown fox jumps over the lazy dog." | jq '{name: .name, description: .description}'

    
                {
                  "name": "Lorem ipsum",
                  "description": "The quick brown fox jumps over the lazy dog."
                }
                

O recurso foi modificado com seus novos valores. Finalmente, você pode excluir um recurso com o verbo HTTP apropriado (observe que nenhuma reversão é possível usando a API no momento):

    $ http DELETE $API'organizations/organization-uri-x/' X-API-KEY:your.api.key.here

    
                HTTP/1.0 204 NO CONTENT
                ... LOTS OF HEADERS ...
                
                

Uma vez feito, você pode verificar se é eficaz enviando um GET para a URL anterior:

    $ http GET $API'organizations/organization-uri-x/'

    
                HTTP/1.0 410 GONE
                ... LOTS OF HEADERS ...
                
                {
                    "message": "Organization has been deleted",
                    "status": 410
                }
                
                


Uma vez feito, você pode verificar se é eficaz enviando um GET para a URL anterior: [exemplos mostrando como usar essa API em Python](https://github.com/opendatalu/udata-examples), bem como a [documentação de referência](/en/docapi).
