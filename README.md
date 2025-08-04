# Databases

In this project you will find docker runtimes for the following databases:

* MariaDB
* MongoDB
* Microsoft SQL Server (MSSQL)
* PostgreSQL
* Redis

All databases are configured to run in Docker containers, making it easy to set up and test locally. The files are written as Docker Compose files (**not** Docker Swarm Compose files).

## Running the databases

### MariaDB

* Type: Relational database
* Host: `localhost`
* Port: `3306`
* Username: `root`
* Password: `root`
* Default database: `playground`

#### Database Management

* [http://localhost:8082 (phpMyAdmin)](http://localhost:8082) (local web interface)
* [MySQL Workbench](https://www.mysql.com/products/workbench/) (Download link)

#### Commands

**Run MariaDB database**

```bash
docker compose -f mariadb-compose.yml up -d
```

**Stop MariaDB database**

```bash
docker compose -f mariadb-compose.yml down
```

### MongoDB

* Type: Document database
* Host: `localhost`
* Port: `27017`
* Username: `root`
* Password: `root`
* Default database: [no default, just request a database (e.g. `playground`) and it will be created automatically]

#### Database Management

* [http://localhost:8081 (Mongo Express)](http://localhost:8081) (local web interface)
* [MongoDB Compass](https://www.mongodb.com/try/download/compass) (Download link)

#### Commands

**Run MongoDB database**

```bash
docker compose -f mongodb-compose.yml up -d
```

**Stop MongoDB database**

```bash
docker compose -f mongodb-compose.yml down
```

### Microsoft SQL Server (MSSQL)

* Type: Relational database
* Host: `localhost`
* Port: `1433`
* Username: `sa`
* Password: `Password123!`
* Default database: [Not automatically created, you can create a database using SQL Server Management Studio or Azure Data Studio]

#### Management

* [Azure Data Studio](https://azure.microsoft.com/en-us/products/data-studio) (Download link)
* [SQL Server Management Studio (SSMS)](https://learn.microsoft.com/en-us/ssms/) (Download link)

#### Commands

**Run MSSQL database**

```bash
docker compose -f mssql-compose.yml up -d
```

**Stop MSSQL database**

```bash
docker compose -f mssql-compose.yml down
```

### PostgreSQL

* Type: Relational database
* Host: `localhost`
* Port: `5432`
* Username: `root`
* Password: `root`
* Default database: `playground`

#### Database Management

* [http://localhost:8083 (adminer)](http://localhost:8083) (simple local web interface)
    * Credentials:
        * System: `PostgreSQL`
        * Server: `db` (`localhost` is only used on host system)
        * Username: `root`
        * Password: `root`
* [http://localhost:8084 (pgAdmin)](http://localhost:8084) (full-featured local web interface)

#### Commands

**Run PostgreSQL database**

```bash
docker compose -f postgres-compose.yml up -d
```

**Stop PostgreSQL database**

```bash
docker compose -f postgres-compose.yml down
```

### Redis

* Type: In-memory data structure store
* Host: `localhost`
* Port: `6379`
* Username: [not applicable, this Redis instance does not use authentication by default]
* Password: [not applicable, this Redis instance does not use authentication by default]
* Default database: [no default database, Redis uses a single database by default]

There is not provided any volume for redis, since it by default is an in-memory database. If you want to persist data, you can add a volume to the `redis-compose.yml` file (it is commented out by default).
