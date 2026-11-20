# Estimación de tiempo · Programa 1 (PSP0)

En PSP0 no hay datos históricos, así que se estima por **descomposición**:
se divide el trabajo en tareas, se estima cada una y se suma. Los minutos de la
columna "Plan" son una referencia: **ajústalos a tu propio ritmo** antes de
escribir el total en PSP Tracker.

| Fase | Tarea | Plan (min) | Real (min) |
|------|-------|-----------:|-----------:|
| Planificación | Leer el enunciado, resolver preguntas, RF/RNF, estimar | 30 | |
| Diseño | Pseudocódigo, diagrama de clases, interfaz de consola | 50 | |
| Código | Lista enlazada + nodo | 25 | |
| Código | Calculadora (media y desviación) | 20 | |
| Código | Lector de archivo con validaciones | 25 | |
| Código | Interfaz de consola y programa principal | 20 | |
| Compilación | Compilar hasta 0 errores y 0 advertencias | 15 | |
| Pruebas | Casos de prueba (xUnit) y pruebas de consola | 60 | |
| Postmortem | Resumen del plan, revisión de registros, PIP | 25 | |
| | **Subtotal** | **270** | |
| | Contingencia 10 % | 27 | |
| | **Tiempo total planeado** | **297** | |

## Reglas

- El tiempo total planeado se escribe en **PSP Tracker antes de iniciar el Diseño**.
- La columna "Real" se llena en el Postmortem con el Time Log (no de memoria).
- No se cambia el plan al final para que coincida con lo real.

Error de estimación = (real − plan) / plan
