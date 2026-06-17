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

## 5. Hallazgos Clave / Insights
1. Provincias con mayor prevalencia de anemia.  
2. Grupos de edad más afectados en el periodo.  
3. Tendencia temporal: evolución de la anemia en 10 años.  
4. Establecimientos con más casos reportados.  

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
