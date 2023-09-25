### Projeto Final do Curso de Verão Trading com Dados em parceria com a FIU Florida International University

#### ⚠️ Sobre o Projeto Final (PT/BR)
#### ⭐ About the Final Project (EN/US)
😊

### Instruções (PT/BR)

## Banco de Dados para Projeto Final do Curso Ciência de Dados by DIO - IFood


- [Desafio Parte 1: Criando o Diagrama no MysSQL Workbench](#desafio-parte-1---diagrama-do-banco-de-dados)


- [Desafio Parte 2: Criando o Script das Tabelas e Constraints](#desafio-parte-2---script-das-tabelas-e-constraints)


- [Desafio Parte 3: Inserindo Dados no Banco via MySQL](#desafio-parte-3---inserindo-dados-no-banco-via-mysql)


- [Desafio Parte 4: Criando Queries](#desafio-parte-4---criando-queries)


## Desafio Parte 1 - Diagrama do Banco de Dados
[DIAGRAMA DO BANCO DE DADOS]![image](https://github.com/wellingtonb3/ecommerce-ifood/assets/130426959/ee1cd04e-43a8-4763-93ff-4bc6a208a4f8)

[VOLTAR](#ecommerce-ifood)

## Desafio Parte 2 - Script das Tabelas e Constraints

### Criando o Banco de Dados

```mysql
-- criação do banco de dados para o cenário de E-commerce

create database ecommerce1;
use ecommerce1;
```



### Criando a Tabela Cliente

```mysql
create table clients(
	idClient int auto_increment primary key,
        type_client ENUM('Pessoa Física', 'Pessoa Jurídica') not null,
        cpf char(11),
        fname varchar(10),
        minit char(3),
        lname varchar(20),
        cnpj char(14),
        businessname varchar(255),
        address varchar(30),
        phone_number varchar(11) not null,
        constraint unique_cpf_client unique (cpf),
        constraint unique_cnpj_client unique (cnpj)
);

alter table clients auto_increment = 1;

desc clients;
```

------------------------------------------------------------------------

### Criando a Tabela Produto

```mysql
create table product(
	idProduct int auto_increment primary key,
	pname varchar (10) not null, 
	category enum("Eletrônicos","Vestuario","Brinquedos","Alimentos","Móveis") not null,
	for_kids bool default false,
	review float default 0,
	dimensions varchar(10)
);

alter table product auto_increment = 1;
```


--------------------------------------------------------------------------

### Criando a Tabela Pedido
```mysql

 create table orders(
	idOrder int auto_increment primary key,
	idOrderClient int,
	orderstatus ENUM("Cancelado", "Confirmado", "Em processamento") default "Em processamento",
	orderdescription varchar(255),
	freight float default 10,
	delivery ENUM ('Em preparação','Enviado', 'Entregue', 'Extraviado') default "Em preparação",
        delivery_number varchar(20),
        constraint fk_orders_client foreign key (idOrderClient) references clients(idClient)                
);

alter table orders auto_increment = 1;

desc orders;
```

-------------------------------------------------------------------------


### Criando a tabela Estoque
```mysql

create table productstock(
	idProdStock int auto_increment primary key,
	stocklocation varchar(255),
	quantity int default 0
);

alter table productstock auto_increment = 1;
```


-------------------------------------------------------------------------

### Criando a tabela Fornecedor
```mysql

create table supplier(
	idSupplier int auto_increment primary key,
	businessname varchar(255) not null,
	cnpj char(15) not null,
        phone_number varchar(11) not null,
        constraint unique_supplier unique (cnpj)
);
alter table supplier auto_increment = 1;
desc supplier;
```


-----------------------------------------------------------------------

### Criando a tabela Vendedor CNPJ
```mysql

create table seller(
	idSeller int auto_increment primary key,
	businessname varchar(255) not null,
        companyname varchar(255) not null,
        address varchar(255),
	cnpj char(15),
        cpf char(9),
        contact char(11) not null,
        constraint unique_cnpj_seller unique (cnpj),
        constraint unique_cpf_seller unique (cpf)
);

alter table seller auto_increment = 1;
```


-----------------------------------------------------------------------

### Criando a tabela Produtos Vendedor
```mysql

create table product_seller(
	idPseller int,
	idProduct int,
	prodquantity int default 1,
	primary key (idPseller, idProduct),
	constraint fk_product_seller foreign key (idPseller) references seller (idSeller),
	constraint fk_product_product foreign key (idProduct) references product (idProduct)
);

desc product_seller;
```


-------------------------------------------------------------------------

### Criando a tabela Produto / Pedido
```mysql

create table productorder(
	idPOproduct int,
	idPOorder int,
	poquantity int default 1,
	postatus enum ("Disponível","Sem estoque") default "Disponível",
	primary key (idPOproduct, idPOorder),
	constraint fk_productorder_seller foreign key (idPOproduct) references product(idProduct),
	constraint fk_productorder_product foreign key (idPOorder) references orders(idOrder)
);
```


--------------------------------------------------------------------------

### Criando a tabela Localização do Estoque
```mysql

create table stocklocation(
	idLproduct int,
	idLstock int,
	location varchar(255) not null,
	primary key (idLproduct, idLstock),
	constraint fk_stock_location_product foreign key (idLproduct) references product(idProduct),
	constraint fk_stock_location_stock foreign key (idLstock) references productStock(idProdStock)
    );
```



---------------------------------------------------------------------------


### Criando a tabela Produto Fornecedor
```mysql

create table productsupplier(
	idPsSupplier int,
	idPsProduct int,
	quantity int not null,
	primary key (idPsSupplier, idPsProduct),
	constraint fk_product_supplier_supplier foreign key (idPsSupplier) references supplier(idSupplier),
	constraint fk_product_supplier_product foreign key (idPsProduct) references product (idProduct)
);
desc productsupplier;
```


-----------------------------------------------------------------------------

### Criando a tabela Pagamento
```mysql

create table payment(
	idPayment int auto_increment primary key,
	idOPayment int,
	total_value decimal(10,2) not null,
	payment_date date not null,
	type_payment enum ("Boleto", "Cartão de Crédito", "Dois Cartões") not null default "Cartão de Crédito",
	card_number VARCHAR(16),
	expiration_date date,
	security_code varchar(3),
	bank_slipcode varchar(20),
	constraint fk_order_payment foreign key (idOPayment) references orders (idOrder),
	constraint fk_client_payment foreign key (idPayment) references clients (idClient)
);
alter table payment auto_increment = 1;

desc payment;
```


--------------------------------------------------------------------------

### Comandos úteis
```mysql
-- show tables;
-- show databases;
-- use information_schema;
-- show tables;
-- desc table_constraints;
-- desc referential_constraints;
-- select * from referential_constraints;
-- select * from referential_constraints where constraint_schema = 'ecommerce1';''''
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

### Populando a tabela Produtos
```mysql

desc product;
-- idProduct, pname, category ('Eletrônicos','Vestuario','Brinquedos','Alimentos','Móveis'), for_kids boolean, review, dimensions(10)

insert into product (pname, category, for_kids, review, dimensions) values
	('Gabinete', 'Eletrônicos', false, '5', null),
        ('Bombons', 'Alimentos', false, '5', null),
        ('GeForce', 'Eletrônicos', false, '5', null),
        ('Estante', 'Móveis', false, '3', null),
        ('Super Mar', 'Brinquedos', true, '4', null),
        ('Calça Big', 'Vestuario', false, '4', null);

select * from product;
```

---------------------------------------------------------------------------

### Populando a tabela Pedidos
```mysql

desc orders;
-- idOrder, idOrderClient, orderstatus, orderdescription, freight, delivery, delivery_number

insert into orders (idOrderClient, orderstatus, orderdescription, freight, delivery, delivery_number) values
	(8, 'Em processamento', 'Webserver3', 22, 'Em preparação', null ),
        (9, 'Confirmado', 'Webserver2', 27, 'Enviado', 'BC234654367BR'),
        (10, 'Em processamento', 'WebServer1', 12, 'Em preparação', 'AB376347656BR'),
        (11, 'Cancelado', 'Webserver2', 19, null, null);

select * from orders;
```

------------------------------------------------------------------------

### Populando a tabela Produto / Pedido
```mysql

desc productorder;
-- idPOproduct, idOorder, poquantity, postatus

insert into productorder (idPOproduct, idPOorder, poquantity, postatus) values
	(1,5,2,default),
        (2,6,1,default),
        (3,7,1,default);

select * from productorder;
```

---------------------------------------------------------------------------

### Populando a tabela Estoque Localização
```mysql

desc productstock;

insert into productstock (stocklocation, quantity) values
	('São Paulo', 1000),
        ('Santa Catarina', 400),
        ('São Paulo', 250),
        ('Minas Gerais', 1000),
        ('Rio de Janeiro', 230),
        ('Alagoas', 3000);

select * from productstock;
```
                        
---------------------------------------------------------------------

### Populando a tabela Estoque UF
```mysql

desc stocklocation;

insert into stocklocation (idLproduct, idLstock, location) values
	(1, 2, 'SP'),
        (2, 5, 'MG');

select * from stocklocation;
```

----------------------------------------------------------------------

### Populando a tabela Fornecedor
```mysql

desc supplier;
-- idSupplier, businessname, cnpj, phone_number

insert into supplier (businessname, cnpj, phone_number)values
	('Lan Distribuidora',386556730001-54,'34 34664455'),
        ('Max Produtos',824556730001-54,'34 34664455'),
        ('STC Alimentos' ,453956730001-54,'34 34664455');

select * from supplier;
```

---------------------------------------------------------------------------

### Populando a tabela Vendedor
```mysql

desc seller;
-- idSeller, businessname, companyname, address, cnpj, cpf, contact

insert into seller (businessname, companyname, address, cnpj, cpf, contact) values
	('Randi ltda', 'Devox', 'Rua Treze, 415 - Landau - Bahia', 543743540001-56, 346756712, 7134556677),
        ('DVX S/C', 'Ritx', 'Av Eng Heitor, 741 - Amazu - Santa Catarina', 562347450001-65, 744756722, 7139673474),
        ('Lauaz ltda ME', 'Sac', 'Rua Treze, 658 - Landau - Alagoas', 456783540001-16, 256756755, 5157445655);

select * from seller;   
```

-------------------------------------------------------------------------

### Populando a tabela Produto / Vendedor
```mysql

desc product_seller;
-- idPseller, idProduct, prodquantity

insert into product_seller (idPseller, idProduct, prodquantity) values
	(1, 2, 4500),
        (1, 3, 1500),
        (3, 4, 440),
        (2, 5, 500),
        (1, 611, 100);

select * from product_seller;
```

----------------------------------------------------------------------

### Populando a tabela Produto Fornecedor
```mysql

desc productsupplier;

insert into productsupplier (idPsSupplier, idPsProduct, quantity) values
	(1, 2, 4500),
        (1, 3, 1500),
        (3, 4, 440),
        (2, 5, 500),
        (1, 6, 100);

select * from productsupplier;
```

-------------------------------------------------------------------------

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


## Desafio Parte 4 - Criando Queries


### Formulando perguntas e respondendo com as Queries


*SELECIONE OS PEDIDOS EFETUADOS COM OS DADOS DE SEUS DEVIDOS COMPRADORES*

```mysql
select * from clients inner join orders ON idClient = idOrderClient;
```
-- ou
```mysql
select * from clients as c, orders as o where (c.idClient = o.idOrderClient);
```
---------------------------------------------------------------------------

  
*SELECIONE TODOS OS CLIENTES SEPARANDO POR PESSOA FÍSICA E JURÍDICA*
```mysql
select * from clients order by type_client;
```
---------------------------------------------------------------------------

  
*SELECIONE O TELEFONE DO CLIENTE COM ID NUMERO 8*
```mysql
select phone_number FROM clients where idClient = 8;
```
---------------------------------------------------------------------------
*VERIFIQUE QUAL A QUANTIDADE DE PRODUTOS DISPONÍVEIS EM SP*
```mysql
select sum(quantity) from productstock where stocklocation = 'São Paulo';
```
---------------------------------------------------------------------------
*SELECIONE OS PRODUTOS DISPONÍVEIS, SUAS QUANTIDADES E LOCALIDADES*
```mysql
select p.pname, ps.stocklocation, quantity from product as p, productstock as ps where idProduct = idProdStock;
```
---------------------------------------------------------------------------
*SELECIONE OS PEDIDOS QUE FORAM PAGOS POR BOLETO BANCÁRIO*

```mysql
select *  from payment where bank_slipcode > 0;
```
---------------------------------------------------------------------------
*SELECIONE OS PEDIDOS QUE FORAM PAGOS POR CARTÃO DE CRÉDITO*
```mysql
select *  from payment where card_number > 0;
```
---------------------------------------------------------------------------
*SELECIONE OS PEDIDOS QUE ESTÃO EM PREPARAÇÃO*
```mysql
select * from orders where delivery = "Em preparação";
```
---------------------------------------------------------------------------
### Comandos úteis para verificação das tabelas
```mysql
show tables;
select * from clients;
select * from orders;
select * from payment;
select * from product;
select * from product_seller;
select * from productorder;
select * from productstock;
select * from productsupplier;
select * from seller;
select * from stocklocation;
select * from supplier;
```


[VOLTAR](#ecommerce-ifood)





