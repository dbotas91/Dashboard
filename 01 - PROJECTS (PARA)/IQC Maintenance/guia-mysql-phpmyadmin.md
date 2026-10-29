---
title: Guia MySQL / phpMyAdmin no Docker
date: 2026-10-29
---

# Guia MySQL / phpMyAdmin no Docker

Este documento descreve como utilizar o serviço MySQL/MariaDB que está rodando dentro do stack Docker do **Dashboard**, bem como como importar e exportar bases de dados usando tanto a linha de comando quanto a interface web do **phpMyAdmin**.

---

## 1. Visão geral do stack Docker

```yaml
services:
  db:
    image: mariadb:10.5
    environment:
      MYSQL_ROOT_PASSWORD: rootpassword
      MYSQL_DATABASE: iqc
      MYSQL_USER: iqc_user
      MYSQL_PASSWORD: iqc_pass
    volumes:
      - db_data:/var/lib/mysql
    ports:
      - "3306:3306"

  phpmyadmin:
    image: phpmyadmin/phpmyadmin
    environment:
      PMA_HOST: db
      PMA_USER: root
      PMA_PASSWORD: rootpassword
      # aumenta o limite de upload (default 64M)
      UPLOAD_LIMIT: 1G
    ports:
      - "8080:80"

volumes:
  db_data:
```

- **db** – contém o MariaDB (MySQL compatível).
- **phpmyadmin** – interface web que se conecta ao serviço `db`.

> O serviço está exposto nas portas **3306** (MySQL) e **8080** (phpMyAdmin) na sua máquina WSL.

---

## 2. Conectar à base de dados via linha de comando

```bash
# Entrar no container do MySQL
docker compose exec db mysql -u root -p$MYSQL_ROOT_PASSWORD
```

### 2.1 Listar bancos de dados

```sql
SHOW DATABASES;
```

### 2.2 Fazer backup (mysqldump)

```bash
# Backup completo (descomprimido)
mysqldump -u root -p$MYSQL_ROOT_PASSWORD --all-databases > all-databases.sql

# Backup comprimido (gzip)
mysqldump -u root -p$MYSQL_ROOT_PASSWORD --all-databases | gzip > all-databases.sql.gz
```

> **Dica:** Salve os arquivos de dump em um diretório montado, por exemplo `/mnt/c/Users/Lenovo/Downloads/` para acesso fácil a partir do Windows.

---

## 3. Restaurar a base de dados via linha de comando

### 3.1 Restaurar arquivo `.sql`

```bash
cat mydump.sql | docker compose exec -T db mysql -u root -p$MYSQL_ROOT_PASSWORD
```

### 3.2 Restaurar arquivo `.sql.gz`

```bash
zcat mydump.sql.gz | docker compose exec -T db mysql -u root -p$MYSQL_ROOT_PASSWORD
```

> O parâmetro `-T` evita alocação de pseudo‑tty, o que impede mensagens de erro como *"current working directory is outside of container mount namespace"*.

---

## 4. Importar/Exportar via phpMyAdmin

1. Abra o navegador e acesse `http://localhost:8080`.
2. Login com **root** e a senha **rootpassword** (ou o usuário que definiu).
3. **Exportar**:
   - Selecione o banco desejado → *Export* → *Quick* → *Go*.
4. **Importar**:
   - Clique em *Import*.
   - Escolha o arquivo `.sql` ou `.sql.gz`.
   - **Importante:** O tamanho máximo de upload padrão é **64 MB**. Para arquivos maiores, ajuste a variável `UPLOAD_LIMIT` no `docker‑compose.yml` (já incluído acima) e reinicie o stack:
     ```bash
     docker compose up -d --build phpmyadmin
     ```
5. **Selecionar arquivos WSL a partir do Windows**
   - O seletor de arquivos do navegador roda no Windows, portanto não consegue navegar diretamente em caminhos Linux. Use o caminho UNC:
     ```
     \\wsl.localhost\Ubuntu\home\dbotas\caminho\para\arquivo.sql.gz
     ```
   - Ou copie temporariamente o dump para um diretório Windows (ex.: `C:\Users\Lenovo\Downloads`) e selecione‑o.

---

## 5. Ajustar limites de tempo e memória (opcional)

Se a importação demorar muito, aumente o timeout do phpMyAdmin editando o serviço:

```yaml
  phpmyadmin:
    environment:
      PMA_HOST: db
      PMA_USER: root
      PMA_PASSWORD: rootpassword
      UPLOAD_LIMIT: 1G
      # tempo máximo de execução em segundos (default 300)
      PHP_TIMEOUT: 1800
```

Depois, reinicie:

```bash
docker compose up -d phpmyadmin
```

---

## 6. Solução de problemas comuns

| Problema | Causa provável | Como resolver |
|---|---|---|
| `ERROR 1045 (28000): Access denied for user` | Senha ou usuário incorreto | Verifique `MYSQL_ROOT_PASSWORD` no `docker‑compose.yml` e use `-p$MYSQL_ROOT_PASSWORD` sem espaço. |
| `File exceeds upload_max_filesize` | Limite padrão 64 M | Defina `UPLOAD_LIMIT` (ex.: `1G`) no serviço `phpmyadmin` e reinicie. |
| `current working directory is outside of container mount namespace` | Uso de `docker exec` sem `-T` | Use `docker compose exec -T db …` como nos exemplos de restauração. |
| phpMyAdmin não vê arquivos do WSL | Navegador abre seletor Windows | Use caminho UNC (`\\wsl.localhost\...`) ou copie para Windows antes de importar. |

---

## 7. Resumo rápido (cheat‑sheet)

```bash
# Entrar no MySQL
docker compose exec db mysql -u root -p$MYSQL_ROOT_PASSWORD

# Dump completo
mysqldump -u root -p$MYSQL_ROOT_PASSWORD --all-databases | gzip > /mnt/c/Users/Lenovo/Downloads/all.sql.gz

# Restaurar gzipped dump
zcat /mnt/c/Users/Lenovo/Downloads/all.sql.gz | docker compose exec -T db mysql -u root -p$MYSQL_ROOT_PASSWORD
```

---

**Pronto!** Você agora tem um guia completo para trabalhar com MySQL/MariaDB e phpMyAdmin dentro do seu ambiente Docker.
