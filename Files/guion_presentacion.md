# Guión de Presentación — Deforestación en México
## Visualización de Datos y Narración de Historias
**Tiempo total: 10 minutos · 20 diapositivas**

---

> **Cómo usar este guión:**
> Las frases en *cursiva* son lo que dices en voz alta.
> Las notas entre corchetes [así] son recordatorios para ti, no se dicen.
> Cada sección tiene el tiempo aproximado.

---

## 🟢 BLOQUE 1 — La historia y los datos (Slides 1–7) · ~3 min

---

### Slide 1 — Portada · 15 seg
*"Buenos días. Voy a hablarles de algo que pasa en México y que casi nadie nota: estamos perdiendo bosques a una velocidad alarmante. La pregunta que intentamos responder es: ¿quién o qué está detrás de eso? Y lo vamos a responder con datos."*

---

### Slide 2 — El problema · 30 seg
*"México es el cuarto país con mayor biodiversidad del mundo. Pero en los últimos 23 años ha perdido casi 5 millones de hectáreas de cobertura arbórea. Para que se hagan una idea: eso es equivalente a borrar del mapa 112 veces la Ciudad de México. Y lo que es más preocupante: la velocidad de esa pérdida no es constante."*

---

### Slides 3–4 — Problemática · 30 seg
*"El problema tiene varias capas. No es solo que se corten árboles — es que esa tierra se convierte en algo más: pastizales para ganado, plantaciones de aguacate, palma africana. El cambio de uso de suelo es la causa real, y es difícil de rastrear porque el gobierno y los satélites no dicen lo mismo."*

---

### Slide 5 — Fuentes de datos · 45 seg
*"Para investigar esto usamos cuatro fuentes de datos. La primera es Global Forest Watch — una plataforma satelital que mide la pérdida de árboles año a año. La segunda es el SIAP, que registra qué se siembra en cada estado de México. La tercera — y esta es nueva — son los datos de producción ganadera, que nos dicen cuántas vacas, cerdos y aves se producen en cada municipio. Y la cuarta es la propia base de datos del gobierno sobre deforestación. Ya les voy a mostrar por qué esa última es… interesante."*

---

### Slides 6–7 — Datos forestales y agrícolas · 30 seg
*"Estos son los datos del EDA, el análisis exploratorio inicial. Lo que ya podíamos ver era claro: pérdida forestal sostenida, y cultivos como el aguacate y la palma africana creciendo a tasas del 180% y 495% respectivamente en 22 años. Eso nos dio las hipótesis de partida."*

---

### Slide 8 — Hipótesis iniciales · 15 seg
*"Con eso en mente planteamos cuatro hipótesis. Las vamos a revisitar al final para ver cuáles se sostienen con los datos."*

---

### Slides 9–10 — Hallazgo exploratorio · 30 seg
*"El EDA ya nos mostraba algo importante: Campeche, Chiapas y Quintana Roo concentran más del 50% de toda la pérdida forestal nacional. No es un problema uniforme — es un problema del sureste mexicano.*"

---

## 🟡 BLOQUE 2 — Los datos nuevos y el preprocesamiento (Slides 11–12) · ~1.5 min

---

### Slide 11 — Producción Pecuaria · 45 seg

[Señala la tabla con los datos del dataset ganadero]

*"Para la segunda fase del análisis incorporamos los datos de producción ganadera del SIAP. Tenemos registros de 2006 a 2024, a nivel municipio, separados por especie y producto. Casi medio millón de registros.*

*Pero hay algo raro aquí. ¿Ven esto? El año 2023 no existe en la base de datos. El gobierno lo omitió. Y eso no es un error técnico — es una decisión. El año 2023 corresponde al cierre del sexenio y a un periodo de deforestación elevada. Vamos a ver eso con detalle más adelante."*

---

### Slide 12 — Filtrado y preprocesamiento · 45 seg

[Señala las tres columnas: filtrado, ruido, normalización]

*"Antes de analizar, tuvimos que limpiar los datos. Estas son las decisiones más importantes que tomamos:*

*Primero, usamos un umbral del 30% de cobertura arbórea — ese es el estándar internacional para bosques tropicales densos. No cualquier árbol cuenta.*

*Segundo, nos enfocamos solo en ganado bovino porque es el que históricamente se asocia con deforestación tropical — los ranchos ganaderos requieren desmontar selva.*

