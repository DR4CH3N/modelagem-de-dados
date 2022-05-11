•  concluido
○ não concluido

## 1) consulta da idade •
```sql
SELECT Nascimento FROM alunos
WHERE Nascimento < '2009-01-01';
```

## 2) consulta calcula media •
```sql
SELECT Nome, Nota1, Nota2, ROUND((Nota1 + Nota2)/2, 2) AS "media das notas"
FROM alunos
```
## 3) consulta calcula limite faltas cargaH ○
```sql

```

## 4) consulta nome professores desenvolvimento •
```sql
SELECT nome, atuacao FROM professores
-- dos fabricantes apple ou microsoft
WHERE curso_id = 1 OR curso_id = 2;
```
## 5) consulta QTD professores da area desenvolvimento ○
```sql
SELECT COUNT(curso_id) AS "quantidade de professores na area de dev"
FROM professores WHERE curso_id = 1 OR curso_id = 2;

SELECT COUNT(curso_id) AS "quantidade de professores por area de atuacao"
FROM professores WHERE atuacao in (1, 2, 3, 4, 5)
```

## 6) consulta alunos nome, titulo e cargaH ○
```sql
    SELECT Nome, Titulo, CargaH FROM alunos, cursos

    SELECT COUNT(DISTINCT) Nome, Titulo, CargaH FROM alunos, cursos
```
## 7) ○
```sql

```

## 8) ○
```sql

```

## 9) ○
```sql

```

## 10) ○
```sql

```

## 11) consulta altera nome do curso e CargaH •
```sql
UPDATE cursos SET titulo = 'AdobeXD'
WHERE id = 4;

UPDATE cursos SET CargaH = 15
WHERE id = 4;
```

## 12) consulta excluir aluno Redes de computadores e aluno UI/UX •
```sql
    # excluir alunos do curso redes de computadores
    DELETE FROM alunos WHERE curso_id = 5 AND id = 15;

    # excluir alunos do curso UI/UX design
    DELETE FROM alunos WHERE curso_id = 3 AND id = 8;
```

## 13) ○
```sql

```