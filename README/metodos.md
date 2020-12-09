## Métodos 

Para facilitar o entendimento dos métodos disponíveis na API, detalharemos cada um deles.


Método | Descrição
------------ | -------------
[Autenticação](metodos/autenticacao.md) | Gerar o Token de acesso aos demais métodos
[Listagem de DUTes](metodos/dutes_index.md) | Listar dados simplificados de DUTes informados pelo cartório ou que foram distribuídos para arquivamento, aceita filtros  
[Visualizar DUTe](metodos/dutes_show.md) | Exibir dados detalhados de um DUTe
[Digitalização [Base64]](metodos/dutes_imagem.md) | Receber digitalização códificado por Base 64  (Documento CRLV)
[Digitalização [Binário]](metodos/dutes_imagem_download.md)| Receber o Binário da digitalização (Documento CRLV)
[Espelho / Comprovante [Binário]](metodos/dutes_imprimir.md) | Receber o Binário da digitalização (Documento CRLV)
[Consultar Veículo no DETRAN-RJ](metodos/veiculos.md) | Consulta prévia que deve ser realizada para validar se é possível informar comunicação de venda para o veículo
[Visualizar Protocolo](metodos/protocolos_show.md) | Consulta prévia que deve ser realizada para validar se é possível informar comunicação de venda para o veículo

Visualizar Protocolo | Exibir dados detalhados do Protocolo do DUTe cadastrado 

##### 1. Integração

A Empresa que desejar acessar os serviços da API, deverá solicitar acesso à API do DUTe RJ enviando um email (suporte@mondriantecnologia.com) os seguintes dados:

* *CNPJ*
* *Razão Social*
* *Nome Fantasia*

Lhe responderemos o email com acesso que utilizaremos para identificar sua empresa no processo de autenticação da API:

* *[Empresa] Usuário*
* *[Empresa] Senha*

##### 2. Homologação e Produção

Os ambientes estarão disponíveis tão logo sua empresa receba o email com __Usuário__ e __Senha__ de acesso.

[Endereço dos Ambientes](ambiente.md)