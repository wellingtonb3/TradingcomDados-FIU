## Final Project for the Trading com Dados Summer Course in collaboration with FIU (Florida International University)

<center><img src = "https://github.com/victorncg/pythonforfinance/blob/main/Captura%20de%20tela%202023-07-14%20144104.png?raw=true" width = "600">

#### About the Final Project (EN/US)

After completing the weekly classes, we have gained proficiency in Python and the relevant libraries approved for the financial market. This knowledge equips us to successfully complete our final project, addressing the following questions:

1. Obtain Adjusted Close (Adj Close) data for 5 stocks of your preference (they can be from any country)

2. In order for us to understand the behavior of these data, use the pandas library to analyse basic statistics of each stock, such as: count, mean, std, min, max and percentiles.

3. Plot these stocks using the plotly library

4. Now, standardize the stocks' prices so they all start from 1. Create a new dataframe with this data.

5. Plot the new standardized data using plotly library

6. Now, let's measure the impact of inflation and interest rates on the financial market.

Using what you learned through this course, create:

a 2-axis plot of Interest Rates and the S&P 500 using plotly.
a 2-axis plot of Inflation and the S&P 500 using plotly.
Hint: Use what you learned in Module 02. Also, the symbol for the S&P 500 in the yfinance library is "^GSPC"

7. Let's create a dataframe with fundamentals for the following companies:
'AAPL', 'MSFT', 'AMZN', 'GOOGL', 'META'

You should obtain the following fundamentals:

'MarketCap', 'EnterpriseValue', 'Revenue', 'ProfitMargin', 'OperatingMargin','dividendRate', 'beta', 'ebitda'

8. Create a panel for the stocks mentioned in question 7, using the same metrics