*Tercero, trabajamos con la ventana 2006-2022 porque es el único período donde los tres datasets coinciden.*

*Y aplicamos una técnica llamada eliminación de ruido — básicamente un promedio móvil de tres años — para separar la tendencia real de la variabilidad climática año a año."*

---

## 🔴 BLOQUE 3 — Los análisis estadísticos (Slides 13–18) · ~4 min

---

### Slide 13 — Distribuciones e intervalos de confianza · 60 seg

[Señala primero la gráfica izquierda: barras por año]

*"Esta es una de mis gráficas favoritas porque cuenta una historia muy clara. Las barras verdes son los años normales — México pierde entre 150,000 y 265,000 hectáreas por año, eso es lo esperado. Las barras naranjas son años preocupantes, y las rojas son los años de alarma.*

*El 2019 salta completamente. 327,000 hectáreas en un solo año — 54% por encima del promedio histórico. Eso en estadística se llama outlier, un valor anómalo. ¿Qué pasó en 2019? Fue el primer año completo del actual gobierno y el año en que se cancelaron los programas de conservación.*

*La gráfica de la derecha muestra algo igualmente importante: los años después de 2018 tienen un promedio de pérdida 20% mayor que los años anteriores. Esa diferencia es estadísticamente significativa — no es coincidencia."*

---

### Slide 14 — Tests de hipótesis: el dato más impactante · 60 seg

[Señala la gráfica de la derecha: gobierno vs satélite]

*"Esta es la gráfica más importante de toda la presentación. El área verde es lo que detectan los satélites de Global Forest Watch. El área morada, mucho más pequeña, es lo que el gobierno mexicano reconoce oficialmente como deforestación.*

*La brecha promedio es del 40 al 55%. Es decir, el gobierno reconoce menos de la mitad de lo que los satélites ven. En 2019 — el peor año — la diferencia fue de 223,000 hectáreas que simplemente no aparecen en los datos oficiales.*

*Aquí el análisis de datos ya no es solo académico — es una herramienta de transparencia. Los satélites no mienten. Los datos oficiales sí pueden ser convenientes."*

[Pausa breve para que el mensaje cale]

---

### Slide 15 — Prueba A/B · 45 seg

[Señala el gráfico de barras horizontales]

*"Aquí hicimos un experimento. Dividimos los 32 estados en dos grupos: los que tienen más ganado bovino y los que tienen menos. La pregunta era: ¿pierden más bosque los estados ganaderos?*

*La respuesta es: sí hay diferencia, pero la prueba estadística nos dice que no es suficientemente robusta para concluir que la ganadería sola explica la deforestación. ¿Por qué? Porque Jalisco tiene muchísimo ganado pero no está en la selva tropical — y Campeche tiene deforestación enorme con ganadería moderada. La clave no es cuánto ganado, sino dónde está ese ganado. La ubicación geográfica en zonas de selva importa más que el volumen de producción."*

---

### Slide 16 — Grafos · 45 seg

[Señala el heatmap primero, luego el grafo circular]

*"Para entender qué estados se 'comportan igual' en términos de deforestación, construimos una red de correlaciones. Piénsenlo así: si dos estados suben y bajan su pérdida forestal al mismo tiempo, tienen una correlación alta.*

*El heatmap de la izquierda muestra esto para los 16 estados más afectados — entre más verde el cuadro, más sincronizados están. Y a la derecha está el resultado más interesante: Campeche, Chiapas, Tabasco, Veracruz, Quintana Roo y Oaxaca forman lo que llamamos el 'corredor del Golfo' — un grupo de estados que siempre se mueven juntos. Cuando uno tiene un año malo, los demás también. Eso sugiere causas comunes: incendios de temporada, políticas federales, o presión ganadera regional."*

---

### Slide 17 — Reducción de dimensionalidad · 45 seg

[Señala el scatter plot grande]

*"Esta técnica se llama PCA y parece complicada, pero el concepto es sencillo: tomamos 34 variables por estado — 17 años de pérdida forestal y 17 años de ganadería bovina — y las comprimimos en dos ejes para poder verlas en una sola gráfica.*

