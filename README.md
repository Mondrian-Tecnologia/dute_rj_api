## Documentação para API do DUTe RJ

#### Dividimos a documentação em tópicos, acesse a opção desejada:

##### 1. Introdução

* [Processo de Integração](README/integracao.md)
* [Ambientes](README/ambiente.md)
* [Status do DUTe](README/status.md)
* [Estrutura do DUTe](README/dute.md)

##### 2. Métodos da API

* [Introdução](README/metodos.md)
* [Autenticação](README/metodos/autenticacao.md)
* [Consultar Veículo no DETRAN-RJ](README/metodos/veiculos.md)
* [Informar Comunicação de Venda](README/metodos/informacao/dutes_create.md)
* [Atualizar Comunicação de Venda](README/metodos/informacao/dutes_update.md)
* [Enviar Digitalização do DUTe](README/metodos/informacao/dutes_upload.md)
* [Cancelar DUTe](README/metodos/dutes_cancelar.md)
* [Listagem de DUTes](README/metodos/dutes_index.md)
* [Visualizar DUTe](README/metodos/dutes_show.md)
* [Digitalização [Base64]](README/metodos/dutes_imagem.md)
* [Digitalização [Binário]](README/metodos/dutes_imagem_download.md)
* [Espelho/Comprovante [Binário]](README/metodos/dutes_imprimir.md)
* [Arquivar DUTe](README/metodos/registro/dutes_update.md)
* [Solicitar Nova Digitalização](README/metodos/registro/dutes_solicitar_imagem.md)
* [Status da Comunicação com DETRAN-RJ](README/metodos/home_status.md)

#### Chat de Suporte ao Cartório

Agora é possível adicionar nosso Chat de Suporte ao usuário em seu sistema.

Crie um iframe ou envie o usuário à página, informando os parâmetros:

* sistema (dute_rj - FIXO)
* nome (nome utilizado no atendimento)
* telefone (somente numeros)

http://chat.mondriantecnologia.com/chat?sistema=dute_rj&nome=<JOAO_DA_SILVA>&telefone=<22 1234456789>

http://chat.mondriantecnologia.com/chat?sistema=dute_rj&nome=teste&telefone=221234456789>




