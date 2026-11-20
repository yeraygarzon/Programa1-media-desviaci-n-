# Requisitos · Programa 1 (PSP0)

## Enunciado resumido

Leer un conjunto de n números reales (n no se conoce de antemano), guardarlos
en una lista enlazada y calcular su media aritmética y su desviación estándar.
Probar con los dos conjuntos de la tabla 6.1 y comparar con los resultados
esperados.

## Preguntas resueltas antes de estimar

| #  | Pregunta | Respuesta / decisión |
|----|----------|----------------------|
| P1 | ¿Lista propia o de la biblioteca? | Lista enlazada **propia** (clases `Nodo` y `ListaEnlazada`). Confirmar con el instructor. |
| P2 | ¿De dónde se leen los datos? | De un archivo de texto; un número por línea, punto decimal. Se ignoran las líneas en blanco. |
| P3 | ¿Desviación muestral o poblacional? | **Muestral (n − 1)**: es la única que reproduce los resultados esperados de la tabla. |
| P4 | ¿Cuántos decimales se muestran? | Dos. |
| P5 | ¿Qué pasa con archivo inexistente, vacío, dato no numérico o un solo dato? | Mensaje claro en español y código de salida 1. Con un solo dato la desviación no está definida. |

## Requisitos funcionales (RF)

| Id | Requisito | Criterio de aceptación |
|----|-----------|------------------------|
| RF-01 | Leer n números reales desde un archivo de texto (uno por línea). | Lee los 10 valores de cada conjunto de la tabla 6.1; ignora líneas en blanco. |
| RF-02 | Almacenar los números en una lista enlazada propia. | La lista conserva el orden de lectura y la cantidad n. |
| RF-03 | Calcular la media aritmética. | Conjunto 1: 550.60 · Conjunto 2: 60.32 (±0.01). |
| RF-04 | Calcular la desviación estándar muestral (n − 1). | Conjunto 1: 572.03 · Conjunto 2: 62.26 (±0.01). |
| RF-05 | Mostrar n, la media y la desviación con 2 decimales. | Salida en consola con tres líneas rotuladas. |
| RF-06 | Validar los datos y avisar con mensajes claros. | Archivo inexistente, vacío, valor no numérico (indica la línea) o n < 2: mensaje en español y código de salida 1. |
| RF-07 | Recibir la ruta del archivo como argumento o pedirla por consola. | `dotnet run -- datos/columna1_tamano_proxy.txt` o, sin argumento, la pide. |

## Requisitos no funcionales (RNF)

| Id | Requisito | Criterio de aceptación |
|----|-----------|------------------------|
| RNF-01 | Aplicación de consola en C# (.NET), multiplataforma. | Compila y ejecuta con `dotnet run`. |
| RNF-02 | Independiente de la configuración regional. | Con cultura es-CO, «15.0» se lee como 15.0 (no 150). |
| RNF-03 | Exactitud numérica. | Diferencia ≤ 0.01 frente a los valores esperados. |
| RNF-04 | Mantenibilidad: capas, estándar de codificación, métodos cortos. | Revisión contra el estándar; 0 advertencias del compilador. |
| RNF-05 | Usabilidad: mensajes en español que digan qué corregir. | Cada error indica la causa y la acción. |
| RNF-06 | Rendimiento. | 100 000 datos en menos de 1 s. |
| RNF-07 | Pruebas automatizadas (xUnit). | Cubre RF-01 a RF-06 y RNF-02, RNF-03, RNF-06. |
| RNF-08 | Control de versiones. | Al menos un commit al cerrar cada fase PSP. |

## Datos de prueba esperados (tabla 6.1)

| Conjunto | Archivo | n | Media | Desviación |
|----------|---------|---|-------|------------|
| Columna 1 (tamaño de proxy) | `datos/columna1_tamano_proxy.txt` | 10 | 550.60 | 572.03 |
| Columna 2 (horas de desarrollo) | `datos/columna2_horas.txt` | 10 | 60.32 | 62.26 |

> Comprobar que estos valores coinciden con los de la tabla 6.1 de tu material.
