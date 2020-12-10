## Digitalização do DUTe em Base64

Método utilizado para receber a digitalização como Base64 de um DUTes que o Cartório informou ou tenha sido definido como Cartório de arquivamento.

*Caso sua empresa ainda não o possua acesso: [Processo de Integração](../integracao.md)*

[Definindo Ambiente](../ambiente.md)

### 1. Sobre a Requisição

Sua requisição deve ter o Token adquirido no método de [Autenticação](autenticacao.md)

__endereço:__ /api/cartorio/v1/dutes/:id/imagem

__método:__ GET

__header:__ {"key":"Authorization","value":"Bearer {{token}}"}

[Saiba mais sobre esta requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

#### 1.1. Como usar?

Para essa requisição informe o ID do DUTe na url.

#### 1.2. Exemplo de Requisição

```bash
curl --location --request GET 'http://<URL_DO_AMBIENTE>/api/cartorio/v1/dutes/138084/imagem' \
--header 'Authorization: Bearer {{token}}'
```

[Mais exemplos de requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

### 2. Requisição executada com sucesso

Uma chamada executada com sucesso tem o retorno abaixo: 
* O campo nova_imagem, informa se o RTD solicitou o envio de uma nova imagem.

##### Bem sucedido - Status: 200
```bash
{
    "dute": {
        "id": 138084,
        "nova_imagem": false,
        "imagem": {
            "file_name": "imagem_(9).pdf",
            "content_type": "application/pdf",
            "base64": "<base64 do arquivo>"
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
