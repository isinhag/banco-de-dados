<!-- _________________________________ -->
# Comando SQL - Para CRUD

## Resumo 
C -> Create (Insere dados)
R -> Read (Ler dados)
U -> Update (Atualizar dados)
D -> Delete (Deletar dados)

## Insert 
## Generos 
```sql
INSERT INTO generos (genero) VALUES ('Comédia');
INSERT INTO generos (genero) VALUES ('Ação');
INSERT INTO generos (genero)
VALUES ('Suspense'),('Terror'), ('Aventura'), ('Ficção científica');
```
<!-- _________________________________ -->
## Insert
## Filmes
```sql
INSERT INTO filmes (título, lancamento, genero_id) VALUES (
'Albergue', 
'2005',
4
);
INSERT INTO filmes (título, lancamento, genero_id) VALUES (
'Top Gun Maverick', 
'2022',
2
);
INSERT INTO filmes (título, lancamento, genero_id) VALUES (
'Se beber não se case', 
'2009',
1
);
```
