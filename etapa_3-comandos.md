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
## 5) consulta QTD professores da area desenvolvimento •
```sql
SELECT COUNT(curso_id) WHERE curso_id = 1 OR curso_id = 2; AS "quantidade de professores"
FROM professores;

SELECT COUNT(curso_id) AS "quantidade de professores na area de dev"
FROM professores WHERE curso_id = 1 OR curso_id = 2;
```

## 6) consulta alunos nome, titulo e cargaH
```sql

```