[back](#about-the-final-project-enus)

## Exercise 1 -

```python
-- Obtaining Adjusted Close (Adj Close) data for 5 stocks

!pip install yfinance
import yfinance as yf
assets = ['PETR4.SA', 'VALE3.SA', 'MGLU3.SA','ITUB4.SA','GOAU4.SA']
adj_close = yf.download (assets , start = '2020-01-01')['Adj Close']
adj_close
```

[back](#about-the-final-project-enus)

## Exercise 2 -

```python
-- Using pandas library to analyse basic statistics of each stock, such as: count, mean, std, min, max and percentiles

import pandas as pd
pd.set_option('display.float_format', '{:.1f}'.format)
adj_close.describe()
```

[back](#about-the-final-project-enus)

## Exercise 3 - 
- Plotting 5 Stocks that I choose![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%201.png)

[back](#about-the-final-project-enus)

## Exercise 4 -

```python
-- Standardizing stock prices so everyone starts at 1
adj_close_std = adj_close/adj_close.iloc[0]
adj_close_std
```

[back](#about-the-final-project-enus)

## Exercise 5 - 
- Plotting these stocks standardized![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%202.png)

[back](#about-the-final-project-enus)

## Exercise 6.1 - 
- Measuring the impact of interest rates on the financial market![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%203.png)

[back](#about-the-final-project-enus)

## Exercise 6.2 - 
- Measuring the impact of inflation on the financial market![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%204.png)

[back](#about-the-final-project-enus)

## Exercise 7 -

```python
-- creating a dataframe with fundamentals for the following companies:
['AAPL', 'MSFT', 'AMZN', 'GOOGL', 'META']

create database ecommerce1;
use ecommerce1;
```

[back](#about-the-final-project-enus)

## Exercise 8 - 
- creating a Panel with 'EnterpriseValue', 'Revenue', 'ProfitMargin', 'OperatingMargin','dividendRate', 'beta', 'ebitda'![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%205.png)

[back](#about-the-final-project-enus)

--------------------------------------------------------------------------

### Main Libraries
```python
YFinance
Nasdaq DataLink
Plotly
```
[back](#about-the-final-project-enus)


---------------------------------------------------------------------------------
---------------------------------------------------------------------------------

## Projeto Final do Curso de Verão Trading com Dados em colaboração com a FIU (Florida International University)


#### Sobre o Projeto Final (PT/BR)

Após concluir as aulas semanais, ganhamos proficiência em Python e nas bibliotecas relevantes homologadas para o mercado financeiro. Esse conhecimento nos capacita para concluir com sucesso nosso projeto final, abordando as seguintes questões:

1. Obtenha dados de fechamento ajustado (adj close) para 5 ações de sua preferência (podem ser de qualquer país.

2. Para entendermos o comportamento desses dados, utilize a biblioteca pandas para analisar estatísticas básicas de cada ação, como: contagem, média, padrão, mínimo, máximo e percentis.

3. Plote essas ações usando a biblioteca plotly

4. Agora, padronize os preços das ações para que todos comecem em 1. Crie um novo dataframe com esses dados.

5. Plote os novos dados padronizados usando a biblioteca plotly

6. Agora, vamos medir o impacto da inflação e das taxas de juros no mercado financeiro.

Usando o que você aprendeu neste curso, crie:

um gráfico de 2 eixos das taxas de juros e do S&P 500 usando plotly;
um gráfico de 2 eixos da inflação e do S&P 500 usando plotly;
Dica: o símbolo do S&P 500 na biblioteca yfinance é "^GSPC"

7. Vamos criar um dataframe com fundamentos para as seguintes empresas:
'AAPL', 'MSFT', 'AMZN', 'GOOGL', 'META'

Você deve obter os seguintes fundamentos:

'MarketCap', 'EnterpriseValue', 'Revenue', 'ProfitMargin', 'OperatingMargin','dividendRate', 'beta', 'ebitda'

8. Crie um Painel para as ações citadas na questão 7, utilizando as mesmas métricas

[voltar](#sobre-o-projeto-final-ptbr)


## Exercício 1 -

```python
-- Obtendo de dados de fechamento ajustado (Adj Close) para 5 ações:

!pip install yfinance
import yfinance as yf
assets = ['PETR4.SA', 'VALE3.SA', 'MGLU3.SA','ITUB4.SA','GOAU4.SA']
adj_close = yf.download (assets , start = '2020-01-01')['Adj Close']
adj_close
```

[voltar](#sobre-o-projeto-final-ptbr)

## Exercício 2 -

```python
-- Usando a biblioteca pandas para analisar estatísticas básicas de cada ação, como: contagem, média, padrão, mínimo, máximo e percentis

import pandas as pd
pd.set_option('display.float_format', '{:.1f}'.format)
adj_close.describe()
```

[voltar](#sobre-o-projeto-final-ptbr)

## Exercício 3 - 
- Plotando as 5 Ações que escolhi![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%201.png)

[voltar](#sobre-o-projeto-final-ptbr)

## Exercício 4 -

```python
-- Padronizando os preços das ações para que todos comecem em 1:
adj_close_std = adj_close/adj_close.iloc[0]
adj_close_std
```

[voltar](#sobre-o-projeto-final-ptbr)

## Exercise 5 - 
- Plotando as ações padronizadas![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%202.png)

[voltar](#sobre-o-projeto-final-ptbr)

## Exercise 6.1 - 
- Medindo o impacto das taxas de juros no mercado financeiro![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%203.png)

[voltar](#sobre-o-projeto-final-ptbr)

## Exercise 6.2 - 
- Medindo o impacto da inflação no mercado financeiro![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%204.png)

[voltar](#sobre-o-projeto-final-ptbr)

## Exercise 7 -

```python
-- Criando um dataframe com fundamentos para as seguintes empresas:
['AAPL', 'MSFT', 'AMZN', 'GOOGL', 'META']
```

[voltar](#sobre-o-projeto-final-ptbr)

## Exercise 8 - 
- creating a Panel with 'EnterpriseValue', 'Revenue', 'ProfitMargin', 'OperatingMargin','dividendRate', 'beta', 'ebitda'![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%205.png)

[voltar](#sobre-o-projeto-final-ptbr)

--------------------------------------------------------------------------

### Principais Bibliotecas utilizadas
```python
YFinance
Nasdaq DataLink
Plotly
```
[voltar](#sobre-o-projeto-final-ptbr)


---------------------------------------------------------------------------------
