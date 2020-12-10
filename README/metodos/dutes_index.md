## Listagem de DUTes

Método utilizado para receber de forma simplificada uma listagem de DUTes que o Cartório informou ou tenha sido definido como Cartório de arquivamento, este método permite filtros que serão detalhados abaixo.

*Caso sua empresa ainda não o possua acesso: [Processo de Integração](../integracao.md)*

[Definindo Ambiente](../ambiente.md)

### 1. Sobre a Requisição

Sua requisição deve ter o Token adquirido no método de [Autenticação](autenticacao.md)

__endereço:__ /api/cartorio/v1/dutes

__método:__ GET

__header:__ {"key":"Authorization","value":"Bearer {{token}}"}

[Saiba mais sobre esta requisição](POSTMAN)

#### 1.1. Como usar?

Para listar os DUTes, não há necessidade de passar nenhum parâmetro, porém é possível filtrar pelos seguintes campos.

* __data_inicial__: A Listagem só retornará DUTes criados a partir da data informada, espara-se o formato "YYYY-MM-DD"
* __data_final__: A Listagem só retornará DUTes criados até a data informada, espara-se o formato "YYYY-MM-DD"
* __status__: A Listagem só retornará DUTes com o Status informado, [consulte os status](../status.md)
* __placa__: A Listagem só retornará DUTes com a Placa informada, espera-se o formato 'XXX0000'
* __cartorio__: A Listagem só retornará DUTes que tenham sido informados pelo cartório, espara-se 'true'
* __rtd__: A Listagem só retornará DUTes que tenham sido direcionados ao cartório arquivar, espara-se 'true'

#### 1.2. Exemplo de Requisição

* Sem parâmetro
```bash
curl --location --request GET 'http://<URL_DO_AMBIENTE>/api/cartorio/v1/dutes' \
--header 'Authorization: Bearer {{token}}'
```

* Somente Pendêntes de Arquivamento
```bash
curl --location --request GET 'http://<URL_DO_AMBIENTE>/api/cartorio/v1/dutes?status=1' \
--header 'Authorization: Bearer {{token}}'

ou

curl --location --request GET 'http://<URL_DO_AMBIENTE>/api/cartorio/v1/dutes?status=pendente_de_registro' \
--header 'Authorization: Bearer {{token}}'
```

* Somente Pendêntes de Arquivamento para o Cartório Arquivar
```bash
curl --location --request GET 'http://<URL_DO_AMBIENTE>/api/cartorio/v1/dutes?status=1&rtd=true' \
--header 'Authorization: Bearer {{token}}'

ou

curl --location --request GET 'http://<URL_DO_AMBIENTE>/api/cartorio/v1/dutes?status=pendente_de_registro&rtd=true' \
--header 'Authorization: Bearer {{token}}'
```

[Mais exemplos de requisição](POSTMAN)

### 2. Requisição executada com sucesso

Uma chamada executada com sucesso tem o retorno abaixo: 

##### Bem sucedido - Status: 200
```bash
{
    "dutes": [
        {
            "id": 138090,
            "placa": "KKA7108",
            "status": "pendente_de_registro",
            "updated_at": "2020-12-09T09:59:31.934-03:00"
        },
        {
            "id": 138089,
            "placa": "KKA7107",
            "status": "pendente_de_registro",
            "updated_at": "2020-12-09T09:51:32.112-03:00"
        }
    ],
    "pagination": {
        "current_page": 1,
        "next_page": null,
        "prev_page": null,
        "total_pages": 1,
        "total_count": 2
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
        "DUTe-RJ:: Erro desconhecido [<F>]"
    ]
}
```
