## fazendo Consultas

### 1 Consulta de alunos que nasceram antes de 2009

```sql
    select nome, data_nascimento from alunos where data_nascimento < '2009-01-01';
```
 ![resultado da pesquisa](imagens-consultas/1-consulta.png)

##

### 1 Consulta de alunos que nasceram antes de 1995

```sql
    select nome, data_nascimento from alunos where data_nascimento < '1995-01-01';
```
 ![resultado da pesquisa](imagens-consultas/2-1consulta.png)

##

### 2 Consulta que calcula a media das notas de cada aluno

```sql
    select nome from alunos where (primeira_nota + segunda_nota)/2;
```