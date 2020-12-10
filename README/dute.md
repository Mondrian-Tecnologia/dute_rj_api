## Estrutura de Informar Comunicação de Venda

#### 1. DUTe

Campo                  | Formato       | Tamanho  | Obrigatório | Observação
---------------------- | ------------- | -------- | ----------- | ----------  
placa                  | AAA9999       |    7     | SIM         | ALFANUMERICO
renavam                |               |    11    | SIM         | NUMERICO
crv                    |               |    12    | SIM         | NUMERICO
data_crv               | YYYY-MM-DD    |    10    | SIM         | DATA
chassi                 |               |          | SIM         | ALFANUMERICO
vendedor_cpf_cnpj      |               | 11 ou 14 | SIM         | NUMERICO
comprador_cpf_cnpj     |               | 11 ou 14 | SIM         | NUMERICO
comprador_nome         |               |  até 40  | SIM         | ALFANUMERICO
comprador_logradouro   |               |  até 30  | SIM         | ALFANUMERICO
comprador_numero       |               |  até 5   | SIM         | NUMERICO
comprador_complemento  |               |  até 20  | SIM         | ALFANUMERICO
comprador_bairro       |               |  até 20  | SIM         | ALFANUMERICO
comprador_cep          | 00000-000     |    9     | SIM         | CEP
comprador_municipio    |    0000       |    4     | SIM         | NUMERICO ([Consulte](http://www.fazenda.mg.gov.br/governo/assuntos_municipais/codigomunicipio/))
comprador_uf           |     AA        |    2     | SIM         | UF (Letras maiúsculas)
data_compra            | YYYY-MM-DD    |    10    | SIM         | DATA
valor_compra           | 10.000,00     |          | SIM         | MOEDA (ex: 700,00 - 1.000,00)
data_autenticacao      | YYYY-MM-DD    |    10    | SIM         | DATA (Data do rec. de firma do vendedor)
selo_vendedor          | AAAA12345-AAA |    13    | SIM         | SELO (4 letras + 5 números + '-' + 3 letras)
selo_comprador         | AAAA12345-AAA |    13    | SIM         | SELO (4 letras + 5 números + '-' + 3 letras)
procuracoes_attributes |               |          | NAO         | ARRAY - Consulte a seção *2. Procuração*
sinal_publicos_attributes |            |          | NAO         | ARRAY - Consulte a seção *3. Sinal Público*

#### 2. Procuração

Campo                 | Formato       | Tamanho  | Obrigatório | Observação
--------------------- | ------------- | -------- | ----------- | ----------  
tipo                  |               |          | SIM         | Informe: "comprador" ou "vendedor" 
numero_procuracao     |               |    30    | SIM         | NUMERICO
nome_procurador       |               |    60    | SIM         | ALFANUMERICO
cpf_procurador        |               |    11    | SIM         | NUMERICO
rg_procurador         |               |    60    | SIM         | NUMERICO
data_procuracao       | YYYY-MM-DD    |    10    | SIM         | DATA
observacao_procuracao |               |    60    | NAO         | ALFANUMERICO

#### 3. Sinal Público

Campo      | Formato       | Tamanho  | Obrigatório | Observação
---------- | ------------- | -------- | ----------- | ----------  
tipo       |               |          | SIM         | Informe: "comprador" ou "vendedor" 
oficio     |               |    60    | SIM         | ALFANUMERICO
tabeliao   |               |    60    | SIM         | ALFANUMERICO
origem     |               |    60    | SIM         | ALFANUMERICO
selo       |               |    60    | SIM         | ALFANUMERICO
data_selo  | YYYY-MM-DD    |    10    | SIM         | DATA
observacao |               |    60    | NAO         | ALFANUMERICO

