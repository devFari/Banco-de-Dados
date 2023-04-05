# Banco-de-Dados
Código do Salão Suzana HAIR



CREATE DATABASE salao(

CREATE TABLE cliente (
    id_cliente VARCHAR (11) PRIMARY KEY
                            NOT NULL,
    nome       VARCHAR (40) NOT NULL,
    tel        VARCHAR (11) NOT NULL,
    endereco   VARCHAR (50) NOT NULL,
    idade      DATE         NOT NULL,
    cabelo     VARCHAR (20) NOT NULL
);

CREATE TABLE funcionario (
    id_func   VARCHAR (11) PRIMARY KEY
                           NOT NULL,
    nome      VARCHAR (40) NOT NULL,
    funcao    VARCHAR (40) NOT NULL,
    data_cont DATE         NOT NULL
);


CREATE TABLE produto (
    id_produto SMALLINT     PRIMARY KEY
                            NOT NULL,
    marca      VARCHAR (20) NOT NULL,
    finalidade VARCHAR (20) NOT NULL,
    validade   DATE         NOT NULL,
    quant      SMALLINT     NOT NULL,
    lot        INTEGER      NOT NULL
);

CREATE TABLE servico (
    id_cliente       REFERENCES cliente (id_cliente) DEFERRABLE
                     NOT NULL,
    cliente          REFERENCES cliente (nome) DEFERRABLE
                     NOT NULL,
    id_func          REFERENCES funcionario (id_func) DEFERRABLE
                     NOT NULL,
    funcionario      REFERENCES funcionario (nome) DEFERRABLE
                     NOT NULL,
    id_produto       REFERENCES produto (id_produto) DEFERRABLE
                     NOT NULL,
    data        DATE NOT NULL
);
);
