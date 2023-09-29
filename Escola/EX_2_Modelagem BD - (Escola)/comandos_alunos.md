## Modelagem física

### Criar banco de dados
```sql

CREATE DATABASE tecdev_escola_isabela CHARACTER SET utf8mb4;

```
<!-- ____________________________________________________________________ -->
### Criar tabela cursos
```sql

CREATE TABLE cursos(
    id SMALLINT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    titulo VARCHAR(30) NOT NULL,
    carga_horaria SMALLINT NOT NULL,
    professor_id SMALLINT NOT NULL
)

```
<!-- ____________________________________________________________________ -->
### Criar tabela professores
```sql

CREATE TABLE professores(
    id SMALLINT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(50) NOT NULL,
    area_de_atuacao ENUM("infra","design","desenvolvimento") NOT NULL,
    curso_id SMALLINT NOT NULL
)

```
<!-- ____________________________________________________________________ -->
### Criar tabela alunos
```sql

CREATE TABLE alunos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(30) NOT NULL,
    data_de_nascimento DATE NOT NULL,
    primeira_nota DECIMAL (4,2) NOT NULL,
    segunda_nota DECIMAL (4,2) NOT NULL,
    curso_id SMALLINT NOT NULL
)

```
<!-- ____________________________________________________________________ -->
### Criação da chave estrangeira (relacionamento entre as tabelas)

```sql
-- Criação das chaves estrangeiras (Exercício)
ALTER TABLE cursos
    ADD CONSTRAINT fk_cursos_professores
    FOREIGN KEY(professor_id) REFERENCES professores(id);

ALTER TABLE professores
    ADD CONSTRAINT fk_professores_cursos
    FOREIGN KEY(curso_id) REFERENCES cursos(id);

ALTER TABLE alunos
    ADD CONSTRAINT fk_alunos_cursos
    FOREIGN KEY(curso_id) REFERENCES cursos(id);

<!-- ____________________________________________________________________ -->
-- Inclusão dos cursos (5 cursos:) Etapa 2
INSERT INTO cursos (titulo, carga_horaria) VALUES(
    'Front-End',
    40
    ),
(
    'Back-End',
    80
    ),
(
    'UX/UI Design',
    30
),
(
    'Figma',
    10
),
(
    'Redes de Computadores',
    100
);

```
<!-- ____________________________________________________________________ -->
### cadastro dos (5 professores) Etapa 2

```sql
INSERT INTO professores (nome, area_de_atuacao, curso_id) VALUES(
    'Jon Oliva',
    'infra',
    5
    ),
(
    'Lemmy Kilmister',
    'design',
    4
    ),
(
    'Neil Peart',
    'design',
    3
    ),
(
    'Ozzy Osbourne',
    'desenvolvimento',
    2
    ),
(
    'David Gilmour',
    'desenvolvimento',
    1
    );
-- Atualização de Id´s

UPDATE cursos SET professor_id = 1 WHERE id = 5;
UPDATE cursos SET professor_id = 2 WHERE id = 4;
UPDATE cursos SET professor_id = 3 WHERE id = 3;
UPDATE cursos SET professor_id = 4 WHERE id = 2;
UPDATE cursos SET professor_id = 5 WHERE id = 1;

-- Cadastro dos alunos

INSERT INTO alunos (nome, data_de_nascimento,primeira_nota, segunda_nota, curso_id) VALUES(
    'Ignacio Neto',
    '1982-02-26',
    8,
    10,
    3
    ),
(
    'Maria Yussef',
    '1985-02-26',
    9,
    10,
    2
    ),
(
    'Robert Sheer',
    '1995-02-03',
    9,
    7,
    5
),
(
    'Rosana Uter',
    '1970-06-09',
    10,
    10,
    1
),
(
    'Vater Gustavo',
    '1955-11-19',
    9,
    9,
    4
),
(
    'Valéria Linda',
    '2005-09-26',
    4,
    7,
    2
),
(
    'Mário Calore',
    '1995-02-03',
    10,
    7,
    3
),
(
    'Ariana Grande',
    '1995-02-03',
    8,
    3,
    4
),
(
    'Michael Robert',
    '1995-02-03',
    9,
    9,
    1
),
(
    'Viviane Lima',
    '2015-01-01',
    10,
    9,
    3
);


```
<!-- ____________________________________________________________________ -->
### Consultas (Etapa 3)

### 1) Faça uma consulta que mostre os alunos que nasceram antes do ano 2009
```sql

-- 5ª Digitação (SQL para criar a consulta acima)

```
![Relatório 1](resultados/relatorio1.jpg)

