
## Descrição

- [ProjetoFilmes](https://app.powerbi.com/view?r=eyJrIjoiMjBmYTFhNDUtMTZhMS00NmE5LWI5OWMtY2E3NmNmOTdjYTlmIiwidCI6ImRmY2E2YzQyLWM0NjktNDg1Ny05NDk5LWViN2YzNjczZjY4NCJ9): Este projeto realiza uma análise da popularidade dos filmes lançados ao longo do tempo. 


# Dashboard de Análise de Filmes

Clique na imagem para visualizar o dashboard interativo no Power BI:


[![ProjetoGame](https://github.com/arthurffc8/Filmes/blob/main/FotoProjetoFilmes.png)](https://app.powerbi.com/view?r=eyJrIjoiMjBmYTFhNDUtMTZhMS00NmE5LWI5OWMtY2E3NmNmOTdjYTlmIiwidCI6ImRmY2E2YzQyLWM0NjktNDg1Ny05NDk5LWViN2YzNjczZjY4NCJ9)



## Estrutura do Projeto

- **top_rated_9000_movies_on_TMDB.csv**; Contém o arquivo com os dados não tratados.
- **FilmesDataSet.csv**; Contém o arquivo com os dados tratados via python
- **projetoFilmes.ipynb**; Contém o arquivo python usado para extração e tratamento dos dados.
  
## Ferramentas Utilizadas

- **Excel**: Para manipulação básica dos dados e tabelas.
- **Python**; Para extração e tratamento dos dados.
- **Power Query**: Utilizado para limpar e modelar os dados.
- **Power BI**: Utilizado para criação das medidas, de dashboards interativos e visualizações avançadas.

`projetoFilmes.ipynb`:
```python
import pandas as pd
#importando o arquivo csv
filmes_df = pd.read_csv('top_rated_9000_movies_on_TMDB_Puro.csv', sep=',')
filmes_df

# excluindo as colunas desnecessárias

filmes_df = filmes_df.drop(columns=['original_language', 'genre_ids'])
filmes_df

# renomeando as colunas

filmes_df = filmes_df.rename(columns={'id': 'Id', 'title': 'Titulo', 'release_date': "Data de Lançamento", 'vote_average': 'Media de Voto', 'vote_count': 'Contagem de Voto', 'popularity': 'Popularidade', 'overview': 'Resumo', 'Genres': "Genero"})
filmes_df

filmes_df.to_csv('FilmesDataSet.csv', sep=';')
```


  
## Principais Insights

- **Gêneros mais populares**: Um ranking coms os gêneros de filmes mais assistidos.
- **Filmes mais Assistidos**: Um ranking coms os filmes de filmes mais assistidos.
- **Filmes mais avaliados**: Um ranking coms os filmes mais avaliados pelo público.
- **Qtd de filmes por gênero**: Quantidade de filmes lançados por gênero.
- **Lançamentos por ano**: Quantidade de filmes lançados por ano


 ## Dicas Adicionais 

 - **Filtros**: É possível utilizar o filtro para obter insights específicos para algum filme ou gênero.
 - **Sinopse**: Filtre um filme específico para poder ter acesso à sinopse.


## Conclusão 

- **Popularidade de filmes de ação**: Mesmo não sendo o gênero com maior quantidade de filmes, representam o gênero mais popular.
- **Decada mais criativa**: É possível perceber um aumento considerável na quantidade de filmes lançados na decadad e 2011-2020.


