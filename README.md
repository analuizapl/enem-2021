# README

## Descrição

Este projeto tem como objetivo analisar os microdados do ENEM 2021 e construir um modelo de regressão linear para prever a nota final dos alunos com base nas variáveis socioeconômicas e nas notas das provas objetivas.

## Dados Utilizados
Para esta análise, foram utilizados os seguintes conjuntos de dados:
Base | Descrição 
--- | --- 
[ENEM Data 2021](https://download.inep.gov.br/microdados/microdados_enem_2021.zip) | Dados sobre o Exame Nacional aplicado em 2021 com todas as notas do candidato.


## Descrição do Código

+ Definição das Colunas: As colunas relevantes dos dados do ENEM 2021 são definidas.

+ Renomeação das Colunas: As colunas do DataFrame são renomeadas para nomes mais descritivos.

+ Substituição de Valores Categóricos: Os valores categóricos das colunas de quantidade são substituídos por valores numéricos.

+ Tratamento de Dados Faltantes: As linhas com dados faltantes são removidas.

+ Codificação de Variáveis Categóricas: As variáveis categóricas são convertidas em variáveis dummy (variáveis indicadoras).

+ Cálculo da Nota Final: A nota final dos alunos é calculada como a média das notas das provas objetivas e da redação.

+ Divisão dos Dados: Os dados são divididos em conjuntos de treinamento e teste.

+ Treinamento do Modelo: Um modelo de regressão linear é treinado usando o conjunto de dados de treinamento.

+ Predição dos Valores: As notas finais são previstas usando o modelo treinado.

+ Importância das Features: As importâncias das features são calculadas e visualizadas para as top 5 e bottom 5 features.

+ Visualização dos Resultados: Gráficos de dispersão são gerados para comparar os valores reais e previstos.

+ Cálculo de Erros: As diferenças entre os valores reais e previstos são calculadas e analisadas.

## Próximos passos
Melhorar o código já existente e explorar mais análises com os dados do enem