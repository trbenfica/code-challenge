# Indicium Tech Code Challenge

Das tarefas pedidas, apenas o carregamento do order\_details.csv local para o banco de dados destino funciona.

Para executar:

```bash
docker-compose -f docker-compose.yml up
```

Usando o seguinte comando, é possível observar que os containers Docker rodam normalmente, sendo acessíveis pelas
portas específicadas no arquivo docker-compose:

```bash
docker ps
```

Para acessar os serviços:

- Airflow:
  - endereço: localhost:8080
  - user: airflow
  - senha: airflow
- Adminer:
  Útil para inspecionar os bancos de dados, tanto northwind, quanto o postgres destino.
  - endereço: localhost:32767
  - para northwind - servidor: db\_source | user: northwind | senha: thewindisblowing
  - para postgres destino - servidor: postgres | user: airflow | senha: airflow

Para executar o carregamento do csv para o postgres destino:

```bash
meltano run tap-csv target-postgres
```


