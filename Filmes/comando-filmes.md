# Comandos SQL
 <!--_________________________________  -->
## Modelagem física 

### Criar banco de dados 

```sql
CREATE DATABASE filmes CHARACTER SET utf8mb4;
```
<!-- __________________________________ -->
### Criar a tabela de filmes 

```sql
CREATE TABLE filmes(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    título VARCHAR(45) NOT NULL,
    lancamento YEAR(4),
    genero_id INT
)
```

<!-- __________________________________ -->
### Criar a tabela de generos 

```sql
CREATE TABLE generos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    genero VARCHAR(45) NOT NULL
)
```
<!-- __________________________________ -->

### Criação da chave estrangeira (relacionamento entre tabelas)

```sql
ALTER TABLE filmes 
    # CONTRAINT é uma restrição definida no relacionamento
    ADD CONSTRAINT  fk_filmes_generos

    # A chave estrangeira deve fazer referência a chave primária
    FOREIGN KEY (genero_id) REFERENCES generos(id)
```