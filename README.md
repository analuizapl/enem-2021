# README

## Descrição

Este repositório contém um código em Python que realiza uma análise dos resultados do  Exame Nacional do Ensino Médio (ENEM) de 2021 por cidade do Brasil. 
O objetivo principal é explorar as notas médias dos estudantes em diferentes matérias e relacioná-las à população estimada de cada município onde as provas foram aplicadas.
O código utiliza bibliotecas como pandas, matplotlib e seaborn para realizar a análise dos dados e gerar visualizações.

## Dados Utilizados
Para esta análise, foram utilizados os seguintes conjuntos de dados:
Base | Descrição 
--- | --- 
[ENEM Data 2021](https://download.inep.gov.br/microdados/microdados_enem_2021.zip) | Dados sobre o Exame Nacional aplicado em 2021 com todas as notas do candidato.
[Cities Data](https://drive.google.com/file/d/1yKnEzytDUOfO06oKcCyyHBiFPYgJAJTg/view)   |  Dados das Cidades Brasileiras      
[Location Data](https://agenciadenoticias.ibge.gov.br/agencia-sala-de-imprensa/2013-agencia-de-noticias/releases/14126-asi-ibge-disponibiliza-coordenadas-e-altitudes-para-21304-localidades-brasileiras) | Lat/Long das cidades brasileiras


## Conteúdo

O projeto inclui os seguintes arquivos e pastas:

1. `analise_enem.ipynb`: Jupyter Notebook contendo o código da análise de dados em Python.
2. O arquivo sqlSave.ipynb contém o código para salvar os dados da análise em uma tabela do banco de dados MySql.
3. O arquivo Script_Pesquisa_table.sql contém um exemplo de script SQL para consultar os dados da tabela criada no banco de dados.
4. `cidades.csv`: Arquivo CSV com informações sobre os municípios, incluindo a população estimada.
5. O diretório Output conterá os seguintes arquivos gerados:
	- `df_microdados.csv`: Arquivo CSV com o conjunto de dados do ENEM após as transformações da análise.
	- `average_scores_by_region.xlsx`: Arquivo Excel contendo as médias das notas por região.
	- `top_10_scores_by_region.xlsx`: Arquivo Excel com as 10 maiores médias de notas por região.
	- `bottom_10_scores_region.xlsx`: Arquivo Excel com as 10 menores médias de notas por região.
	- `top_10_scores_by_state.xlsx`: Arquivo Excel com as 10 maiores médias de notas por estado.
	- `bottom_10_scores_by_state.xlsx`: Arquivo Excel com as 10 menores médias de notas por estado.
	- `top_10_scores_by_city.xlsx`: Arquivo Excel com as 10 maiores médias de notas por cidade.
	- `bottom_10_scores_by_city.xlsx`: Arquivo Excel com as 10 menores médias de notas por cidade.


## Modelagem dos Dados
A modelagem dos dados envolveu a integração dos microdados do ENEM com os dados de municípios, para que fosse possível realizar a análise por região do Brasil. 
O processo de modelagem foi feito da seguinte forma:

1.Dados do ENEM: Os microdados do ENEM contêm informações sobre os candidatos, incluindo as notas obtidas em cada prova (Ciências da Natureza, Ciências Humanas, Linguagens e Códigos, Matemática e Redação).

2.Dados dos Municípios: O arquivo cidades.csv contém dados socioeconômicos dos municípios brasileiros, incluindo a estimativa da população para o ano de 2019.

3.Integração de Dados: Os dados dos municípios foram integrados aos microdados do ENEM utilizando a coluna "Município de Prova" como chave de ligação. Dessa forma, foi possível enriquecer o DataFrame do ENEM com informações adicionais, como a população estimada de cada município.

4.Cálculo das Médias por Região: Com os dados enriquecidos, o código calculou as médias das notas de cada prova por região do Brasil (Norte, Nordeste, Centro-Oeste, Sudeste e Sul).

5.Análise e Visualização: O código utilizou as bibliotecas matplotlib e seaborn para criar gráficos e visualizações dos resultados, identificando as 10 maiores e 10 menores médias de notas por região.


## Requisitos

Para executar a análise de dados e reproduzir os resultados, são necessárias as seguintes bibliotecas Python:

- pandas
- matplotlib
- seaborn


## Como executar

1. Certifique-se de ter as bibliotecas Python mencionadas instaladas em seu ambiente.
2. Execute o arquivo `analise_enem.ipynb` usando o Jupyter Notebook ou qualquer ambiente compatível.
3. Faça o download dos arquivos microdados_enem.csv e cidades.csv e coloque-os na mesma pasta do arquivo enem_analysis.ipynb.
4. A análise será executada e os resultados serão salvos nos arquivos mencionados na seção "Conteúdo" dentro da pasta Output.
