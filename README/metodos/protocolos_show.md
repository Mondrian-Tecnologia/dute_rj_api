## Consultar Protocolo de Envio ao DETRAN-RJ

Método utilizado para realizar consulta de Protocolo, criado para que algumas operações sejam realizadas de forma assíncrona.

*Caso sua empresa ainda não o possua acesso: [Processo de Integração](../integracao.md)*

[Definindo Ambiente](../ambiente.md)

### 1. Sobre a Requisição

Sua requisição deve ter o Token adquirido no método de [Autenticação](autenticacao.md)

__endereço:__ /api/cartorio/v1/dutes/:dute_id/protocolos/:id_protocolo

__método:__ GET

__header:__ {"key":"Authorization","value":"Bearer {{token}}"}

[Saiba mais sobre esta requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

#### 1.1. Como usar?

Para requisitar acesso, informe os seguintes parâmetros de entrada.

* __cpf_vendedor__: CPF/CNPJ do Vendedor / Proprietário, espera-se somente números
* __placa__: Placa do veículo
* __renavam__: Renavam do veículo
* __crv__: CRV do veículo
* __data_crv__: Data de Emissão do CRV, formato esperado "YYYY-MM-DD"

#### 1.2. Exemplo de Requisição

```bash
curl --location --request GET 'http://<URL_DO_AMBIENTE>/api/cartorio/v1/dutes/138090/protocolos/8' \
--header 'Authorization: Bearer {{token}}'
```

[Mais exemplos de requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

### 2. Requisição executada com sucesso

Uma chamada executada com sucesso tem o retorno abaixo: 

##### Bem sucedido - Status: 200
```bash
{
    "id": 8,
    "metodo": "informar",
    "status": "sucesso",
    "protocolo_detran": "2020-344004000126",
    "dute": {
        "id": 138090,
        "placa": "KKA7108",
        "renavam": "00951210246",
        "crv": "011382636010",
        "status": 1,
        "status_descricao": "pendente_de_registro"
    }
}
```

##### Acesso não autorizado - Status: 401

##### Protocolo não localizado - Status: 404

```bash
{
    "errors": [
        "Protocolo não encontrado."
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
