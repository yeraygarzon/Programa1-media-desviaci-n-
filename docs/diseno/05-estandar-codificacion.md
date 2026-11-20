# Estándar de codificación (C#)

| Tema | Regla |
|---|---|
| Nombres | Clases y métodos `PascalCase`; variables locales y campos privados `camelCase` |
| Idioma | Identificadores en español, sin tildes ni ñ |
| Métodos | Máximo 30 líneas; una sola responsabilidad |
| Acumuladores | Siempre `double` (nunca `int`) |
| Números | Convertir con `CultureInfo.InvariantCulture` y `NumberStyles.Float` |
| Errores | Lanzar excepciones con mensaje claro; capturarlas solo en `Programa` |
| Comentarios | Cabecera por clase con su propósito; comentar el "por qué", no el "qué" |
| Llaves y sangría | 4 espacios; llaves en línea nueva |
| Compilación | 0 errores y 0 advertencias |
| Prohibido | `List<T>` o arreglos para guardar los datos (se usa `ListaEnlazada`) |
