# Desafío Técnico - Ejercicio de Performance con JMeter

## Objetivo
Ejecutar una prueba de performance sobre una URL pública de práctica QA:

- URL base: `https://dummyjson.com`
- Endpoints parametrizados en CSV:
  - `/products/1`
  - `/products/search?q=phone`
  - `/carts/1`

## Stack técnico
- Java 17
- Maven 3.9.1 compatible
- Apache JMeter ejecutado mediante `jmeter-maven-plugin`
- Datos parametrizados en CSV
- Reporte HTML Dashboard de JMeter

## Estructura relevante
```text
src/test/jmeter/dummyjson-products-performance.jmx
src/test/resources/data/performance-endpoints.csv
docs/criterios-performance.md
```

## Ejecutar prueba de performance
Ejecución base:
```bash
mvn clean verify
```

Ejecución parametrizada:
```bash
mvn clean verify -Dhost=dummyjson.com -Dprotocol=https -Dusers=10 -Drampup=10 -Dloops=5
```

## Reportes generados
- Resultados JTL/CSV: `target/jmeter/results/`
- Dashboard HTML JMeter: `target/jmeter/reports/`

## Criterios de aceptación
Ver `docs/criterios-performance.md`.

## Observaciones QA
La prueba usa datos parametrizados en CSV, valida códigos HTTP esperados y considera una aserción de SLA máximo de 2000 ms por request. Los valores de carga pueden modificarse por propiedades Maven sin tocar el archivo JMX.
# desafio-performance
#