<!-- _________________________ -->
### 2) Faça uma consulta que calcule a média das notas de cada aluno e as mostre com duas casas decimais.
```sql

-- 6ª Digitação (SQL para criar a consulta acima)


```
![Relatório 2](resultados/relatorio2.jpg)

<!-- _________________________ -->
### 3) Faça uma consulta que calcule o limite de faltas de cada curso de acordo com a carga horária. Considere o limite como 25% da carga horária. Classifique em ordem crescente pelo título do curso.
```sql

-- 7ª Digitação (SQL para criar a consulta acima)

```
![Relatório 3](resultados/relatorio3.jpg)

<!-- _________________________ -->

### 4) Faça uma consulta que mostre os nomes somente dos professores da área de desenvolvimento.
```sql

-- 8ª Digitação (SQL para criar a consulta acima)

```
![Relatório 4](resultados/relatorio4.jpg)
<!-- _________________________ -->

### 5) Faça uma consulta que mostre a quantidade de professores por área de desenvolvimento.
```sql

-- 9ª Digitação (SQL para criar a consulta acima)

```
![Relatório 5](resultados/relatorio5.jpg)

<!-- _________________________ -->

### 6) Faça uma consulta que mostre o nome dos alunos, o título e a carga horária dos cursos que fazem.
```sql

-- 10ª Digitação (SQL para criar a consulta acima)

```
![Relatório 6](resultados/relatorio6.jpg)

<!-- _________________________ -->
### 7) Faça uma consulta que mostre o nome dos professores e o título do curso que lecionam. Classifique pelo nome do professor.
```sql

-- 11ª Digitação (SQL para criar a consulta acima)

```
![Relatório 7](resultados/relatorio7.jpg)

<!-- _________________________ -->
### 8) Faça uma consulta que mostre o nome dos alunos, o título dos cursos que fazem, e o professor de cada curso.
```sql

-- 12ª Digitação (SQL para criar a consulta acima)

```
![Relatório 8](resultados/relatorio8.jpg)

<!-- _________________________ -->
### 9) Faça uma consulta que mostre a quantidade de alunos que cada curso possui. Classifique os resultados em ordem descrecente de acordo com a quantidade de alunos.
```sql

-- 13ª Digitação (SQL para criar a consulta acima)

```
![Relatório 9](resultados/relatorio9.jpg)

<!-- _________________________ -->
### 10) Faça uma consulta que mostre o nome dos alunos, suas notas, médias, e o título dos cursos que fazem. Devem ser considerados somente os alunos de Front-End e Back-End. Mostre classificados pelo nome do aluno.
```sql

-- 14ª Digitação (SQL para criar a consulta acima)

```
![Relatório 10](resultados/relatorio10.jpg)

<!-- _________________________ -->
### 11) Faça uma consulta que altere o nome do curso de Figma para Adobe XD e sua carga horária de 10 para 15.
```sql

-- 15ª Digitação (SQL para criar a consulta acima)

```
![Relatório 11](resultados/relatorio11.jpg)

<!-- _________________________ -->
### 12) Faça uma consulta que exclua um aluno do curso de Redes de Computadores e um aluno do curso de UX/UI.
```sql

-- 16ª Digitação (SQL para criar a consulta acima)

```
![Relatório 12](resultados/relatorio12.jpg)
<!-- _________________________ -->
### 13) Faça uma consulta que mostre a lista de alunos atualizada e o título dos cursos que fazem, classificados pelo nome do aluno.
```sql

-- 17ª Digitação (SQL para criar a consulta acima)

```
![Relatório 13](resultados/relatorio13.jpg)
<!-- _________________________ -->
## DESAFIOS

### 1) Criar uma consulta que calcule a idade do aluno
```sql

-- 18ª Digitação (SQL para criar a consulta acima)

```
![Desafio 1](resultados/desafio1.jpg)

<!-- _________________________ -->
### 2) Criar uma consulta que calcule a média das notas de cada aluno e mostre somente os alunos que tiveram a média **maior ou igual a 7**.
```sql

-- 19ª Digitação (SQL para criar a consulta acima)

```
![Desafio 2](resultados/desafio2.jpg)

<!-- _________________________ -->
### 3) Criar uma consulta que calcule a média das notas de cada aluno e mostre somente os alunos que tiveram a média **menor que 7**.
```sql

-- 20ª Digitação (SQL para criar a consulta acima)

```
![Desafio 3](resultados/desafio3.jpg)

<!-- _________________________ -->

### 4) Criar uma consulta que mostre a quantidade de alunos com média **maior ou igual a 7**.
```sql

-- 21ª Digitação (SQL para criar a consulta acima)

```
![Desafio 4](resultados/desafio4.jpg)
