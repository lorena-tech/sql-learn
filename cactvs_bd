drop database cactvs_bd;

create database cactvs_bd;

use cactvs_bd;

/*email, senha, nome = cadastro
foto, cep, sexo = perfil (nao obrigatorio)
ativo=php*/
create table usuario (
cod_usuario int primary key auto_increment,
email varchar(100) unique not null,
senha varchar(100) not null,
nome varchar(50) not null,
ativo bool not null,
foto varchar (1000));

/*nao usa nada*/
create table adm (
cod_adm int primary key auto_increment,
usuario varchar (100) unique not null,
senha varchar (100) not null,
ativo bool not null);
 
create table filme (
cod_filme int primary key auto_increment,
sinopse varchar (3000) not null,
diretor varchar(100) not null,
produtora varchar(100) not null,
premio varchar(100) not null,
ano varchar (4) not null,
titulo varchar(100) not null unique,
genero varchar(100) not null,
nota varchar (100) not null,
ativo bool not null,
idioma varchar(50) not null,
onde_assistir varchar(200) not null,
classificacao varchar (50) not null,
foto varchar (1000) not null,
ator varchar (200) not null);

create table serie (
cod_serie int primary key auto_increment,
titulo varchar(200) not null unique,
produtora varchar(200) not null,
ano varchar(4) not null,
criador varchar (100) not null,
premio varchar(100) not null,
genero varchar(50) not null,
ativo bool not null,
sinopse varchar(3000) not null,
nota varchar (100) not null,
idioma varchar(20) not null,
onde_assistir varchar(200) not null,
classificacao varchar (50) not null,
foto varchar (1000) not null,
logo varchar (2000) not null,
ator varchar (200) not null);

create table temporada(
cod_temp int primary key auto_increment,
ativo bool not null,
num_temporada varchar (4) not null,
qtd_ep varchar(100),
ano varchar(4) not null,
cod_serie int not null,
foreign key(cod_serie) references serie(cod_serie));
 
create table episodio(
cod_ep int primary key auto_increment,
titulo varchar(100) not null,
numero_ep varchar(4) not null,
descricao varchar(1000) not null,
ativo bool not null,
cod_temp int not null,
foreign key(cod_temp) references temporada(cod_temp));

create table filmes_favoritados(
cod_usuario int,
cod_filme int,
ativo bool not null,
foreign key(cod_usuario) references usuario(cod_usuario),
foreign key(cod_filme) references filme(cod_filme));

create table visualiza(
cod_usuario int,
cod_serie int,
ativo bool not null,
foreign key(cod_usuario) references usuario(cod_usuario),
foreign key(cod_serie) references serie(cod_serie));


create table lembrete (
cod_lembrete int primary key auto_increment,
mensagem varchar(300) not null,
lembrete_data datetime not null);

insert into filme(titulo, ano, premio, ator, idioma, diretor, genero, produtora, sinopse, onde_assistir, nota, classificacao, foto, ativo)
values("Esquadrão Suicida", "2016", "Oscar de Melhor Maquiagem e Penteado", "Will Smith", "Inglês", "David Ayer", "Ação", "Warner Bros, Pictures", "Um time dos mais perigosos e encarcerados supervilões são contratados por uma agência secreta do governo, para combater uma poderosa entidade. No entanto, quando eles percebem que não foram escolhidos apenas para ter sucesso, mas também por sua óbvia culpa quando inevitavelmente falharem, terão que decidir se vale a pena ou não continuar correndo risco de morte.", "Netflix", "27%", "12", "Esquadrão Suicida.jpg", true);

insert into serie(titulo, ano, premio, ator, idioma, criador, genero, produtora, sinopse, onde_assistir, nota, classificacao, foto, logo, ativo)
values("Você", "2018", "6º lugar na lista de melhores séries do ano pelo The New York Times", "Elizabeth Lail", "Inglês", "Greg Berlanti", "Suspense", "Netflix", "Guinevere Beck (Elizabeth Lail) é uma aspirante a escritora, que vê sua vida mudar completamente ao entrar em uma livraria no East Village, onde conhece o charmoso gerente, Joe Goldberg (Penn Badgley). Assim que a conhece, Joe tem certeza de que ela é a garota dos seus sonhos, e fará de tudo para conquistá-la — usando a internet e as redes sociais para descobrir tudo sobre Beck. O que poderia ser visto como paixão se transforma em uma obsessão perigosa, uma vez que Joe não vai medir esforços para tirar de seu caminho tudo e todos que podem ameaçar seus objetivos.", "Netflix", "93%", "16", "Você.jpg", "vc-logo.png", true);

