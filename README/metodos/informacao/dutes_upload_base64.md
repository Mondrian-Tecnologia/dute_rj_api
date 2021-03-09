## Enviar Imagem 

Método utilizado informar digitalização (CRLV) da Comunicação de Venda.

*Caso sua empresa ainda não o possua acesso: [Processo de Integração](../../integracao.md)*

[Definindo Ambiente](../../ambiente.md)

### 1. Sobre a Requisição

Sua requisição deve ter o Token adquirido no método de [Autenticação](../autenticacao.md)

__endereço:__ /api/cartorio/v1/informacao/dutes/:id/upload/base64

__método:__ POST

__header:__ {"key":"Authorization","value":"Bearer {{token}}"}

[Saiba mais sobre esta requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

#### 1.1. Como usar?

Para essa requisição informe o ID do DUTe na url e envie o arquivo da digitalização [veja exemplos](https://documenter.getpostman.com/view/5620626/TVmV5DRq):

#### 1.2. Exemplo de Requisição

```bash
curl --location --request POST 'http://homolog.rj.duteletronico.com.br/api/cartorio/v1/informacao/dutes/137890/upload/base64' \
--header 'Authorization: Bearer {{token}}' \
--data-raw '{ "imagem": "JVBERi0xLjMNCiXi48/TDQoNCj...." 
}'
```

[Mais exemplos de requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

### 2. Requisição executada com sucesso

Uma chamada executada com sucesso tem o retorno abaixo: 

##### Bem sucedido - Status: 200
```bash
{
    "dute": {
        "id": 138090,
        "imagem": {
            "file_name": "imagem_(9).pdf",
            "content_type": "application/pdf",
            "base64": "JVBERi0xLjQKJcfsj6... continua"
        }
    }
}
```

##### Acesso não autorizado - Status: 401

##### Dute não localizado - Status: 404

```bash
{
    "errors": [
        "Dute não encontrado."
    ]
}
```

##### Erro Interno - Status: 500
```bash
{
    "errors": [
        "DUTe-RJ:: Erro desconhecido [<mensagem>]"
    ]
}
```
