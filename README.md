# USA Cars Analysis

Análise exploratória e visualização de dados de carros usados anunciados nos EUA.

## Arquivos

### Dados
- **`USA_cars_datasets.csv`** — dataset original com 2.499 anúncios de carros, sem valores ausentes. Contém: marca, modelo, ano, preço, quilometragem, cor, estado e status do título.
- **`USA_cars_datasets_reallife.csv`** — versão "realista" do mesmo dataset, com valores ausentes intencionais em colunas como `price`, `brand`, `year` e `mileage`.

### Notebooks
- **`data_cleaning_and_eda.ipynb`** — limpeza de dados e análise exploratória aplicadas ao dataset com valores ausentes:
  - Identificação e tratamento de nulos por coluna
  - Preenchimento de `brand` via mapeamento por modelo
  - Remoção de linhas sem `model` ou `color` (< 1% do dataset)
  - Imputação de `mileage` e `year` pela mediana agrupada por marca, modelo e faixa de preço
  - Predição dos 79 preços ausentes com três modelos de ML: **XGBoost** (R² 0.92), **Random Forest** (R² 0.96) e **Regressão Linear** (R² 0.29)

- **`plots.ipynb`** — visualizações exploratórias usando o dataset limpo original:
  - Evolução do preço médio por ano de fabricação
  - Dispersão preço × marca (colorida por quilometragem)
  - Regressão quilometragem × preço para BMW, Nissan e Jeep
  - Distribuição de preços por condição do veículo (boxplot)

## Principais achados
- Random Forest foi o melhor modelo para imputação de preços (MAE ≈ $1.583).
- Carros mais novos têm preços médios maiores, com queda acentuada após 2020 (poucos registros).
- Maior quilometragem reduz o preço de forma consistente nas três marcas analisadas.
