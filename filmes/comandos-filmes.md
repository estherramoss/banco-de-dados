# comandos SQL - Referência 
<!-- ______________________________________________ -->
## Modelagem física 
### Criar banco de dados
```sql
CREATE DATABASE filmes CHARACTER SET utf8mb4;
```
<!-- ____________________________________________________ -->

### Criar a tabela filmes
```sql
CREATE TABLE filmes(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    titulo VARCHAR(45) NOT NULL
    lancamento YEAR (4)
    genero_id INT
)
```

<!-- ___________________________________________________________ -->

### Criar a tabela generos
```sql
CREATE TABLE generos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    genero VARCHAR (45)
)
```

<!-- ___________________________________________________________ -->

### Criação da chave estrangeira (relacionamento entre tabelas)
```sql
ALTER TABLE filmes
# CONSTRAINT é uma restrição definida no relacionamento
ADD CONSTRAINT fk_filmes_generos

# A chave estrangeira deve fazer referência a chave primaria
FOREIGN KEY (genero_id) REFERENCES generos(id)
```

