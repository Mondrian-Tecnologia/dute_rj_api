## Digitalização do DUTe para Download

Método utilizado para receber a digitalização como Binário de um DUTes que o Cartório informou ou tenha sido definido como Cartório de arquivamento.

*Caso sua empresa ainda não o possua acesso: [Processo de Integração](../integracao.md)*

[Definindo Ambiente](../ambiente.md)

### 1. Sobre a Requisição

Sua requisição deve ter o Token adquirido no método de [Autenticação](autenticacao.md)

__endereço:__ /api/cartorio/v1/dutes/:id/imagem/download

__método:__ GET

__header:__ {"key":"Authorization","value":"Bearer {{token}}"}

[Saiba mais sobre esta requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

#### 1.1. Como usar?

Para essa requisição informe o ID do DUTe na url.

#### 1.2. Exemplo de Requisição

```bash
curl --location --request GET 'http://<URL_DO_AMBIENTE>/api/cartorio/v1/dutes/138084/imagem/download' \
--header 'Authorization: Bearer {{token}}'
```

[Mais exemplos de requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

### 2. Requisição executada com sucesso

Uma chamada executada com sucesso tem o retorno abaixo: 

##### Bem sucedido - Status: 200
```bash
%PDF-1.4
%�쏢 
... continua
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
