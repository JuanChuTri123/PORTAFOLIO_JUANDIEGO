# Proyecto6_Anemia_Cusco - 2010–2020

**“Analizamos el perfil académico de los egresados de la UNE para identificar patrones de rendimiento y brechas institucionales.”**

---

## 1. Problema de Negocio
La Universidad Nacional de Educación enfrenta el reto de comprender mejor el comportamiento académico de sus egresados entre 2020 y 2025.
Los datos estaban en bruto y con inconsistencias, lo que dificultaba responder preguntas clave:
¿Qué facultades concentran más egresados?
¿Cómo varía el rendimiento académico según sede y nivel de estudio?
¿Existen brechas de género en las facultades?
¿Qué programas muestran mejores promedios finales?
¿Cuánto tiempo tardan los estudiantes en egresar según matrícula y trámite? 

---

## 2. Datos
|Titulo|Detalle|
|--|--|
|**Fuente**| Plataforma Nacional de Datos Abiertos - Perú|
|**Tamaño** |11678 filas, 17 columnas | 
|**Descripción**| Información de egresados UNE: facultad, nivel académico, tipo de estudio, año de matrícula, año de egreso, créditos acumulados, promedio final, sede, sexo.  |
|**Diccionario de datos** |Archivo excel proporcionado por la página de Datos Abiertos, para saber la descripción de cada columna de los datos que usaremos en este proyecto.|

## 3. Herramientas y Tecnologías
- Python + Pandas (ETL): Limpieza, transformación y creación del dataset df_limpio.
- SQL Server (SSMS): Carga del dataset en la base de datos Egresados_UNE y análisis profundo con consultas SQL.
- GitHub: Portafolio y control de versiones del proyecto.
- Power BI (opcional): Visualización de KPIs y dashboards interactivos.

## 4. Proceso / Metodología
1. **Limpieza**  
   - Se detectaron valores vacíos o null, según análisis lo reemplazamos con "No especificado"
   - Se eliminó columnas innecesarias o que no aportarían valor en el análisis ni en la limpieza como la columna fecha corte, y la modalidad la cual en todas es "presencial"
   - Se verificó si hay registros duplicados con respecto a todas la columnas, no hubo duplicación
   - Proceso de eliminacion de duplicación de DNI, se detectó muchos duplicados, de grupos de (2,4 y 9) repetidos, se hizo un análisis preciso y correcto para reemplazar valores y eliminar si era necesario.
   - Se hizo la transformación de todas las columnas, ya sea desde nombrar los encabezados hasta reemplazar valores que están mal escritos o sucios, como en la columna Facultad la mayoría de valores tenían digitos irreconocibles los cuales fueron reemplazados y mejorados
   - Las fechas y todo lo relacionado estaban mal, ya sea por datos sucios o datos que no coincidían, como el año de egreso con la fecha de egreso, para ello se extrajo el año de la fecha de egreso como una nueva columna
   - Los semestres se compararon también con la fecha de egreso, casi todas no coincidian, por ello se creó una columna personalizada para los semestres
   - La columna Tipo de estudio, tenían valores con caractéres sucios y desconocidos, como no se podría identificar muy bien los valores, notamos que todos los datos que estaban sucios comenzaban con "complementación", asi que todos los datos se agruparon con esa categoría.
2. **Carga en SQL Server**  
- Inserción en tabla EgresadosUNE.
- Validación de tipos de datos y claves.

3. **Análisis SQL**  
- Distribución de egresados por tipo de estudio.
- Brechas de género por facultad.
- Ranking de programas con mayor promedio final.
- Comparación de duración de estudios por sede.
- Segmentación de alumnos (nuevos, recurrentes, leales).
- Relación entre año de trámite y año de egreso.

