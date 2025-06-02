# Liquibase Test

## 1. Create project folder

```bash
mkdir liquibase
cd liquibase
```

## 2. Download version 4.19.1 (community edition)

```bash
wget https://github.com/liquibase/liquibase/releases/download/v4.19.1/liquibase-4.19.1.tar.gz
```

## 3. Extract files

```bash
tar -xzf liquibase-4.19.1.tar.gz
cd ..
sudo mv liquibase /opt/liquibase
```

## 4. Download PostgreSQL driver

```bash
wget https://jdbc.postgresql.org/download/postgresql-42.7.3.jar -O /opt/liquibase/lib/postgresql.jar
```

## 5. Configure environment variables

```bash
echo 'export LIQUIBASE_HOME="/opt/liquibase"' >> ~/.bashrc
echo 'export PATH="$PATH:$LIQUIBASE_HOME"' >> ~/.bashrc
source ~/.bashrc
```

## 6. Test Liquibase

```bash
liquibase --version
```

## 7. Project execution

### Start PostgreSQL:

```bash
docker-compose up -d
```

### Run migrations:

```bash
/opt/liquibase/liquibase --defaultsFile=./liquibase.properties update
```

**Note:**  
Liquibase will connect to the database and execute the first migration located in `changelog/v1.xml`.
