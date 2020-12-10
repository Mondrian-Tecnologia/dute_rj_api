## Consultar Veículo na base do DETRAN-RJ

Método utilizado para realizar consulta de veículo cadastrado na base do DETRAN-RJ, utilize o método para verificar se será possível realizar a Comunicação de Venda para o Veículo.

*Caso sua empresa ainda não o possua acesso: [Processo de Integração](../integracao.md)*

[Definindo Ambiente](../ambiente.md)

### 1. Sobre a Requisição

Sua requisição deve ter o Token adquirido no método de [Autenticação](autenticacao.md)

__endereço:__ /api/cartorio/v1/veiculos

__método:__ POST

__header:__ {"key":"Authorization","value":"Bearer {{token}}"}

[Saiba mais sobre esta requisição](POSTMAN)

#### 1.1. Como usar?

Para requisitar acesso, informe os seguintes parâmetros de entrada.

* __cpf_vendedor__: CPF/CNPJ do Vendedor / Proprietário, espera-se somente números
* __placa__: Placa do veículo
* __renavam__: Renavam do veículo
* __crv__: CRV do veículo
* __data_crv__: Data de Emissão do CRV, formato esperado "YYYY-MM-DD"

#### 1.2. Exemplo de Requisição

```bash
curl --location --request POST 'http://<URL_DO_AMBIENTE>/api/cartorio/v1/veiculos' \
--header 'Authorization: Bearer {{token}}' \
--data-raw '{
    "veiculo": {
        "cpf_vendedor": "00000000000",
        "placa": "JYU1234",
        "crv": "123456",
        "renavam": "132456",
        "data_crv": "2020-01-01"    
    }
}'
```

[Mais exemplos de requisição](POSTMAN)

### 2. Requisição executada com sucesso

Uma chamada executada com sucesso tem o retorno abaixo: 

##### Bem sucedido - Status: 200
```bash
{
    "veiculo": {
        "nome_vendedor": "NOME DO VENDEDOR",
        "cpf_vendedor": "00000000000",
        "placa": "JYU1234",
        "crv": "123456",
        "renavam": "132456",
        "data_crv": "2020-01-01"
    }
}
```

##### Acesso não autorizado - Status: 401

##### Erros do DETRAN-RJ - Status: 422
```bash
{
    "errors": [
        "99: RENAVAM DIVERGE DA PLACA"
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
