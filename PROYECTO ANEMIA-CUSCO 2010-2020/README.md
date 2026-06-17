# Proyecto6_Anemia_Cusco - 2010–2020


*One-liner*: **“Identificamos patrones de anemia en Cusco para orientar políticas de salud pública.”**

---

## 1. Problema de Negocio
El Gobierno Regional de Cusco enfrenta una alta incidencia de anemia en niños y adolescentes entre 2010 y 2020.  
Los datos estaban dispersos y con errores de calidad, lo que dificultaba responder preguntas clave:  
- ¿Qué provincias concentran más casos?  
- ¿Qué grupos de edad son los más afectados?  
- ¿La tendencia mejora o empeora con los años?  
- ¿Qué establecimientos requieren mayor apoyo?  

---

## 2. Datos
- **Fuente**: Plataforma Nacional de Datos Abiertos - Perú
- **Link**: https://www.datosabiertos.gob.pe/dataset/casos-de-anemia-por-edades-entre-los-a%C3%B1os-2010-2020-en-la-region-de-cusco
- **Tamaño**: 83413 filas, 14 columnas  
- **Descripción**: Casos de anemia y normales por edad, año, provincia, distrito y establecimiento de salud  
- **Diccionario de datos**: [Data Dictionary - Anemia Cusco 2010-2020](DiccionarioDatos_ANEMIACUSCO.xlsx)

---

## 3. Herramientas y Tecnologías
- Power Query (ETL)  
- Power BI (visualización)  
- GitHub (portafolio y versionado)  

---

## 4. Proceso / Metodología
1. **Limpieza**  
   - Reemplazo de valores nulos en PROVINCIA, DISTRITO, COD_EESS, UBIGEO  
   - Validación de sumas CASOS + NORMAL = TOTAL  
   - Normalización de formatos y tipos de datos
   - Renombramiento de columnas para facilidad lectora
   - Eliminación de columnas que no aportarán valor en este proyecto (Ubigeo, FechaCorte)

2. **Análisis**  
   - Creación de medidas:  
     - Total de casos de anemia
     - Tasa de anemia = Casos anemia / Total Casos
     - Distribución por provincia  (en porcentaje)
     - Provincia con más casos de anemia

3. **Visualización**  
   - Gráficos:  
     - Mapa geográfico por Departamento - Provincia - Distrito 
     - Serie temporal de casos (anemia y sin anemia) (2010–2020)  
     - Gráfico de áreas por edad  
     - Comparación Casos con anemia vs Casos sin anemia, por provincia  
     - Embudo de los 15 distritos con más casos de anemia

---

2. Grupos de edad más afectados en el periodo.  

3. Tendencia temporal: evolución de la anemia en 10 años.  

4. Establecimientos con más casos reportados.  


## 5. Hallazgos Clave / Insights

1. **Provincias con mayor prevalencia de anemia**  
   Según el gráfico de columnas, las provincias con más casos son **Cusco (42,451), La Convención (20,156) y Quispicanchi (16,369)**.  
  En conjunto, estas tres provincias concentran **más del 50% de los casos reportados en la región** (Cusco 27.5%, La Convención 13.0% y Quispicanchi 10.6%).
  Este hallazgo evidencia que la **focalización de recursos y programas de salud pública** debe priorizarse en estas zonas críticas para lograr un mayor impacto en la reducción de la anemia.

2. **Grupos de edad más afectados**  
   El análisis por edad muestra picos de incidencia en los grupos de **6, 12 y 18 años**, con una disminución progresiva en edades mayores.  
   Esto confirma que la anemia afecta principalmente a **niños y adolescentes**, etapas de mayor vulnerabilidad nutricional, lo que sugiere reforzar programas de suplementación y educación alimentaria en estas cohortes.

3. **Tendencia temporal 2010–2020**  
   La serie temporal revela un crecimiento sostenido de casos entre 2010 y 2019, seguido de un **leve descenso hacia 2020**.  
   Este comportamiento podría reflejar el impacto de **políticas de suplementación y campañas de salud** implementadas en los últimos años, aunque la prevalencia sigue siendo alta.

4. **Establecimientos con más casos reportados**  
   El ranking de establecimientos muestra que **10 centros de salud concentran cerca del 20% de los casos de anemia**.  
   Estos puntos focales representan áreas estratégicas para **reforzar la atención primaria y mejorar la capacidad de diagnóstico y tratamiento**.


---

## 6. Recomendaciones / Impacto
- Focalizar recursos en provincias críticas.  
- Programas de prevención en edades más vulnerables.  
- Monitoreo anual para evaluar impacto de políticas.  

---

## 7. Links
- **Dashboard Interactivo**: [Power BI Link]  
- **Código ETL (Power Query)**: `/etl/transformaciones.pq`  
- **Dataset limpio**: `/data/dataset_limpio.csv`  

---

## 8. Cómo ejecutar el proyecto
```bash
1. Clona el repo
2. Abre el archivo .pbix en Power BI
3. Explora el dashboard con los filtros disponibles
