## Visualizar DUTe

Método utilizado para receber detalhadamente os dados de um DUTes que o Cartório informou ou tenha sido definido como Cartório de arquivamento.

*Caso sua empresa ainda não o possua acesso: [Processo de Integração](../integracao.md)*

[Definindo Ambiente](../ambiente.md)

### 1. Sobre a Requisição

Sua requisição deve ter o Token adquirido no método de [Autenticação](autenticacao.md)

__endereço:__ /api/cartorio/v1/dutes/:id

__método:__ GET

__header:__ {"key":"Authorization","value":"Bearer {{token}}"}

[Saiba mais sobre esta requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

#### 1.1. Como usar?

Para essa requisição informe o ID do DUTe na url.

#### 1.2. Exemplo de Requisição

```bash
curl --location --request GET 'http://<URL_DO_AMBIENTE>/api/cartorio/v1/dutes/138090' \
--header 'Authorization: Bearer {{token}}'
```

[Mais exemplos de requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

### 2. Requisição executada com sucesso

Uma chamada executada com sucesso tem o retorno abaixo: 

##### Bem sucedido - Status: 200
```bash
{
    "dute": {
        "id": 138090,
        "num_protocolo": "2020-344004000126",
        "chave_validacao": "D29CCADC0C",
        "created_at": "2020-12-09T09:56:24.554-03:00",
        "updated_at": "2020-12-09T09:59:31.934-03:00",
        "placa": "KKA7108",
        "renavam": "00951210246",
        "crv": "011382636010",
        "data_crv": "2014-03-22",
        "data_protocolo": "2020-12-09",
        "status": 1,
        "status_descricao": "pendente_de_registro",
        "vendedor_cpf_cnpj": "00000000000",
        "vendedor_nome": null,
        "comprador_cpf_cnpj": "10473093782",
        "comprador_nome": "NOME DO COMPRADOR",
        "comprador_logradouro": "ALAMEDA SANTA CRUZ",
        "comprador_numero": "0002",
        "comprador_complemento": "CASA",
        "comprador_bairro": "JAPUIBA",
        "comprador_cep": "23934565",
        "comprador_municipio": "5801",
        "comprador_uf": "RJ",
        "data_compra": "2020-11-30",
        "valor_compra": "30.000,00",
        "data_autenticacao": "2020-11-30",
        "selo_vendedor": "EDPE21233-BNE",
        "selo_comprador": "EDPE21234-LTX",
        "cartorio_informacao": "MONDRIAN TECNOLOGIA LTDA",
        "cartorio_registro": "2 OFICIO DE JUSTIÇA DE ANGRA DOS REIS",
        "data_registro": null,
        "numero_registro": null,
        "numero_selo_registro": "",
        "verificador_selo": null,
        "url_imagem": "/api/cartorio/v1/dutes/138090/imagem",
        "envio_pendente": "NAO",
        "retorno_detran": "Enviado com sucesso",
        "faturado": "NAO",
        "procuracoes_attributes": [
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
        ],
        "protocolos": [
            {
                "id": 8,
                "status": "sucesso",
                "metodo": "informar",
                "protocolo_detran": "2020-344004000126"
            }
        ]
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
