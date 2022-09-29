# Curso-MYSQL
Repositorio feito para guardar meus arquivos do curso de MySQL

/* COMO CRIAR CADASTRO */

create database cadastro;
default character set utf8 
default collate utf8_general_ci;

/* COMO CRIAR TABELA */


create table pessoas (
id int not null auto_increment, /* COMANDO ADD UM ID E PREENCHE OS PROXIMOS AUTOMATICAMENTE*/
nome varchar(30) not null unique, /* COMANDO NAO PERMITE QUE OS NOMES SE REPETEM*/
nascimento date,
sexo enum('M', 'F'),
peso decimal(5,2),
altura decimal(3,2),
nacionalidade varchar(30) default 'Brasil',
primary key (id)  /* COMANDO DECLARA QUE ID E A PRIMEIRA COLUNA, CONTINUAÇÃO DO CODIGO ACIMA*/


) default charset = utf8;

/* INSERIR DADOS DE PESSOAS */

INSERT INTO pessoas
(nome, nascimento, sexo, peso, altura, nacionalidade)
VALUES 
('Maria', '1983-02-01', 'F', '78.5', '1.83', 'Brasil'),
('Lidia', '1987-02-01', 'F', '78.5', '1.83', 'Brasil'),
('Cristiane', '1987-02-01', 'F', '78.5', '1.83', 'Brasil'),
('Felipe', '1985-02-01', 'M', '78.5', '1.83', 'Uruguai'),
('Pedro', '1982-02-01', 'M', '78.5', '1.83', 'Brasil'),
('Ana', '1981-02-01', 'F', '78.5', '1.83', 'Uruguai'),
('Luciana', '1987-02-01', 'F', '78.5', '1.83', 'Brasil'),
('Tali', '1987-02-01', 'M', '78.5', '1.83', 'Brasil'),
('Amora Pessoa', '2000-02-01', 'F', '78.5', '1.83', 'Uruguai');

/* VISUALIZAR DADOS DE UMA TABELA*/

select * from pessoas;

/* COMANDO CRIA UMA TABELA DENTRO DA PASTA */

create table if not exists cursos (
nome varchar(30) not null unique,
descricao text,
carga int unsigned,
totalaulas int unsigned,
ano year default '2016'
) default charset = utf8mb3;

alter table cursos
add column idcurso int first;

alter table cursos
add primary key (idcurso);

describe cursos;

insert into cursos values 
('1', 'HTML4','Curso de HTML5', '40', '37', '2014'),
('2', 'Algoritmos', 'Logica de Programação', '20', '57', '2014'),
('3', 'Photoshop', 'Dicas de Photoshp', '20', '10', '2014'),
('4', 'PGP', 'Curso de PHP', '20', '57', '2014'),
('5', 'sapateados', 'Curso de PHP', '40', '20', '2010'),
('6', 'java', 'Introducao', '20', '57', '2014'),
('7', 'MSQL', 'Banco de dados', '20', '57', '2012'),
('8', 'Word', 'Completo', '20', '57', '2014'),
('9', 'Cozinha', 'Arabeo', '20', '57', '2016'),
('10', 'Youtube', 'Gerar', '20', '57', '2014'),
('11', 'Excel', 'Polemica', '20', '57', '2018');
select * from cursos;
 
 
 /*COAMDO INSERE TABELAS AS PASTAS */

INSERT INTO pessoas
(nome, nascimento, sexo, peso, altura, nacionalidade)
VALUES 
('Frederico', '2001-04-06', 'M', '6.8', '1.10', 'Brasil');


('1', 'HTML4', 'Curso de HTML5', '40', '37', '2014'),
('2', 'ALgoritmos', 'Logica de Programação', '20', '57', '2014'),
('3', 'ALgoritmos', 'Logica de Programação', '20', '57', '2014'),
('4', 'ALgoritmos', 'Logica de Programação', '20', '57', '2014'),
('5', 'ALgoritmos', 'Logica de Programação', '20', '57', '2014'),
('6', 'ALgoritmos', 'Logica de Programação', '20', '57', '2014'),
('7', 'ALgoritmos', 'Logica de Programação', '20', '57', '2014'),
('8', 'ALgoritmos', 'Logica de Programação', '20', '57', '2014'),
('9', 'ALgoritmos', 'Logica de Programação', '20', '57', '2014'),
('10', 'ALgoritmos', 'Logica de Programação', '20', '57', '2014')
('11', 'ALgoritmos', 'Logica de Programação', '20', '57', '2014');
select * from cursos;

/* COMANDO ALTERA NOME DA VARIAVEL */
update cursos
set nome = 'HTML5'
where idcurso = '1';


/* COMANDO DELETA UMA LINHA DA TABELA*/

delete fron cursos
where idcurso='8';


