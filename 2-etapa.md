## desenvolvendo o dados ao banco

### cadastrando os cursos
```sql
    insert into cursos (nome, carga_horaria) values ('Front-End', '40h'), ('Back-End', '80h'), ('UX/UI Design', '30h'), ('Figma', '10h'), ('Rede de Computadores', '100h');
```

### cadastrando os professores
```sql
    insert into professores (nome, area, id_curso) values ('Jon Oliva', 'Infra', 25), ('Lemmy Kilmister', 'design', 24), ('Neil Peart', 'design', 23), ('ozzy Osborne', 'desenvolvimento', 22), ('David Gilmour', 'desenvolvimento', 21);
```
### cadastrando os alunos

```sql
    INSERT INTO alunos (nome, data_nascimento, primeira_nota, segunda_nota, id_curso) VALUES 
    ('João Silva', '1995-08-15', 8.5, 7.2, 21), 
    ('Maria Santos', '1992-04-25', 9.0, 4.4, 21), 
    ('Pedro Almeida', '1998-11-03', 6.7, 7.5, 25), 
    ('Ana Costa', '1990-07-10', 8.4, 5.5, 25), 
    ('Luís Pereira', '1994-02-18', 1.0, 7.5, 23),
    ('Miguel Rodrigues', '1993-09-22', 7.8, 2.5, 23),
    ('Guilherme Ribeiro', '1991-12-12', 6.5, 6.9, 24),
    ('Beatriz Fernandes', '1996-03-08', 6.5, 9.0, 24),
    ('Carolina Sousa', '1999-01-30', 9.2, 9.0, 22),
    ('Sofia Oliveira', '1997-06-29', 10.0, 6.0, 22);

```
