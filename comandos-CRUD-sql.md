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
VALUES ('APPLE',) ('LG'), ('samsung'), ('brastemp')
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

