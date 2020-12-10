## Informar Comunicação de Venda

Método utilizado informar Comunicação de Venda.

*Caso sua empresa ainda não o possua acesso: [Processo de Integração](../../integracao.md)*

[Definindo Ambiente](../../ambiente.md)

### 1. Sobre a Requisição

Sua requisição deve ter o Token adquirido no método de [Autenticação](../autenticacao.md)

__endereço:__ /api/cartorio/v1/informacao/dutes

__método:__ POST

__header:__ {"key":"Authorization","value":"Bearer {{token}}"}

A Requisição criará um protocolo de envio ao DETRAN-RJ, consulte a situação do protocolo para acompanhar o envio ou receber o erro do envio. Consulte [Visualizar Protocolo](../protocolos_show.md).

Caso o protocolo informe que foi bem sucedido o envio ao DETRAN, informe a digitalização através do método [Enviar Imagem do DUTe](dutes_upload.md)

Para alterar ou reenviar uma informação, utilize o método de [Atualizar DUTe](dutes_update.md), para o isso o DUTe não pode ter protocolo enviado som sucesso ou pendente.

[Saiba mais sobre esta requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

#### 1.1. Como usar?

Para essa requisição informe o ID do DUTe na url e envie os parâmetros documentos em [Estrutura do DUTe](../../dute.md).

#### 1.2. Exemplo de Requisição

```bash
curl --location --request PATCH 'http://<URL_AMBIENTE>>/api/cartorio/v1/informacao/dutes/138103' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {{token}}' \
--data-raw '{
    "dute": {
        "comprador_cpf_cnpj": "10473093782",
        "comprador_nome": "COMPRADOR",
        "comprador_logradouro": "ALAMEDA SANTA CRUZ",
        "comprador_numero": "0000",
        "comprador_complemento": "CASA",
        "comprador_bairro": "JAPUIBA",
        "comprador_cep": "23934-565",
        "comprador_municipio": "5801",
        "comprador_uf": "RJ",
        "data_compra": "2020-11-30",
        "valor_compra": "30.000,00",
        "data_autenticacao": "2020-11-30",
        "selo_vendedor": "EDPE21233-BNE",
        "selo_comprador": "EDPE21234-LTX",
        "procuracoes_attributes": [
            {
                "tipo": "vendedor",
                "numero_procuracao": "123456",
                "nome_procurador": "PROCURADOR",
                "cpf_procurador": "003.270.273-63",
                "rg_procurador": "123456",
                "data_procuracao": "2020-12-09",
                "observacao_procuracao": "OBSERVACAO"
            },
            {
                "tipo": "comprador",
                "numero_procuracao": "123456",
                "nome_procurador": "NOME DO PROCURADOR",
                "cpf_procurador": "104.826.013-53",
                "rg_procurador": "1111111111111",
                "data_procuracao": "2020-12-09",
                "observacao_procuracao": ""
            }
        ],
        "sinal_publicos_attributes": [
            {
                "tipo": "vendedor",
                "oficio": "1 OFICIO DE XXX",
                "tabeliao": "TABELIAO DE TESTE",
                "origem": "CIDADE",
                "selo": "ASDASD123213232131",
                "data_selo": "2020-12-09",
                "observacao": ""
            }
        ]
    }
}'
```

[Mais exemplos de requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

### 2. Requisição executada com sucesso

Uma chamada executada com sucesso tem o retorno abaixo: 

##### Bem sucedido - Status: 200
```bash
{
    "protocolo": {
        "id": 24,
        "status": "pendente",
        "dute_id": 138103,
        "dute": {
            "placa": "KKA0001",
            "renavam": "00951210246",
            "crv": "011382636010",
            "status": "em_envio"
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
