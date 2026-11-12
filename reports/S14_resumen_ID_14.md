# Resumen S14 - Estudiante ID 14

- Semilla: 1014 | Huella de la muestra: `cc67cfaa181c` | Partición: 24500 / 5250 / 5250 (prueba sin usar)
- Umbral: 0.5 | `class_weight='balanced'` | Costos supuestos: FP = R$ 8, FN = R$ 35

## PCA
- Variables numéricas iniciales: 24
- Componentes para explicar >= 90 % de la varianza: 15 (90.57 % conservado)

## Comparación en validación
| experimento | descripcion | accuracy | precision | recall | f1 | ap | fp | fn | costo_brl |
|---|---|---|---|---|---|---|---|---|---|
| A | Sin PCA, C=1.0 | 0.679 | 0.1268 | 0.6366 | 0.2115 | 0.1605 | 1556 | 129 | 16963 |
| B | PCA 90 %, C=1.0 | 0.6629 | 0.1128 | 0.5803 | 0.1888 | 0.1304 | 1621 | 149 | 18183 |
| C | PCA 90 %, C=0.1 | 0.664 | 0.114 | 0.5859 | 0.1908 | 0.1305 | 1617 | 147 | 18081 |
| D | PCA 90 %, C=10.0 | 0.6619 | 0.1129 | 0.5831 | 0.1891 | 0.1287 | 1627 | 148 | 18196 |

- Mayor Accuracy: **A** | Mayor Recall: **A** | Menor costo: **A**
- Referencia "nunca alerta": costo R$ 12,425
- Modelo elegido por costo: **A** (Sin PCA, C=1.0), costo R$ 16,963

## Prueba KS sobre `valor_flete` (entrenamiento vs. validación)
- D = 0.0145 | p = 0.3167 | alfa = 0.05 -> **No rechazar H0**
- La prueba compara particiones; no compara modelos.
