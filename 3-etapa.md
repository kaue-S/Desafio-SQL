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