insert into temporada(qtd_ep, ano, cod_serie, num_temporada, ativo)
values("10", "2018", 1, "1", true);

insert into episodio(titulo, numero_ep, descricao, cod_temp, ativo)
values("Piloto","1","Joe conhece e se apaixona por Beck e a acompanha nas redes social para descobrir tudo sobre ela. Quando percebe a chance de um amor real, algumas coisas ficam no caminho, como o ex dela, Benji.", 1, true),
("O último cara legal em Nova Yorque","2","Beck e Joe têm um primeiro encontro de verdade. Joe faz tudo que pode para conquistar Beck, mas ela está pensando em seu ex, Benji.", 1, true),
("Talvez","3","Beck não está certa de que Joe é o escolhido, então ele se propõe a provar que seria um ótimo namorado. Equilibrar esse momento importante em sua relação florescente com as manobras complicadas que ele tem feito nos bastidores é um desafio para Joe.", 1, true),
("O capitão","4","Beck sai da cidade para se encontrar com o homem que está lhe enviando mensagens de texto; Joe segue e fica chocado com o que encontra. Beck percebe que ela e Joe vão ter que trazer um nível assustador de verdade e autenticidade para sua conexão.", 1, true),
("Vivendo com o inimigo","5","Beck sai da cidade para se encontrar com o homem que está lhe enviando mensagens de texto; Joe segue e fica chocado com o que encontra. Beck percebe que ela e Joe vão ter que trazer um nível assustador de verdade e autenticidade para sua conexão.", 1, true),
("Amour fou","6","A devoção de Joe a Beck leva ele a uma casa de verão estranhamente remota e a um encontro face a face com um adversário igualmente obcecado que tem a mesma intenção de possuir seu coração.", 1, true),
("Um relacionamento especial","7","Joe fornece um ombro para se apoiar depois que Beck sofre uma perda; incapaz de abalar a preocupação e o ciúme que ainda sente, Joe se esforça para explorar seus medos; Beck começa a suspeitar que ela está sendo seguida.", 1, true),
("Eu sou seu, meu bem!","8","Um encontro casual faz com que Joe e Beck decidam a direção que querem que sua história siga.", 1, true),
("Candace","9","Beck não pode abalar a sensação de que há mais na história do amor perdido de Joe, Candace. Determinado a descobrir a verdade, é a vez de Beck ir a extremos chocantes para descobrir a verdade sobre Joe. Mas ela pode ter ido longe demais.", 1, true),
("O castelo do barba azul","10","As verdades mais profundas de Beck são reveladas; Joe vai ao limite do que ele fará por amor.", 1, true);


insert into serie(titulo, ano, premio, ator, idioma, criador, genero, produtora, sinopse, onde_assistir, nota, classificacao, foto, ativo, logo)
values("Bojack Horseman", "2014", "Critics' Choice Television Award de Melhor Série Animada", "Will Arnett", "Inglês", "Raphael Bob-Waksberg", "Animação", "Netflix", "BoJack Horseman, um cavalo humanoide, busca um retorno a Hollywood anos depois de sua fama como estrela de uma sitcom nos anos 1990. Com a ajuda de um amigo humano e sua ex-namorada felina, ele se esforça para recuperar sua carreira e sua dignidade.", "Netflix", "93%", "16", "Bojack Horseman.jpg", true, "Bojack Horseman-logo.png");

insert into temporada(qtd_ep, ano, cod_serie, ativo, num_temporada)
values("10", "2014", 2, true, "1");

insert into episodio(titulo, numero_ep, descricao, cod_temp, ativo)
values("episodio 1","1","descricao episodio 1", 2, true),
("episodio 2","2","descricao episodio 2", 2, true),
("episodio 3","3","descricao episodio 3", 2, true),
("episodio 4","4","descricao episodio 4", 2, true),
("episodio 5","5","descricao episodio 5", 2, true),
("episodio 6","6","descricao episodio 6", 2, true),
("episodio 7","7","descricao episodio 7", 2, true),
("episodio 8","8","descricao episodio 8", 2, true),
("episodio 9","9","descricao episodio 9", 2, true),
("episodio 10","10","descricao episodio 10", 2, true);


insert into adm (usuario, senha, ativo) values ("adm", "123", 1);

insert into usuario (email, senha, nome, ativo, foto) values ("maurilio.anjos@gmail.com", "123", "Maurilio", 1, "maurilio.jpg");
insert into usuario (email, senha, nome, ativo, foto) values ("cult@gmail.com", "123", "Cult", 1, "caradecult.jpg");
