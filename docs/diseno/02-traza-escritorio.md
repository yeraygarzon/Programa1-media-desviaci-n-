# Traza de escritorio

Hazla **a mano** (calculadora o papel) y compara con lo esperado. Aquí tienes la referencia para verificar la tuya.

## Datos 1 (n = 10): 160, 591, 114, 229, 230, 270, 128, 1657, 624, 1503

**Media:** suma = 5506 → 5506 / 10 = **550.60**

| i | xᵢ | d = xᵢ − 550.6 | d² |
|---|------|----------|-------------|
| 1 | 160 | −390.6 | 152 568.36 |
| 2 | 591 | 40.4 | 1 632.16 |
| 3 | 114 | −436.6 | 190 619.56 |
| 4 | 229 | −321.6 | 103 426.56 |
| 5 | 230 | −320.6 | 102 784.36 |
| 6 | 270 | −280.6 | 78 736.36 |
| 7 | 128 | −422.6 | 178 590.76 |
| 8 | 1657 | 1106.4 | 1 224 120.96 |
| 9 | 624 | 73.4 | 5 387.56 |
| 10 | 1503 | 952.4 | 907 065.76 |

Σd² = 2 944 932.40
- Dividiendo entre n − 1 = 9 → 327 214.71 → √ = **572.03** ✔ (esperado)
- Dividiendo entre n = 10 → 294 493.24 → √ = 542.67 ✘ (error típico)

## Datos 2 (n = 10): 15.0, 69.9, 6.5, 22.4, 28.4, 65.9, 19.4, 198.7, 38.8, 138.2

Suma = 603.2 → media **60.32**

Σd² = 34 882.096 → / 9 = 3 875.788 → √ = **62.26** ✔
(Entre n daría 59.06 ✘)

## Casos límite para trazar también
| Entrada | Resultado esperado |
|---|---|
| 1 dato (p. ej. 5) | Media = 5; desviación → error "al menos 2 datos" |
| 2 datos (4 y 6) | Media = 5; Σd² = 2; /1 = 2; σ = 1.41 |
| Archivo vacío | Error "no contiene datos" |

> Si tu traza no coincide con lo esperado, **hay un defecto de diseño**: regístralo en PSP Tracker (inyectado en Planeación o Diseño, eliminado en Diseño) y corrígelo aquí antes de pasar a Código.
