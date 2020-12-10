## Solicitar Nova Digitalização DUTe

Método utilizado informar ao cartório que informou que a não é possível realizar o arquivamento com a imagem atual.

*Caso sua empresa ainda não o possua acesso: [Processo de Integração](../../integracao.md)*

[Definindo Ambiente](../../ambiente.md)

### 1. Sobre a Requisição

Sua requisição deve ter o Token adquirido no método de [Autenticação](../autenticacao.md)

__endereço:__ /api/cartorio/v1/registro/dutes/:id/solicitar_imagem

__método:__ POST

__header:__ {"key":"Authorization","value":"Bearer {{token}}"}

[Saiba mais sobre esta requisição](https://documenter.getpostman.com/view/5620626/TVmV4YYQ)

#### 1.1. Como usar?

Para essa requisição informe o ID do DUTe na url.

#### 1.2. Exemplo de Requisição

```bash
curl --location --request POST 'http://localhost:3000/api/cartorio/v1/registro/dutes/138089/solicitar_imagem' \
--header 'Authorization: Bearer {{token}}'
```

[Mais exemplos de requisição](https://documenter.getpostman.com/view/5620626/TVmV4YYQ)

### 2. Requisição executada com sucesso

Uma chamada executada com sucesso tem o retorno abaixo: 

##### Bem sucedido - Status: 200
```bash
{
    "dute": {
        "id": 138089,
        "nova_imagem": true,
        "imagem": {
            "file_name": null,
            "content_type": null,
            "base64": "not_found"
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
