```sql
# criação da database

CREATE DATABASE exercicioSQL CHARACTER SET utf8mb4;

# criar a tabela filmes

CREATE TABLE filmes (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    titulo TINYTEXT NOT NULL,
    ano DATE NOT NULL,
    genero_id INT NOT NULL
);

# criar a tabela generos

CREATE TABLE generos (
    id INT PRIMARY KEY NOT NULL AUTO_INCREMENT,
    generos VARCHAR(20) NOT NULL
);

ALTER TABLE filmes
    # CONSTRAINT é uma restrição definida no relacionamento;
    ADD CONSTRAINT fk_generos_filmes
    # filmes em ultima ordem vai ser onde o constraint vai ser criado

    # a chave estrangeira deve fazer referencia a chave primaria
    FOREIGN KEY(genero_id) REFERENCES generos(id);

    # OBS: voce tem que criar o campo primeiro do relacionamento antes de fazer o relacionamento em si!

INSERT INTO generos (generos)
VALUES ('Terror'), ('Ação'), ('Suspense'), ('Drama')


```
