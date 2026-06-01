# analise-mercado-imobiliario
nálise exploratória, tratamento de outliers e engenharia de atributos utilizando Python, Pandas e Seaborn.

# 📈 Análise de Elasticidade de Preços no Mercado Imobiliário

## 🎯 Objetivo do Projeto
Identificar se a renda média de uma região é um fator decisivo e confiável para prever a valorização imobiliária, além de mapear o impacto geográfico e estrutural nos preços dos imóveis.

## 📂 Fonte dos Dados
Os dados utilizados neste projeto foram obtidos a partir do conjunto de dados público **California Housing Dataset**, baseado no censo oficial de habitação realizado na Califórnia. A base de dados foi acessada diretamente através dos arquivos de amostra nativos do ambiente **Google Colab** (`sample_data/california_housing_train.csv`).

## 🛠️ Desafios Técnicos & Soluções (Data Cleaning)
* **Tratamento de Outliers:** Durante a análise exploratória, identifiquei um *teto artificial (data truncation)* exatamente na marca de $500.000, onde os dados foram cortados, gerando uma linha acumulada que enviesava a análise.
* **Ação Tomada:** Utilizei a biblioteca **Pandas** para aplicar uma filtragem dinâmica, removendo os registros truncados (`df['median_house_value'] < 500000`) e isolando o comportamento orgânico do mercado.

## 🧠 Engenharia de Atributos (Feature Engineering)
* Realizei a criação da nova métrica **'Quartos por Família'** dividindo o total de quartos pelo total de lares (`total_bedrooms / households`). 
* **Insight de Negócio:** Ao analisar o impacto no preço, concluiu-se que fatores socioeconômicos (renda média) têm uma influência significativamente maior na valorização imobiliária (correlação forte de 0.69) do que características físicas estruturais do imóvel (número de quartos, que apresentou correlação próxima a zero).

## 📍 Análise Geoespacial
A análise revelou que o preço dos imóveis é fortemente ditado pela **proximidade geográfica com os grandes polos econômicos e zonas costeiras** (regiões metropolitanas de Los Angeles e San Francisco), sobrepondo o fator de densidade populacional isolado.

---
*Projeto desenvolvido como parte do portfólio de transição de carreira para Ciência de Dados.*
