# VRC / HRV RRi Analyzer Pro v9.1

## Cambios v8.6
- Añadida interpretación avanzada de HVG/grafos.
- Añadida clasificación compacto local / equilibrado / disperso global.
- Añadido índice de compactación HVG en escala -2 a +2.
- Añadidas definiciones y valores orientativos de métricas HVG.
- Añadidas definiciones y valores orientativos de dominios:
  - Amplitud
  - Vagal
  - Complejidad
  - MSE 1-20
  - Recurrencia
- Conserva correcciones v8.5:
  - SampEn y MSE con la misma señal y tolerancia.
  - MSE1 = SampEn.
  - Entropías con λ=500.


## v8.7
- Añadida exportación completa de gráficos desde la pestaña Exportar.
- El ZIP incluye una carpeta `graficos/` con archivos HTML interactivos.
- Se exportan gráficos de HRV, dominios, MSE, Dashboard, Poincaré, RRi superpuesto y HVG/grafos cuando están disponibles.
- Opción experimental para intentar exportar PNG si el servidor tiene kaleido disponible.


## v8.8
- Exportación de gráficos en PNG, SVG y/o HTML interactivo desde la pestaña Exportar.
- Añadido `kaleido` a requirements.txt para generar PNG/SVG directamente desde Plotly.
- El ZIP incluye un script `convert_html_to_png.py` para convertir los HTML a PNG localmente si Streamlit Cloud no permite PNG automático.
- Carpeta de salida:
  - `graficos/html`
  - `graficos/png`
  - `graficos/svg`
  - `graficos/indice_graficos_exportados.csv`


## v8.9
- Corrige el NameError de `CONVERT_HTML_TO_PNG_SCRIPT`.
- El script `convert_html_to_png.py` queda definido antes de la pestaña Exportar.
- Añadida protección para que un fallo al escribir el script no bloquee la app.


## v9.0
- Corrige el KeyError en Poincaré/Grafos cuando `long_df` no contiene columna `Fase`.
- La sección HVG ahora muestra un aviso si no hay métricas disponibles en vez de romper la app.


## v9.1
- Corrige la exportación de gráficos para conservar colores.
- Añadida paleta fija `EXPORT_COLORWAY`.
- PNG, SVG y HTML se preparan con plantilla `plotly_dark`, fondo oscuro y colores explícitos.
- Evita que los traces sin color explícito salgan en gris al exportar con Kaleido.
