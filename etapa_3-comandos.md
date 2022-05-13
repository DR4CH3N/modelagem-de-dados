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
## 3) consulta calcula limite faltas cargaH •
```sql
SELECT Titulo, CargaH, (CargaH * 0.25) AS "Limite de faltas (por hora)"
FROM cursos ORDER BY Titulo
```

## 4) consulta nome professores desenvolvimento •
```sql
SELECT nome, atuacao FROM professores
-- dos fabricantes apple ou microsoft
WHERE curso_id = 1 OR curso_id = 2;
```
## 5) consulta QTD professores da area desenvolvimento •
```sql
SELECT atuacao, COUNT(atuacao) 
FROM professores GROUP BY atuacao


```

## 6) consulta alunos nome, titulo e cargaH •
```sql
   SELECT alunos.Nome, cursos.Titulo, cursos.CargaH 
   FROM alunos INNER JOIN cursos
   ON alunos.curso_id = cursos.id ORDER BY alunos.nome;

```
## 7) consulta mostra nome professores, titulo curso, classificar pelo nome do professor •
```sql
    SELECT professores.Nome, cursos.Titulo, cursos.CargaH 
    FROM professores INNER JOIN cursos 
    ON professores.curso_id = cursos.id 
    ORDER BY professores.nome
```

## 8) consulta mostra nome alunos, titulo curso e professor de cada curso •
```sql
    SELECT alunos.nome, cursos.Titulo, professores.nome 
    FROM alunos
    INNER JOIN cursos
    ON alunos.curso.id = cursos.id 
    INNER JOIN professores
    ON professores.curso_id = cursos.id;

        SELECT alunos.nome AS "Alunos", cursos.titulo AS "Cursos", professores.nome AS "Professores" FROM alunos INNER JOIN cursos ON alunos.curso_id = cursos.id INNER JOIN professores ON cursos.professor_id = professores.id;
```

## 9) constulta mostra QTD alunos de cada curso, classificar resultados em order decrescente •
```sql
    SELECT (cursos.Titulo) AS "cursos", COUNT(alunos.curso_id) AS "QTD de alunos por curso"
    FROM alunos 
    INNER JOIN cursos
    ON alunos.curso_id = cursos.id
    GROUP BY curso_id 
    ORDER BY curso_id DESC
```

## 10) consulta mostra nome alunos, notas, medias e titulo do curso que fazem, somente alunos front e back end. mostrar classificados pelo nome do aluno •
```sql
SELECT alunos.nome, alunos.Nota1, alunos.Nota2, cursos.Titulo, cursos.Titulo

    SELECT alunos.nome, alunos.nota1, alunos.nota2, ROUND(AVG(alunos.nota1 + alunos.nota2)/2, 2) AS "Médias", cursos.titulo FROM alunos INNER JOIN cursos ON alunos.curso_id = cursos.id WHERE cursos.titulo = "Front-End" OR cursos.titulo = "Back-End" GROUP BY alunos.nome ORDER BY alunos.nome;
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

## 13) consulta mostra lista alunos, titulo curso classificados por nome de aluno •
```sql
      SELECT alunos.Nome AS "Aluno", cursos.Titulo AS "curso",
    COUNT(alunos.curso_id) AS "qtd de alunos no curso"
    FROM alunos INNER JOIN cursos
    ON alunos.curso_id = cursos.id
    GROUP BY aluno
    ORDER BY alunos.Nome ASC


    SELECT alunos.nome, cursos.titulo FROM alunos INNER JOIN cursos ON alunos.curso_id = cursos.id ORDER BY alunos.nome;
```



## DESAFIOS


## 1)
```sql
SELECT nome, ROUND(DATEDIFF(CURDATE(), nascimento)/365) AS "Idade" FROM alunos;
```

## 2)
```sql
SELECT nome, ROUND(AVG(nota1 + nota2)/2, 2) AS "Média" FROM alunos GROUP BY nome HAVING Média > 7;
```


## 3) 
```sql
SELECT nome, ROUND(AVG(nota1 + nota2)/2, 2) AS "Média" FROM alunos GROUP BY nome HAVING Média < 7;
```

## 4)
```sql

```