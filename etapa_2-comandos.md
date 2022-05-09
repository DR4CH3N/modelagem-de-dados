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
INSERT INTO professores(nome, atuacao, professor_id) VALUES(
    'jon oliva',
    'infra'
    
    
);
```