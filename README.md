# PIZZARIA-SQL-SISTEMA

CREATE TABLE receitas(

id integer	PRIMARY KEY	autoincrement,
instruções	varchar,
autor		varchar
);

INSERT INTO receitas(instruções,autor)VALUES

('abra a massa, coloque o molho e quejo de tomate, coloque os ingredientes da pizza acima do queijo e coloque no forno', 'Caetano Bernardo');

create TABLE embalagem(

id		integer PRIMARY KEY autoincrement,
material	varchar,
tamanho		double,
preco		double
); INSERT INTO embalagem(material,tamanho,preco)values

('plastico', 45.00, 2.50), ('papelão', 45.00, 1.25), ('plastico degradavel', 40.00, 4.15);

create TABLE pizza(

id				integer PRIMARY KEY autoincrement,
ingredientes	varchar,
sabor			varchar,
preco			double,
descricão		varchar,
tamanho			double,
id_embalagem	integer,
id_receitas		integer,

FOREIGN KEY (id_embalagem) REFERENCES embalagem(id),
FOREIGN KEY (id_receitas) REFERENCES receitas(id)
);

INSERT INTO pizza(ingredientes,sabor,preco,descricão,tamanho,id_embalagem)VALUES

('massa, quiejo, calabresa, cebola', 'calabresa', 28.99, 'pizza de calabresa com cebola', 28.00, 1),

('massa, quiejo, presunto, cebola, ovo, milho', 'portuguesa', 28.99, 'pizza portuguesa completa com', 28.00, 2),

('massa, tomate, quiejo', 'queijo', 28.99, 'pizza de calabresa com cebola', 28.00, 3),

('massa, queijo, calabresa, cebola', 'Calabresa com Cebola', 28.99, 'Pizza de calabresa com cebola', 28.00, 1),

('massa, queijo, frango, catupiry', 'Frango com Catupiry', 25.99, 'Pizza de frango com catupiry', 28.00, 2), ('massa, queijo, presunto, milho', 'Presunto e Milho', 27.50, 'Pizza de presunto e milho', 30.00, 3),

('massa, queijo, bacon, cebola', 'Bacon e Cebola', 29.99, 'Pizza de bacon com cebola', 30.00, 1),

('massa, queijo, marguerita', 'Marguerita', 26.50, 'Pizza de marguerita', 30.00, 2),

('massa, queijo, peperoni', 'Peperoni', 28.50, 'Pizza de peperoni', 32.00, 3),

('massa, queijo, quatro queijos', 'Quatro Queijos', 31.99, 'Pizza quatro queijos', 32.00, 1),

('massa, queijo, camarão, catupiry', 'Camarão com Catupiry', 35.99, 'Pizza de camarão com catupiry', 32.00, 2),

('massa, queijo, atum, cebola', 'Atum e Cebola', 32.50, 'Pizza de atum com cebola', 36.00, 3),

('massa, queijo, calabresa, palmito', 'Calabresa e Palmito', 33.50, 'Pizza de calabresa com palmito', 36.00, 1),

('massa, queijo, frango, cheddar', 'Frango com Cheddar', 30.99, 'Pizza de frango com cheddar', 36.00, 2), ('massa, queijo, vegetariana', 'Vegetariana', 29.50, 'Pizza vegetariana', 38.00, 3),

('massa, queijo, carne seca, catupiry', 'Carne Seca com Catupiry', 34.99, 'Pizza de carne seca com catupiry', 38.00, 1),

('massa, queijo, portuguesa', 'Portuguesa', 32.50, 'Pizza portuguesa', 38.00, 2),

('massa, queijo, frango com requeijão', 'Frango com Requeijão', 31.99, 'Pizza de frango com requeijão', 40.00, 3),

('massa, queijo, lombo, abacaxi', 'Lombo com Abacaxi', 33.50, 'Pizza de lombo com abacaxi', 40.00, 1),

('massa, queijo, mussarela de búfala, tomate seco', 'Mussarela de Búfala e Tomate Seco', 35.99, 'Pizza de mussarela de búfala com tomate seco', 40.00, 2),

