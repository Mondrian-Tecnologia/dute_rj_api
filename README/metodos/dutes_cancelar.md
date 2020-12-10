## Cancelar 

Método utilizado para cancelar uma informação de venda.

*Caso sua empresa ainda não o possua acesso: [Processo de Integração](../integracao.md)*

[Definindo Ambiente](../ambiente.md)

### 1. Sobre a Requisição

Sua requisição deve ter o Token adquirido no método de [Autenticação](autenticacao.md)

__endereço:__ /api/cartorio/v1/informacao/dutes/:id/cancelar

__método:__ POST

__header:__ {"key":"Authorization","value":"Bearer {{token}}"}

A Requisição criará um protocolo de envio ao DETRAN-RJ, consulte a situação do protocolo para acompanhar o envio ou receber o erro do envio. Consulte [Visualizar Protocolo](protocolos_show.md).

Caso o protocolo informe que foi bem sucedido o envio ao DETRAN e o novo status do DUTe seja "cancelado" o valor pago pode ser estornado ao cliente, caso o novo status seja "desistencia' significa que o DUTe já foi faturado ou se encontra registrado, não sendo autorizada a realização do estorno.

[Saiba mais sobre esta requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

#### 1.1. Como usar?

Para essa requisição informe o ID do DUTe na url e envie o arquivo da digitalização [veja exemplos](https://documenter.getpostman.com/view/5620626/TVmV5DRq):

* __motivo_cancelamento__: Informe o motivo do cancelamento, entre as opções:
    * registro_indevido
    * dados_incorretos
    * desistencia 

#### 1.2. Exemplo de Requisição

```bash
curl --location --request POST 'http://localhost:3000/api/cartorio/v1/dutes/138091/cancelar' \
--header 'Authorization: Bearer {{token}}' \
--header 'Content-Type: application/json' \
--data-raw '{
	"motivo_cancelamento": "desistencia"
}'
```

[Mais exemplos de requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

### 2. Requisição executada com sucesso

Uma chamada executada com sucesso tem o retorno abaixo: 

##### Bem sucedido - Status: 200
```bash
{
    "protocolo": {
        "id": 11,
        "status": "pendente",
        "dute_id": 138091,
        "dute": {
            "placa": "KKA9985",
            "renavam": "00951210246",
            "crv": "011382636010",
            "status": "pendente_de_registro"
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
