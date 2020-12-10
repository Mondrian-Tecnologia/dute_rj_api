## Métodos 

Para facilitar o entendimento dos métodos disponíveis na API, detalharemos cada um deles.


Método | Descrição
------------ | -------------
[Autenticação](metodos/autenticacao.md) | Gerar o Token de acesso aos demais métodos
[Consultar Veículo no DETRAN-RJ](metodos/veiculos.md) | Consulta prévia que deve ser realizada para validar se é possível informar comunicação de venda para o veículo
[Informar Comunicação de Venda](metodos/informacao/dutes_create.md) | Informar Comunicação de Venda
[Atualizar Comunicação de Venda](metodos/informacao/dutes_update.md) | Atualizar Comunicação de Venda
[Enviar Digitalização do DUTe](metodos/informacao/dutes_upload.md) | Enviar Digitalização do DUTe (CRLV)
[Cancelar DUTe](metodos/dutes_cancelar.md) | Solicitar Cancelamento do DUTe
[Visualizar Protocolo](metodos/protocolos_show.md) | Consulta a situação de um protocolo, o protocolo é utilizado para acompanhar requisições assíncronas como Informar Com. de Venda e Cancelamentos. 
[Listagem de DUTes](metodos/dutes_index.md) | Listar dados simplificados de DUTes informados pelo cartório ou que foram distribuídos para arquivamento, aceita filtros  
[Visualizar DUTe](metodos/dutes_show.md) | Exibir dados detalhados de um DUTe
[Digitalização [Base64]](metodos/dutes_imagem.md) | Receber digitalização códificado por Base 64  (Documento CRLV)
[Digitalização [Binário]](metodos/dutes_imagem_download.md)| Receber o Binário da digitalização (Documento CRLV)
[Espelho / Comprovante [Binário]](metodos/dutes_imprimir.md) | Receber o Binário da digitalização (Documento CRLV)
[Arquivar](metodos/registro/dutes_update.md) | Informar os dados de Arquivamento de um DUTe
[Solicitar Nova Digitalização](metodos/registro/dutes_solicitar_imagem.md) | Solicitar nova digitalização ao cartório que informou a Com. de Venda
[Visualizar Protocolo](metodos/protocolos_show.md) | Exibir dados detalhados do Protocolo do DUTe cadastrado 