*Cada punto es un estado. Los que están cerca se parecen en su patrón. Hacia la derecha están los estados con alta deforestación y alta ganadería — ven que los puntos rojos, los de riesgo crítico, se agrupan: Campeche, Chiapas, Quintana Roo, Veracruz. A la izquierda están los estados que prácticamente no tienen problema — Aguascalientes, Tlaxcala, la Ciudad de México.*

*Lo importante: cuando agregamos la ganadería a las variables, los grupos se separan más claramente. Eso nos dice que la ganadería sí agrega información para entender qué estados son más vulnerables."*

---

### Slide 18 — Anonimización · 30 seg

[Señala brevemente las gráficas de antes/después]

*"Un punto importante en ciencia de datos es la privacidad. Los datos ganaderos llegan a nivel municipio — y en un municipio pequeño, un productor grande es prácticamente identificable. Aplicamos una técnica llamada k-anonimato: si un estado tiene menos de 5 municipios en la base de datos, los agrupamos bajo 'datos agrupados'. Así preservamos la estadística estatal sin exponer a productores individuales. Es una práctica estándar en análisis de datos sensibles."*

---

## 🟢 BLOQUE 4 — El veredicto y las conclusiones (Slides 19–20) · ~1.5 min

---

### Slide 19 — Hipótesis finales · 45 seg

[Lee cada hipótesis brevemente, enfatiza el veredicto]

*"Regresamos a las hipótesis de partida.*

*H1 sobre cultivos de exportación: parcialmente confirmada. El aguacate y la palma sí crecen junto con la pérdida forestal, pero la correlación no es tan directa como esperábamos.*

*H2 sobre el sureste: completamente confirmada. Campeche, Chiapas, Quintana Roo y Veracruz acumulan el 59% de toda la pérdida nacional.*

*H3 sobre la tendencia creciente: confirmada, con un matiz — el pico de 2019 es real y estadísticamente anómalo, y coincide con un cambio de política pública.*

*H4 sobre la ganadería: soportada pero no concluyente. Los pastizales son el principal destino del bosque deforestado, pero necesitamos datos más granulares para probarlo estadísticamente."*

---

### Slide 20 — Conclusiones · 45 seg

[Habla pausado, sin apresurar — es el cierre]

*"Cerramos con cinco conclusiones.*

*Uno: México perdió el equivalente a 112 ciudades de México en bosques en 23 años.*

*Dos: 2019 no fue un año normal. Fue el peor año de la serie y coincide exactamente con un cambio de política pública.*

*Tres: La ganadería bovina es un driver encubierto. El bosque se convierte principalmente en pastizal. Y el gobierno decidió no publicar los datos ganaderos de 2023.*

*Cuatro: El gobierno reconoce menos de la mitad de la deforestación que los satélites detectan. Los datos públicos oficiales no son suficientes para entender la crisis.*

*Cinco: La deforestación no es aleatoria — hay un corredor del Golfo que concentra el problema y que se mueve de forma sincronizada.*

*Este trabajo demuestra que la ciencia de datos no es solo un ejercicio académico. Es una herramienta para hacer preguntas que el gobierno preferiría que no se hicieran. Gracias."*

---

## 📌 Consejos de presentación

**Antes de empezar:**
- Practica el slide 14 (gobierno vs satélite) — es el más impactante, no lo apresures
- El slide 20 es tu cierre — habla más lento ahí, no corras

**Para no-técnicos:**
- Nunca digas "Pearson", "bootstrap" o "p-value" en voz alta
- En su lugar: "la estadística nos dice", "con 95% de certeza", "esto no es coincidencia"
- Si alguien pregunta por el p-value: *"Es una medida de qué tan probable es que el resultado sea pura casualidad — en este caso la probabilidad de que sea casualidad es menor al 5%"*

**Para el grafo (slide 16):**
- Señala físicamente el corredor del Golfo en el grafo circular
- La analogía de "se mueven juntos" es clave — úsala

**Para el PCA (slide 17):**
- La frase clave: *"No importa entender el algoritmo — lo que importa es que los puntos rojos se agrupan. Eso nos dice que estos estados comparten una historia."*
- Señala explícitamente que los rojos están a la derecha y los verdes a la izquierda

**Tiempo de respaldo:**
Si vas adelantado: profundiza en el slide 14 (gobierno vs satélite)
Si vas atrasado: abrevia el slide 18 (anonimización) a 10 segundos: *"También aplicamos técnicas de privacidad en los datos municipales — esto está documentado en el reporte."*
