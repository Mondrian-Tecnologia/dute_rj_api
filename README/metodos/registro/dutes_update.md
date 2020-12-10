## Arquivar DUTe

Método utilizado informar os dados de arquivamento de um DUTe.

*Caso sua empresa ainda não o possua acesso: [Processo de Integração](../../integracao.md)*

[Definindo Ambiente](../../ambiente.md)

### 1. Sobre a Requisição

Sua requisição deve ter o Token adquirido no método de [Autenticação](../autenticacao.md)

__endereço:__ /api/cartorio/v1/registro/dutes/:id

__método:__ PATCH

__header:__ {"key":"Authorization","value":"Bearer {{token}}"}

[Saiba mais sobre esta requisição](https://documenter.getpostman.com/view/5620626/TVmV4YYQ)

#### 1.1. Como usar?

Para essa requisição informe o ID do DUTe na url e os seguintes parâmetros:

* __numero_selo_registro__: Informe o Número do Selo de Arquivamento com seu Validador, espera-se o formato "AAAA00000-AAA"
* __numero_registro__: Informe o Número do Arquivamento, utilize um dado que facilite a localização do Arquivamento se necessário.
* __data_registro__: Informe a Data em que o Arquivamento foi praticado, espera-se o formato "YYYY-MM-DD"

#### 1.2. Exemplo de Requisição

```bash
curl --location --request PATCH 'http://<URL_DO_AMBIENTE>/api/cartorio/v1/registro/dutes/138090' \
--header 'Authorization: Bearer {{token}}' \
--data-raw '{
    "numero_selo_registro": "AAAA12345-AAB",
    "data_registro": "2020-01-01",
    "numero_registro": 1234
}'
```

[Mais exemplos de requisição](https://documenter.getpostman.com/view/5620626/TVmV4YYQ)

### 2. Requisição executada com sucesso

Uma chamada executada com sucesso tem o retorno abaixo: 

##### Bem sucedido - Status: 200
```bash
{
    "dute": {
        "id": 138090,
        "created_at": "2020-12-09T09:56:24.554-03:00",
        "updated_at": "2020-12-10T09:22:35.781-03:00",
        "status": 2,
        "status_descricao": "registrado",
        "data_registro": "2020-01-01",
        "numero_registro": "1234",
        "numero_selo_registro": "AAAA12345",
        "verificador_selo": "AAB"
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
