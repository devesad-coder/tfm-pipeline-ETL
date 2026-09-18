# TFM-pipeline-ETL

Este repositorio contiene el código fuente desarrollado para el Trabajo de Fin de Máster (TFM) de Data Engineering. El proyecto implementa una arquitectura Medallón (Bronce, Plata, Oro) para automatizar la ingesta, transformación y modelado de datos de eventos deportivos de StatsBomb.

## Arquitectura y tecnologías
* **Capa Bronce (Data Lake):** Extracción masiva de JSONs dinámicos con `glob` e ingesta cruda en **MongoDB Atlas** (NoSQL).
* **Capa Plata (Transform & ML):** Aplanamiento de datos y Feature Engineering usando **Python (Pandas)**. Detección de anomalías y talento mediante el algoritmo *Isolation Forest* de **Scikit-Learn**.
* **Capa Oro (Data Warehouse):** Carga automatizada de tablas maestras estructuradas en **Snowflake** mediante `write_pandas` para su posterior consumo en **Tableau**.

## Configuración del entorno
Para ejecutar los scripts, es necesario configurar las credenciales de base de datos. Se incluye un archivo `example.env` con la estructura requerida para las conexiones a Snowflake y MongoDB Atlas.

*Nota: En cumplimiento con la licencia de StatsBomb y las buenas prácticas de Data Engineering, los archivos de datos crudos (.json) no se distribuyen en este repositorio. Para reproducir este entorno, es necesario descargar los datos desde el repositorio oficial de StatsBomb y alojarlos en el directorio de entrada local.* https://github.com/hudl/open-data

**Dashboard final:** Ver visualización interactiva en Tableau Public 
https://public.tableau.com/app/profile/david.devesa.p.rez/viz/Visualizacion_scouting/REDESDEPASES
