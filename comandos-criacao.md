# comandos SQL - Referência 
<!-- ______________________________________________ -->
## Modelagem física 

### Criar banco de dados
```sql
CREATE DATABASE vendas CHARACTER SET utf8mb4;
```
<!-- ____________________________________________________ -->

### Criar a tabela fabricantes
```sql
CREATE TABLE fabricantes(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL
)
```
<!-- ________________________________________________________ -->
```sql
CREATE TABLE produtos (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL,
    descricao TEXT (1000) NOT NULL,
    preco DECIMAL (6,2) NOT NULL,
    quantidade TINYINT (4) NOT NULL
)
```

<!-- ____________________________________________________ -->

### Adicionar campo/coluna em uma tabela
```sql
ALTER TABLE produtos ADD fabricante_id INT NOT NULL
AFTER quantidade;
```
<!-- _______________________________ -->

### Criação da chave estrangeira (relacionamento entre tabelas)
```sql
ALTER TABLE produtos
# CONSTRAINT é uma restrição definida no relacionamento
ADD CONSTRAINT fk_produtos_fabricantes

# A chave estrangeira deve fazer referência a chave primaria
FOREIGN KEY (fabricante_id) REFERENCES fabricantes(id)
```

<!-- _______________________________________________ -->
# Comando SQL - Para CRUD (Referência)

## Resumo
C -> Create (Insere dados)
R -> Read (Ler dados)
U -> Update (Atualizar dados)
D -> Delete (Deletar dados)

## Insert
## fabricantes
```sql
INSERT INTO fabricantes (nome) VALUES ('Asus');
INSERT INTO fabricantes (nome) VALUES ('Dell');
INSERT INTO fabricantes (nome) 
VALUES ('Apple'), ('LG'), ('Samsung'), ('Brastemp');
```

<!-- ______________________________________________________ -->
## Inset
## Produtos
```sql
INSERT INTO produtos (nome, descricao, preco, quantidade, fabricante_id) VALUES (
    'Ultrabook',
    'Ultrabook Asus Intel Core 19',
    6500.99,
    7,
    1
);
INSERT INTO produtos (nome, descricao, preco, quantidade, fabricante_id) VALUES (
    'Geladeira',
    'FrostFree com acesso a internet',
    8500.99,
    10,
    6 -- Brastemp
);
INSERT INTO produtos (nome, descricao, preco, quantidade, fabricante_id) VALUES (
    'Tablet Android',
    'tablet 10 polegadas com 256gb de armazenamento',
    4999,,
    3,
    5 -- Samsung
);
INSERT INTO produtos (nome, descricao, preco, quantidade, fabricante_id) VALUES (
    'Iphone 14 Pro Max',
    'Processador Bionic 15 com 512gb de armazenamento',
    4999,,
    3,
    5 -- Apple
);
INSERT INTO produtos (nome, descricao, preco, quantidade, fabricante_id) VALUES (
    'Ipad Mini',
    'Tablet com tela de retina 4k com 512gb  de armazenamento',
    5000,
    8,
    3 -- Apple
);
```