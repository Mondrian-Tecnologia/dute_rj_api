## Status da Comunicação com o DETRAN-RJ

Método utilizado para verificar se nossos servidores conseguem estabelecer comunicação com o DETRAN-RJ

*Caso sua empresa ainda não o possua acesso: [Processo de Integração](../integracao.md)*

[Definindo Ambiente](../ambiente.md)

### 1. Sobre a Requisição

Sua requisição deve ter o Token adquirido no método de [Autenticação](autenticacao.md)

__endereço:__ /api/cartorio/v1/status

__método:__ GET

__header:__ {"key":"Authorization","value":"Bearer {{token}}"}

[Saiba mais sobre esta requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

#### 1.1. Como usar?

Não há necessidade de enviar nenhum parâmetro 

Retornos:
* __200__: Comunicação estabelecida
* __-1__: Timeout ou Instabilidade
* __500__: Falha no WS do DETRAN-RJ
* __Demais cõdigos__: Falha de roteamento ou segmento

#### 1.2. Exemplo de Requisição

```bash
curl --location --request GET 'http://<URL_DO_AMBIENTE>/api/cartorio/v1/status' \
--header 'Authorization: Bearer {{token}}'
```

[Mais exemplos de requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

### 2. Requisição executada com sucesso

Uma chamada executada com sucesso tem o retorno abaixo: 

##### Bem sucedido - Status: 200
```bash
{
    "detran": {
        "status": -1
    }
}
```

##### Acesso não autorizado - Status: 401

##### Erro Interno - Status: 500
```bash
{
    "errors": [
        "DUTe-RJ:: Erro desconhecido [<mensagem>]"
    ]
}
```
