## fazendo Consultas

### 1 Consulta de alunos que nasceram antes de 2009.

```sql
    select nome, data_nascimento from alunos where data_nascimento < '2009-01-01';
```
 ![resultado da pesquisa](imagens-consultas/1-consulta.png)

##

### 1.2 Consulta de alunos que nasceram antes de 1995.

```sql
    select nome, data_nascimento from alunos where data_nascimento < '1995-01-01';
```
 ![resultado da pesquisa](imagens-consultas/1-2consulta.png)

##

### 2 Consulta que calcula a media das notas de cada aluno.

```sql
    select nome, round((primeira_nota + segunda_nota) / 2, 2) as media from alunos;
```
![resultado da pesquisa](imagens-consultas/2-consulta.png)

##

### 3 Consulta para calcular o limite de falta de cada curso, tolerância de falta de 25%.

```sql
    SELECT titulo, (carga_horaria * 0.25) AS "Limite de Faltas" FROM cursos;
```
![resultado da pesquisa](imagens-consultas/3-consulta.png)

##

### 4 consulta para mostrar somente o nome dos professores da área de "desenvolvimento".

```sql
    SELECT nome, area_atuacao FROM professores WHERE area_atuacao LIKE '%desenvolvimento%';
```
![resultado da pesquisa](imagens-consultas/4-consulta.png)

##

### 5 consulta para mostrar a quantidade de professores por cada matéria

```sql
    SELECT area_atuacao AS "Matéria", COUNT(*) AS "Professores por matéria" FROM professores GROUP BY area_atuacao;
```
![resultado da pesquisa](imagens-consultas/5-consulta.png)

##

### 6 consulta para mostrar nome dos alunos, carga horaria e o cursos que fazem

```sql
    SELECT alunos.nome AS "Nome do aluno", cursos.titulo AS "Curso", cursos.carga_horaria AS "Carga Horaria"
    FROM alunos INNER JOIN cursos ON alunos.id_curso = cursos.id;
```
![resultado da pesquisa](imagens-consultas/6-consulta.png)

##

### 7 consulta para mostrar os nomes dos professores e o curso que eles lecionam

```sql
    SELECT professores.nome AS "Professor", cursos.titulo AS "Curso" FROM professores INNER JOIN cursos ON professores.id_curso = cursos.id ORDER BY professores.nome;
```
![resultado da pesquisa](imagens-consultas/7-consulta.png)

##

### 8 consulta para mostrar os nomes dos alunos, nomes dos cursos e o professor de cada curso

```sql
     SELECT alunos.nome AS "alunos", cursos.titulo AS "Curso", professores.nome AS "Professores" FROM alunos INNER JOIN cursos ON alunos.id_curso = cursos.id inner join professores ON cursos.id_professor = professores.id;
```
![resultado da pesquisa](imagens-consultas/8-consulta.png)

##

### 9 consulta para mostrar a quantidade de alunos de cada curso 

```sql
    SELECT cursos.titulo AS "Cursos", COUNT(alunos.id) AS " QTD alunos"
    FROM cursos
    INNER JOIN alunos ON cursos.id = alunos.id_curso
    GROUP BY cursos.titulo
    ORDER BY "QTD alunos" DESC;
```
![resultado da pesquisa](imagens-consultas/9-consulta.png)

##

### 10  consulta que mostra o nome do aluno, notas, media em dois cursos específicos e listado por ordem alfabética dos alunos

```sql
SELECT alunos.nome, cursos.titulo AS "Curso", alunos.primeira_nota AS "Primeira nota", alunos.segunda_nota AS "Segunda nota", 
ROUND((alunos.primeira_nota + alunos.segunda_nota) / 2, 2) AS media
FROM alunos
INNER JOIN cursos ON alunos.id_curso = cursos.id
WHERE alunos.id_curso = 21 OR alunos.id_curso = 22
ORDER BY alunos.nome;

```
![resultado da pesquisa](imagens-consultas/10-consulta.png)

##

### 11 alterando o nome do curso de figma para adobe xd

```sql
    UPDATE cursos SET titulo = "Adobe XD" WHERE id = 24;
    UPDATE cursos SET carga_horaria = 15 WHERE id = 24;
```
![resultado da pesquisa](imagens-consultas/11-consulta.png)

##

### 12 deletando um aluno do curso de ui/ux e um aluno do curso de redes

```sql
    DELETE FROM alunos WHERE id = 4 OR id = 5;
```
![resultado da pesquisa](imagens-consultas/12-consulta.png)

##

### 13 mostrando o nome dos alunos e cursos que fazem em ordem alfabética

```sql
SELECT alunos.nome, cursos.titulo AS "Curso" FROM alunos
INNER JOIN cursos ON alunos.id_curso = cursos.id
ORDER BY alunos.nome;
```
![resultado da pesquisa](imagens-consultas/13-consulta.png)

##

# outros desafios


## 1 Criar uma consulta que calcule a idade do aluno
```sql
    SELECT alunos.nome, TIMESTAMPDIFF(YEAR, alunos.data_nascimento, CURDATE()) AS "idade" FROM alunos;

```
![resultado da pesquisa](imagens-consultas/14-consulta.png)


