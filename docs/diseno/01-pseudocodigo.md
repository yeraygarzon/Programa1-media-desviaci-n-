# Pseudocódigo — Programa 1 (PSP0)

Convenciones: `n` = cantidad de datos; acumuladores siempre `double`; la desviación es **muestral (n − 1)**.

## Dominio

```
CLASE Nodo
    Valor : double
    Siguiente : Nodo (o nulo)

CLASE ListaEnlazada
    cabeza, cola : Nodo (nulo al inicio)
    Cantidad : entero = 0

    Agregar(valor):
        nuevo = Nodo(valor)
        SI cabeza es nulo ENTONCES cabeza = nuevo; cola = nuevo
        SINO cola.Siguiente = nuevo; cola = nuevo
        Cantidad = Cantidad + 1

    Recorrer():                      // devuelve los valores en orden
        actual = cabeza
        MIENTRAS actual no es nulo
            ENTREGAR actual.Valor
            actual = actual.Siguiente
```

```
Media(lista):
    SI lista.Cantidad == 0 ENTONCES error "No hay datos"
    suma = 0.0
    PARA CADA x EN lista.Recorrer()
        suma = suma + x
    RETORNAR suma / lista.Cantidad

DesviacionEstandar(lista):
    SI lista.Cantidad < 2 ENTONCES error "Se necesitan al menos 2 datos"
    m = Media(lista)
    acumulado = 0.0
    PARA CADA x EN lista.Recorrer()
        d = x - m
        acumulado = acumulado + d * d
    RETORNAR raizCuadrada(acumulado / (lista.Cantidad - 1))
```

## Infraestructura

```
LeerArchivo(ruta):
    SI no existe el archivo ENTONCES error "Archivo no encontrado: <ruta>"
    lista = ListaEnlazada nueva
    numeroLinea = 0
    PARA CADA linea EN archivo
        numeroLinea = numeroLinea + 1
        linea = recortar espacios
        SI linea está vacía ENTONCES continuar
        SI no se puede convertir a número (cultura invariante)
            ENTONCES error "Línea <numeroLinea> no es un número: <linea>"
        lista.Agregar(valor)
    SI lista.Cantidad == 0 ENTONCES error "El archivo no contiene datos"
    RETORNAR lista
```

## Aplicación / Presentación

```
Principal(argumentos):
    ruta = argumentos[0], o pedirla por consola si falta
    INTENTAR
        lista = LeerArchivo(ruta)
        mostrar "n = ", lista.Cantidad
        mostrar "Media = ", Media(lista)  con 2 decimales
        mostrar "Desviación estándar = ", DesviacionEstandar(lista) con 2 decimales
    SI ocurre error ENTONCES mostrar mensaje; terminar con código 1
```
