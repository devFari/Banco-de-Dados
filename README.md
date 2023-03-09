# Banco-de-Dados
Código do Salão Suzana HAIR



create database salao(

create tabe clientes(
	id_cliente 		varchar (11) not null,
	nome 			varchar (40) not null,
	tel 			varchar (11) not null,
	endereço 		varchar (50) not null,
	idade 			date not null,
	cabelo 			varchar (20) not null,
	primary key (id_cliente),

);

create table funcionario(
	id_funco 		varchar (11) not null,
	nome 			varchar (40) not null,
	funcao 			varchar (40) not null,
	data_cont 		date not null
	primary key (id_func),

);

create table produto(
	id_produto 	smallint not null,
	marca 		varchar (20) not null,
	finalidade 	varchar (20) not null
	validade 	date not null,
	quant 		smallint not null,
	lot 		int not null,
	primary key (id_produto),

);

create table servico(
	id_cliente 	varchar(11) not null 	REFERENCES CLIENTE (id_cliente),
	cliente		varchar(40) not null 	REFERENCES CLIENTE (nome),
	id_func		varchar(11) not null 	REFERENCES FUNCIONARIO (id_func),
	funcionario 	varchar(40) not null 	REFERENCES FUNCIONARIO (nome),
	id_produto 	smallint not null 	REFERENCES PRODUTO (id_produto),
	data date not null,

);



-- alimentando o bd
-- tabela cliente

insert into cliente values("19355785689",	"Britney",	"81955569288",	"R Barão de Itamaracá N 958",2002-02-11,	"Cacheado/castanho");
insert into cliente values("89549722489",	"Amanda",	"81940048926",	"R Jão Cabral N892",1995-05-15,			"liso/loiro");
insert into cliente values("21238576941",	"Ediane",	"81995880117",	"R Ernesto Dias Lopes N88",1980-11-17,		"Ondulado/grizalho");
insert into cliente values("19259786622",	"Hilary",	"81979152468",	"R Joaquim Bezerra N 22",2000-12-09,		"liso/loiro");
insert into cliente values("59288867197",	"Yasmim",	"81955589752",	"R Antônio de Goes N 825",2005-11-27,		"cabelo");



-- alimentando tabela funcionario

insert into cliente values("11157296874",	"Rochele",	"Cabeleleira",	2022-11-07,);
insert into cliente values("89756342851",	"Lohany",	"Manicure",	2022-07-15,);
insert into cliente values("23568945211",	"Kenia",	"Cabeleleira",	2022-05-29,);
insert into cliente values("46813546288",	"Milena",	"Cabeleleira",	2023-01-20,);
insert into cliente values("35915725800",	"Bianca",	"Esteticista",	2022-04-01,);


-- alimentando tabela produtos

insert into produtos values(1,	"Salonline",	"Hidratação",			2025-03-01,	30,	307255981)
insert into produtos values(2,	"Niely Gold",	"Creeme de Cabelo",		2025-03-01,	15,	153246824)
insert into produtos values(3,	"Impala",	"Esmalte Transaparente",	2023-05-01,	09,	462597584)
insert into produtos values(4,	"MAXTON",	"Tinta cab. ruivo",		2024-01-01,	40,	465130247)
insert into produtos values(5,	"X&D",		"Gel unha",			2023-07-01,	20,	501206598)



-- alimentando tabela serviço

insert into servico values("19355785689",	"Britney",	"11157296874",	"Rochele",	1,	2023-03-03)
insert into servico values("89549722489",	"Amanda",	"89756342851",	"Lohany",	5,	2023-02-12)
insert into servico values("21238576941",	"Ediane",	"23568945211",	"Kenia",	3,	2023-02-24)
insert into servico values("19259786622",	"Hilary",	"46813546288",	"Milena",	2,	2023-01-29)
insert into servico values("59288867197",	"Yasmim",	"35915725800",	"Bianca",	4,	2023-03-01)

