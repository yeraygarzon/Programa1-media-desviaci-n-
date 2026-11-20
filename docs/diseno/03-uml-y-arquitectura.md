# Diagrama de clases, capas y actividad

## Clases

```mermaid
classDiagram
    class Nodo {
        +double Valor
        +Nodo Siguiente
    }
    class ListaEnlazada {
        -Nodo cabeza
        -Nodo cola
        +int Cantidad
        +Agregar(double valor)
        +Recorrer() IEnumerable~double~
    }
    class CalculadoraEstadistica {
        +Media(ListaEnlazada) double
        +DesviacionEstandar(ListaEnlazada) double
    }
    class LectorArchivoNumeros {
        +Leer(string ruta) ListaEnlazada
    }
    class ConsolaUI {
        +ObtenerRuta(string[] args) string
        +MostrarResultados(int n, double media, double desv)
        +MostrarError(string mensaje)
    }
    class Programa {
        +Main(string[] args) int
    }
    ListaEnlazada "1" o-- "0..*" Nodo
    CalculadoraEstadistica ..> ListaEnlazada
    LectorArchivoNumeros ..> ListaEnlazada
    Programa ..> LectorArchivoNumeros
    Programa ..> CalculadoraEstadistica
    Programa ..> ConsolaUI
```

## Arquitectura en 4 capas

| Capa | Contiene | Depende de |
|---|---|---|
| Dominio | `Nodo`, `ListaEnlazada`, `CalculadoraEstadistica` | nada |
| Infraestructura | `LectorArchivoNumeros` (archivos) | Dominio |
| Presentación | `ConsolaUI` (entrada/salida por consola) | — |
| Aplicación | `Programa` (orquesta el flujo) | las tres anteriores |

Motivo: el Dominio no sabe de archivos ni de consola, así que se prueba con xUnit sin tocar disco, y se puede reutilizar.

**Sin base de datos:** el enunciado solo pide leer un archivo, calcular y mostrar; no hay que conservar datos entre ejecuciones.

## Estructura de carpetas
```
src/
  Dominio/            Nodo.cs, ListaEnlazada.cs, CalculadoraEstadistica.cs
  Infraestructura/    LectorArchivoNumeros.cs
  Presentacion/       ConsolaUI.cs
  Aplicacion/         Programa.cs
tests/                pruebas xUnit
```

## Diagrama de actividad

```mermaid
flowchart TD
    A([Inicio]) --> B[Obtener ruta]
    B --> C{¿Archivo existe?}
    C -- No --> X[Mostrar error] --> Z([Fin código 1])
    C -- Sí --> D[Leer línea a línea]
    D --> E{¿Línea válida?}
    E -- No --> X
    E -- Sí --> F[Agregar a la lista]
    F --> G{¿Más líneas?}
    G -- Sí --> D
    G -- No --> H{¿n ≥ 2?}
    H -- No --> X
    H -- Sí --> I[Calcular media y desviación]
    I --> J[Mostrar resultados] --> K([Fin código 0])
```
