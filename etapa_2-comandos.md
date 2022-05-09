## inserir dados na tabela cursos

```sql
INSERT INTO cursos(Titulo, CargaH) VALUES(
    'Back-End',
    80
    # basicamente o mesmo comando para 5 cursos, apenas muda o valor da cargaH e a string/titulo diferente
);
```

## inserir dados na tabela professores

```sql
## design, desenvolvimento e infra são as 3 areas/atuações disponiveis
## id 1 = front-end, id 2 = back-end, id 3 = UX/UI Design, id 4 = Figma, id 5 = Redes de computadores
INSERT INTO professores(nome, atuacao, curso_id) VALUES(
    'jon oliva',
    'infra',
    5
    
);
INSERT INTO professores(nome, atuacao, curso_id) VALUES(
    'Naruto',
    'design',
    4
    
);
INSERT INTO professores(nome, atuacao, curso_id) VALUES(
    'um cara ai',
    'design',
    3
    
);
INSERT INTO professores(nome, atuacao, curso_id) VALUES(
    'Blaidd',
    'desenvolvimento',
    2
    
);
INSERT INTO professores(nome, atuacao, curso_id) VALUES(
    'enunciado atualizado',
    'desenvolvimento',
    1
    
);
```

## inserir dados na tabela Alunos

```sql
## design, desenvolvimento e infra são as 3 areas/atuações disponiveis
## id 1 = front-end, id 2 = back-end, id 3 = UX/UI Design, id 4 = Figma, id 5 = Redes de computadores
INSERT INTO alunos(Nome, Nascimento, Nota1, Nota2, curso_id) VALUES(
    'joão ninguem',
    '1997-06-20',
    8,
    7,
    2
    
);
# 
INSERT INTO alunos(Nome, Nascimento, Nota1, Nota2, curso_id) VALUES(
    'Cade o codigo',
    '2000-10-15',
    3,
    4,
    2

),
(
    'maluco beleza',
    '2004-08-19',
    5,
    5,
    3
),
(
  'Filho do joão ninguem',
    '2006-06-20',
    8,
    8,
    3
),
(
  'mucalol',
    '1995-05-20',
    0,
    0,
    5
),
(
    'Diane',
    '1991-03-03',
    10,
    10,
    5
),
(
  'mario',
    '1990-05-05',
    7,
    7,
    2
),
(
  'Tomás turbano',
    '1993-02-28',
    3,
    3,
    4
),
(
  'chaves',
    '1970-04-24',
    1,
    2,
    4
),
(
  'O tal do mula',
    '1985-09-09',
    2,
    10,
    5
);
```