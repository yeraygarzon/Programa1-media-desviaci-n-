# Diseño de la interfaz de consola

Uso: `dotnet run --project src -- datos/datos1.txt` (si falta el argumento, el programa pide la ruta).

| Escenario | Salida | Código |
|---|---|---|
| 1. Datos válidos | `n = 10`<br>`Media = 550.60`<br>`Desviación estándar = 572.03` | 0 |
| 2. Archivo inexistente | `Error: archivo no encontrado: datos/x.txt` | 1 |
| 3. Archivo vacío | `Error: el archivo no contiene datos` | 1 |
| 4. Línea inválida | `Error: línea 4 no es un número: abc` | 1 |

Reglas: dos decimales; punto como separador decimal en la salida (cultura invariante); mensajes de error siempre empiezan con `Error:`.
