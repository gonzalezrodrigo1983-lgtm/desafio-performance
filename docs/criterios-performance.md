# Criterios de aceptación de performance

| Métrica | Umbral propuesto | Observación |
|---|---:|---|
| Tiempo de respuesta promedio | <= 1000 ms | Medido sobre endpoints públicos DummyJSON |
| Tiempo máximo por muestra | <= 2000 ms | Validado con Duration Assertion |
| Error rate | 0% | No deben existir respuestas HTTP distintas al código esperado |
| Usuarios concurrentes base | 10 | Parametrizable con `-Dusers` |
| Ramp-up base | 10 segundos | Parametrizable con `-Drampup` |
| Iteraciones base | 5 | Parametrizable con `-Dloops` |
