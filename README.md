## Projeto Final do Curso de Verão Trading com Dados em parceria com a FIU Florida International University

<center><img src = "https://github.com/victorncg/pythonforfinance/blob/main/Captura%20de%20tela%202023-07-14%20144104.png?raw=true" width = "600">

#### ⚠️ Sobre o Projeto Final (PT/BR)
#### ⭐ About the Final Project (EN/US)
😊

### Instruções (PT/BR)



- [Desafio Parte 1: Criando o Diagrama no MysSQL Workbench](#desafio-parte-1---diagrama-do-banco-de-dados)


- [Desafio Parte 2: Criando o Script das Tabelas e Constraints](#desafio-parte-2---script-das-tabelas-e-constraints)


- [Desafio Parte 3: Inserindo Dados no Banco via MySQL](#desafio-parte-3---inserindo-dados-no-banco-via-mysql)


- [Desafio Parte 4: Criando Queries](#desafio-parte-4---criando-queries)


## Desafio Parte 1 - Diagrama do Banco de Dados
[DIAGRAMA DO BANCO DE DADOS]![image](https://github.com/wellingtonb3/TradingcomDados-FIU/blob/main/newplot%201.png)

[VOLTAR](#ecommerce-ifood)




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

### Populando a tabela Clientes
```mysql

desc clients;
-- idClient, type_client, cpf, fname, minit, lname, cnpj, businessname, address, phone_number

insert into clients (type_client, cpf, fname, minit, lname, cnpj, businessname, address, phone_number) values
	('Pessoa_Física', '29537472910','Maria', 'E', 'Ferreira', null , null, 'Av Treze 41, Jamba - Gusmão', '31 45983385'),
        ('Pessoa_Jurídica', null, null, null, null, 45284901000321, 'Acording System', 'Rua Jota 32, Pamonhas - Jequi', '41 45983210'),
	('Pessoa_Física', '29347472910','Maria', 'E', 'Ferreira', null , null, 'Av Treze 41, Jamba - Gusmão', '31 45983385'),
        ('Pessoa_Física', '48302769178', 'José', 'G', 'Alandra', null, null, 'Rua Santa 52, Gara - Jarandi', '11 49603377'),
        ('Pessoa_Jurídica', null, null, null, null, 47295789000156, 'Pururu Aços', 'Rua Jota 32, Pamonhas - Jequi', '21 55983567'),
        ('Pessoa_Física', '48702769331', 'José', 'G', 'Alandra', null, null, 'Rua Dio 36, Ilha - Betiquita', '15 39563355'),
	('Pessoa_Jurídica', null, null, null, null, 29367912000177, 'Casa Móveis', 'Rua Gari 26, Camba - Jetu', '21 46333567');
          
select * from clients;
```

---------------------------------------------------------------------------




### Populando a tabela Pagamento
```mysql

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





