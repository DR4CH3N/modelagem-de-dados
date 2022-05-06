# comandos CRUD são comandos para manipulaçao de dados

## comandos SQL para crud - referencia

### resumo
- C -> create (inserir dados)
- R -> read (ler dados)
- U -> update (atualizar dados)
- D -> delete (deletar dados)

## insert
``` sql
INSERT INTO fabricantes (nome) VALUES('Asus');
INSERT INTO fabricantes (nome) VALUES('Dell');
INSERT INTO fabricantes (nome)
VALUES ('APPLE'), ('LG'), ('samsung'), ('brastemp')
```

## produtos

```sql
INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id) VALUES(
    'Tablet Android',
    'Tablet com a versão 12 do sistema operacional da google, 
    possui tela de 10 polegadas e armazenamento de 64GB.', 
    4999,
    3, 
    5 # Samsung
);

INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id) VALUES
(
    'Geladeira',
    'Refrigerador Frost-Free com acesso a internet das coisas e blah blah blah',
    1500,
    10,
    6 # brastemp
),
(
    'Iphone 13 Pro Max',
    'Alta durabilidade, processador bionic 14, 
    memoria 128GB de armazenamento, 6GB de RAM e custa um rim',
    6999.99,
    3,
    3 -- Apple
),
(
    'ipad mini',
    'tablet Apple com tela retina display de 4K, memoria interna de 64GB,
    acesso ao iCloud.',
    5000,
    8,
    3 
);

INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id) VALUES 
(
    'Xbox Series X',
    'Console de ultima geração com acesso aos melhores jogos, etc etc',
    2500,
    5,
    8 # microsoft
),
(
    'Ultrabook positivo 100% legitimo',
    'Equipamento com processador AMD Ryzen5, 12GB de memoria RAM, placa de video Nvidia RTX 3060',
    4500.68,
    3,
    7
); 
```

## SELECT

### Ler dados da tabela produtos
```sql
SELECT * FROM produtos;
SELECT nome, preco FROM produtos;
SELECT nome FROM produtos WHERE preco < 5000;
SELECT nome, descricao FROM produtos WHERE fabricante_id = 3; # Apple
```

### operadores logicos: E, OU, NÃO
```sql
SELECT * FROM produtos
WHERE preco >= 5000 AND preco < 8000;

SELECT nome, preco FROM produtos
-- dos fabricantes apple ou microsoft
WHERE fabricante_id = 3 OR fabricante_id = 8;

SELECT nome, preco, quantidade FROM produtos WHERE NOT fabricante_id = 3;
-- versão 1 usando NOT

SELECT nome, preco, quantidade FROM produtos
WHERE fabricante_id != 3; -- versão 2 usando operador !=

WHERE fabricante_id in (3,8); -- usando função IN (lista)
```

### filtros
```sql
SELECT nome, preco, FROM produtos ORDER BY nome; -- ORDEM ASCENDENTE/crescente (padrão)
SELECT nome, preco FROM produtos ORDER BY nome DESC -- ORDEM DECRESCENTE 
SELECT nome, descricao FROM produtos
WHERE descricao LIKE '%processador%'; -- LIKE (COMO)

-- OPERADOR CORINGA (significa qualquer texto)
```

### OPERAÇÕES E FUNÇÕES DE AGREGAÇÃO

```sql
SELECT SUM(preco) FROM produtos; -- SOMA
SELECT SUM(preco) AS TOTAL FROM produtos; -- ALIAS (APELIDO)

SELECT SUM(quantidade) AS "quantidade em estoque"
FROM PRODUTOS WHERE fabricante_id = 3; -- apple;

-- AVG (media) MEDIA
SELECT AVG(preco) AS "Média dos preços" --  apelido
FROM produtos;

-- ROUND (arredondar/arredondamento)
SELECT ROUND(AVG(preco), 2) AS "média dos preços"
FROM produtos;

--  COUNT (contagem)
SELECT COUNT(id) AS "quantidade de fabricantes"
FROM produtos;

-- DISTINCT é um comando para evitar a duplicidade na contagem em campos quenão são chave primaria
SELECT COUNT(DISTINCT fabricante_id) AS "quantidade de fabricantes"
FROM produtos;

SELECT nome, preco, quantidade, (preco * quantidade) AS TOTAL 
FROM produtos;

```

### AGRUPAMENTOS

```sql
SELECT fabricante_id, sum(preco) AS TOTAL FROM produtos
GROUP BY fabricante_id;

-- GROUP BY permite segmentar resultados da consulta. 
-- neste caso, somamos todos os preços e segmentamos/agrupamos
-- por cada fabricante.
```

## UPDATE (SEMPRE COM WHERE)

### atualizar dados em uma tabela
```sql
UPDATE fabricantes SET nome = 'Microsoft Brasil'
WHERE id = 8;

-- mudar o preço do ultrabook da positivo para 5.2K
UPDATE produtos SET preco = 5200
WHERE id = 7

-- mudar a quantidade dos produtos da asus e APPLE para 15.
UPDATE produtos SET quantidade = 15 
WHERE fabricante_id = 1 OR fabricante_id = 3;
``` 

## DELETE (SEMPRE COM WHERE)

### exlcuir dados de uma tabela

```sql
DELETE FROM fabricantes WHERE id = 4; -- LG

DELETE FROM produtos
WHERE preco <= 2000 AND preco > 500;
```

### constultas em duas ou mais tabelas (junção)
```sql
-- SELECT nomeDaTabela.nomeDaColuna
SELECT produtos.nome, fabricantes.nome

-- INNER JOIN é o comando que permite JUNTAR tabelas
FROM produtos INNER JOIN fabricantes

-- ON comando para indicar o criteirio de junção
ON produtos.fabricante_id = fabricantes.id;

SELECT 
produtos.nome AS "Produto" 
fabricantes.nome AS "" Fabricante

FROM produtos INNER JOIN fabricantes
ON produtos.fabricante_id = fabricantes.id
ORDER BY produtos.nome;

-- fabricatnte, soma dos preços e quantidade de produtos

SELECT fabricantes.nome AS fabricante,
SUM(produtos.preco) AS Total, 
COUNT(produtos.fabricante_id) AS "qtd de produtos"
FROM produtos INNER JOIN fabricantes
ON produtos.fabricante_id = fabricantes.id
GROUP BY fabricante
ORDER BY Total;

-- Trazer a quantidade de produtos de cada fabricante

SELECT fabricantes.nome AS fabricante,
COUNT(produtos.fabricante_id) AS "qtd de produtos"
FROM produtos INNER JOIN fabricantes
ON produtos.fabricante_id = fabricantes.id
GROUP BY fabricante


```