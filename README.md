# Teste Liquibase

## 1. Criar pasta e baixar o projeto

```bash
mkdir liquibase
cd liquibase
```

## 2. Download da versão 4.19.1 (open communitary)

```bash
wget https://github.com/liquibase/liquibase/releases/download/v4.19.1/liquibase-4.19.1.tar.gz
```

## 3. Descompactar

```bash
tar -xzf liquibase-4.19.1.tar.gz
cd ..
sudo mv liquibase /opt/liquibase
```

## 4. Baixar driver do Postgres

```bash
wget https://jdbc.postgresql.org/download/postgresql-42.7.3.jar -O /opt/liquibase/lib/postgresql.jar
```

## 5. Configurar variáveis de ambiente

```bash
echo 'export LIQUIBASE_HOME="/opt/liquibase"' >> ~/.bashrc
echo 'export PATH="$PATH:$LIQUIBASE_HOME"' >> ~/.bashrc
source ~/.bashrc
```

## 6. Testar o Liquibase

```bash
liquibase --version
```

## 7. Execução do projeto

### Iniciar PostgreSQL:

```bash
docker-compose up -d
```

### Executar migrações:

```bash
/opt/liquibase/liquibase --defaultsFile=./liquibase.properties update
```

**Observação:**  
O Liquibase vai conectar ao banco e executar o primeiro migration que está em `changelog/v1.xml`.
