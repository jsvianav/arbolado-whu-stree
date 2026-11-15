# Inventario de arbolado urbano con nubes de puntos LiDAR

Proyecto final de la Electiva de Ingeniería de Software, Universidad de San Buenaventura Cali. Trabajo realizado por John Viana.

En este proyecto se entrenó una red neuronal basada en PointNet++ que separa los árboles de las calles en nubes de puntos LiDAR del conjunto de datos WHU-STree. La red dice si cada punto es árbol y predice hacia dónde está el centro de su árbol, y después los árboles se separan buscando los picos de densidad de los puntos desplazados.

## Archivos

- `arbolado_whu_stree_E1_E2.ipynb` es el notebook ejecutado en Google Colab con el modelo entrenado en Nanjing y sus resultados en Nanjing (E1) y Shenyang (E2).
- `informe/informe_proyecto_final.pdf` es el informe técnico del proyecto.
- `resultados/E1_E2/` tiene las curvas de entrenamiento y las figuras de ejemplo.

## Resultados en prueba

Promedio y desviación estándar de tres semillas, en porcentaje.

| Experimento | mIoU | Det | Com | F1 | PQ |
|---|---|---|---|---|---|
| E1, Nanjing a Nanjing | 94,2 | 55,9 ± 0,2 | 38,7 ± 0,3 | 58,5 ± 0,2 | 47,7 ± 0,2 |
| E2, Nanjing a Shenyang | 96,0 | 71,9 ± 0,1 | 11,0 ± 0,2 | 79,5 ± 0,2 | 70,0 ± 0,1 |

## Cómo ejecutarlo

El notebook está pensado para Google Colab con GPU. Los datos de WHU-STree se piden a sus autores con el formulario del repositorio oficial (WHU-USI3DV/WHU-STree), y el identificador de la carpeta que ellos entregan se pega en la variable ID_CARPETA_WHU de la sección 1.1. La primera vez, el notebook copia las nubes de puntos a Mi unidad de Google Drive y después las procesa, entrena el modelo y lo evalúa. Si la sesión se desconecta, al volver a ejecutarlo continúa donde había quedado.

## Referencia del conjunto de datos

R. Ding, Z. Chen, W. Fan, C. Long, H. Xiao, Y. Zeng, Z. Dong, B. Yang, WHU-STree: A multi-modal benchmark dataset for street tree inventory, ISPRS Journal of Photogrammetry and Remote Sensing 233 (2026) 519–542.
