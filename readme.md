# Migraciones - Documentación de uso

Este proyecto contiene la base de datos y migraciones para el funcionamiento del proyecto de prueba de uso de webhooks

## Requisitos previos
asegúrese de realizar las siguientes acciones para que el proyecto funcione correctamente

- Configurar adecuadamente el archivo `liquibase/liquibase.properties`.

## Comandos

### Ejecucion de migraciones

```bash
docker run --rm --network events-network -v $(pwd)/liquibase.properties:/liquibase/liquibase.properties -v $(pwd)/changelog.xml:/liquibase/changelog.xml -v $(pwd)/changelog:/liquibase/changelog liquibase --defaults-file=/liquibase/liquibase.properties update
  ```

### Rollback de migraciones

```bash
docker run --rm --network events-network -v $(pwd)/liquibase.properties:/liquibase/liquibase.properties -v $(pwd)/changelog.xml:/liquibase/changelog.xml -v $(pwd)/changelog:/liquibase/changelog liquibase --defaults-file=/liquibase/liquibase.properties rollbackCount 1
  ```