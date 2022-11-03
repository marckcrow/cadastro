-- Scrip do banco de dados SQL

use dbcadprod;


--criação de tabelas
CREATE TABLE marcas
(
id INT PRIMARY KEY IDENTITY(1,1),
descricao VARCHAR (50),
tipo VARCHAR(2)
);

CREATE TABLE produto
(
id INT PRIMARY KEY IDENTITY(1,1),
marcas_id INT,
nome VARCHAR(100),
preco MONEY,
fotos varchar(50)
);

--criação de relacionamentos
ALTER TABLE produto
ADD CONSTRAINT fk_marcas_id
FOREIGN KEY (marcas_id)
REFERENCES marcas(id);

--inserção de dados
INSERT marcas
(descricao,tipo)
VALUES
('Broto legal','A'),
('Prato fino','A'),
('Carmil','B'),
('Scala','B');

INSERT produto
(marcas_id,nome,preco,fotos)
VALUES
(1,'Feijao',3,'fbl.png'),
(2,'Arroz Sinha',5,'fbl.png'),
(3,'Arroz Dede',5,'fbl.png'),
(4,'Parafuso',3,'fbl.png');



select * from marcas;
select * from produto;
