## Projeto Final do Curso de Verão Trading com Dados em parceria com a FIU Florida International University

<center><img src = "https://github.com/victorncg/pythonforfinance/blob/main/Captura%20de%20tela%202023-07-14%20144104.png?raw=true" width = "600">

#### ⚠️ Sobre o Projeto Final (PT/BR)
#### ⭐ About the Final Project (EN/US)


#### ⚠️ Sobre o Projeto Final (PT/BR)

Depois das aulas semanais, na qual pudemos aprender toda a introdução de Python e algumas Bibliotecas necessárias para o Mercado Financeiro, tivemos que executar nosso trabalho final em cima das seguintes questões:


1. Obtenha dados de fechamento ajustado (Adj Close) para 5 ações de sua preferência (podem ser de qualquer país)

2. Para entendermos o comportamento desses dados, utilize a biblioteca pandas para analisar estatísticas básicas de cada ação, como: contagem, média, padrão, mínimo, máximo e percentis.

3. Plote essas ações usando a biblioteca plotly

4. Agora padronize os preços das ações para que todos comecem em 1. Crie um novo dataframe com esses dados.

5. Plote os novos dados padronizados usando a biblioteca plotly

6. Agora vamos medir o impacto da inflação e das taxas de juros no mercado financeiro.

Usando o que você aprendeu neste curso, crie:

um gráfico de 2 eixos das taxas de juros e do S&P 500 usando plotly.
um gráfico de 2 eixos da inflação e do S&P 500 usando plotly.
Dica: use o que você aprendeu no Módulo 02. Além disso, o símbolo do S&P 500 na biblioteca yfinance é "^GSPC"

7. Vamos criar um dataframe com fundamentos para as seguintes empresas:
['AAPL', 'MSFT', 'AMZN', 'GOOGL', 'META']


Você deve obter os seguintes fundamentos:

'MarketCap', 'EnterpriseValue', 'Receita', 'ProfitMargin', 'OperatingMargin', 'dividendRate', 'beta', 'ebitda'

8. Crie um painel para as ações citadas na questão 7, utilizando as mesmas métricas



## Exercício 3 - 
- [DIAGRAMA DO BANCO DE DADOS]![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%201.png)

## Exercício 5 - 
- [DIAGRAMA DO BANCO DE DADOS]![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%202.png)

## Exercício 6.1 - 
- [DIAGRAMA DO BANCO DE DADOS]![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%203.png)

## Exercício 6.2 - 
- [DIAGRAMA DO BANCO DE DADOS]![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%204.png)

## Exercício 8 - 
- [DIAGRAMA DO BANCO DE DADOS]![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%205.png)



--------------------------------------------------------------------------

### Bibliotecas Utilizadas
```python
YFinance
Nasdaq DataLink
Plotly
```

[VOLTAR](#ecommerce-ifood)


## Desafio Parte 3 - Inserindo Dados no Banco via MySQL


### Acessando o Banco de Dados
```mysql

use ecommerce1;
show tables;
```
---------------------------------------------------------------------------


### Populando a tabela Pagamento
```python

desc payment;

insert into payment (idOPayment, total_value, payment_date, type_payment, card_number, expiration_date, security_code, bank_slipcode) values
        (5, 229.00, '2023-04-12', default, 4533432275643544, '2027-05-01', 321, null),
        (6, 124.00, '2023-02-28', 'Boleto', null, null, null, 42376598765367845345),
        (7, 329.00, '2023-04-14', default, 1267432275643544, '2028-05-01', 221, null),					
        (8, 125.00, '2023-03-28', 'Boleto', null, null, null, 16776598765367845345);

select * from payment;
```

---------------------------------------------------------------------------

[VOLTAR](#ecommerce-ifood)


#### ⭐ About the Final Project (EN/US)

You should follow the steps described below and at the end, share your final notebook with us.

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
['AAPL', 'MSFT', 'AMZN', 'GOOGL', 'META']

You should obtain the following fundamentals:

'MarketCap', 'EnterpriseValue', 'Revenue', 'ProfitMargin', 'OperatingMargin','dividendRate', 'beta', 'ebitda'

8. Create a panel for the stocks mentioned in question 7, using the same metrics


## Exercise 3 - 
- [DIAGRAMA DO BANCO DE DADOS]![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%201.png)

## Exercise 5 - 
- [DIAGRAMA DO BANCO DE DADOS]![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%202.png)

## Exercise 6.1 - 
- [DIAGRAMA DO BANCO DE DADOS]![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%203.png)

## Exercise 6.2 - 
- [DIAGRAMA DO BANCO DE DADOS]![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%204.png)

## Exercise 8 - 
- [DIAGRAMA DO BANCO DE DADOS]![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%205.png)