('massa, queijo, palmito, champignon', 'Palmito com Champignon', 32.50, 'Pizza de palmito com champignon', 42.00, 3),

('massa, queijo, bacon, rúcula', 'Bacon e Rúcula', 34.99, 'Pizza de bacon com rúcula', 42.00, 1),

('massa, queijo, chocolate, morango', 'Chocolate e Morango', 36.50, 'Pizza de chocolate com morango', 42.00, 2),

('massa, queijo, banana, canela', 'Banana com Canela', 33.99, 'Pizza de banana com canela', 44.00, 3),

('massa, queijo, presunto, tomate', 'Presunto e Tomate', 35.50, 'Pizza de presunto com tomate', 44.00, 1),

('massa, queijo, pepperoni, cebola roxa', 'Peperoni e Cebola Roxa', 37.99, 'Pizza de peperoni com cebola roxa', 44.00, 2),

('massa, queijo, alho poró, bacon', 'Alho Poró com Bacon', 36.50, 'Pizza de alho poró com bacon', 46.00, 3),

('massa, queijo, camarão, palmito', 'Camarão e Palmito', 39.50, 'Pizza de camarão com palmito', 46.00, 1),

('massa, queijo, carne seca, catupiry', 'Carne Seca com Catupiry', 38.99, 'Pizza de carne seca com catupiry', 46.00, 2);

create TABLE pizzaiolo(

id			integer PRIMARY KEY autoincrement,
nome		varchar,
salario		double,
faz			varchar,

FOREIGN KEY (faz) REFERENCES pizza(sabor)
);

INSERT INTO pizzaiolo(nome, salario, faz)VALUES

('João Silva', 2500.00, 'Calabresa com Cebola'), ('Maria Santos', 2800.00, 'Frango com Catupiry'), ('Pedro Oliveira', 3000.00, 'Presunto e Milho'), ('Ana Pereira', 2700.00, 'Bacon e Cebola'), ('Lucas Costa', 3200.00, 'Marguerita'), ('Juliana Almeida', 2900.00, 'Peperoni'), ('Marcos Santos', 3100.00, 'Quatro Queijos'), ('Carla Souza', 2600.00, 'Camarão com Catupiry'), ('André Oliveira', 2900.00, 'Atum e Cebola'), ('Mariana Lima', 3100.00, 'Calabresa e Palmito'), ('Rodrigo Ferreira', 2800.00, 'Frango com Cheddar'), ('Fernanda Costa', 3000.00, 'Vegetariana'), ('Rafael Santos', 2700.00, 'Carne Seca com Catupiry'), ('Amanda Oliveira', 3200.00, 'Portuguesa'), ('Patricia Lima', 2500.00, 'Frango com Requeijão'), ('Leonardo Silva', 2900.00, 'Lombo com Abacaxi'), ('Luana Sousa', 3100.00, 'Mussarela de Búfala e Tomate Seco'), ('Bruno Oliveira', 2700.00, 'Palmito com Champignon'), ('Camila Costa', 3200.00, 'Bacon e Rúcula'), ('Gustavo Santos', 2800.00, 'Chocolate e Morango'), ('Vanessa Lima', 3000.00, 'Banana com Canela'), ('Renato Oliveira', 2700.00, 'Presunto e Tomate'), ('Aline Ferreira', 3100.00, 'Peperoni e Cebola Roxa'), ('Felipe Sousa', 2900.00, 'Alho Poró com Bacon'), ('Tatiane Santos', 3000.00, 'Camarão e Palmito'), ('Thiago Oliveira', 2800.00, 'Milho com Bacon'), ('Isabela Lima', 3200.00, 'Brócolis com Requeijão'), ('Vinicius Costa', 2700.00, 'Presunto Parma e Rúcula'), ('Caroline Oliveira', 3100.00, 'Tomate e Manjericão');

select nome from pizzaiolos where faz = "sabor de pizza";

(com o comando acima você seleciona o nome do pizzaiolo que faz determiando sabor de pizza)
