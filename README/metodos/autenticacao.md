## Autenticação

A autenticação se fará através de um JWT.

Para a geração do mesmo será necessário possuir um acesso para a empresa (usuario e senha) e um acesso de usuário do cartório (usuario e senha).

*Caso sua empresa ainda não o possua: [Processo de Integração](../integracao.md)*

[Definindo Ambiente](../ambiente.md)

### 1. Sobre a Requisição

__endereço:__ /api/cartorio/auth/login

__método:__ POST

[Mais exemplos de requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

#### 1.1. Como usar?

Para requisitar acesso, informe os seguintes parâmetros de entrada.

* __usuario da empresa__: Login da empresa recebido por email no [Processo de Integração](../integracao.md)
* __senha da empresa__: Senha da empresa recebida por email no [Processo de Integração](../integracao.md)
* __usuario do cartorio__: Login de usuário do cartorio
* __senha do cartorio__: Senha de usuário do cartorio

#### 1.2. Exemplo de Requisição

```bash
curl --location --request POST 'http://homolog.rj.duteletronico.com.br/api/cartorio/auth/login' \
--header 'Content-Type: application/json' \
--data-raw '{
    "empresa": { 
        "username": "Login_Empresa",
        "password": "Senha_Empresa"
    }, 
    "usuario": {
        "username": "cartorio",
        "password": "123456"
    }
}'
```

[Mais exemplos de requisição](https://documenter.getpostman.com/view/5620626/TVmV5DRq)

### 2. Requisição executada com sucesso

Uma chamada executada com sucesso, armazene o token recebido para utilizar no __header__ das próximas requisições.

O token pode ser gerado quantas vezes seja necessário e sua expiração é informada na resposta. 

##### Bem sucedido - Status: 200
```bash
{
    "token": "eyJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjo4MzQ2LCJleHAiOjE2MDc1ODE0NzJ9.TgWzg4iojfomL2tJ9UCqFd2CTMg8A0ucSZAA_9I3V0k",
    "exp": "12-10-2020 03:24",
    "username": "cartorio"
}
```

##### Falha não autenticação - Status: 403

```bash
{
    "errors": [
        "A senha informada não é válida."
    ]
}
```
##### Empresa ou Usuário não localizado - Status: 404

```bash
{
    "errors": [
        "EmpresaWS não encontrado."
    ]
}
```

##### Erro Interno - Status: 500
```bash
{
    "errors": [
        "DUTe-RJ:: Erro desconhecido []"
    ]
}
```
