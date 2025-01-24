# Proyecto_bioinformatica_diversidad_microbiana
Este repositorio contiene un script diseñado para analizar la diversidad microbiana de suelos bajo diferentes condiciones y tratamientos. El análisis se centra en determinar cómo la presencia o ausencia de cultivos de trigo afecta la diversidad microbiana, utilizando datos obtenidos de múltiples muestras de suelo tratadas experimentalmente.
El script está desarrollado en un Jupyter Notebook y requiere un entorno conda específico para su ejecución. El archivo `ambiente_proyecto_zeballos.yml` incluido en el repositorio detalla las dependencias necesarias. Para configurarlo puede seguir los siguientes pasos: El nombre del entorno es `proyecto_final`. Por lo que, en la terminal en el ambiente (base), luego de clonar el respositorio e ingresar al directorio "Proyecto_bioinformatica", usted puede ejecutar el comando: `conda env create -f ambiente_proyecto_zeballos.yaml`. Ya con el ambiente conda creado, debe activarlo con el comando `conda activate proyecto_final`.
Una vez dentro del ambiente, puede correr todos los códigos en VSCode con el código `code ambiente_proyecto_zeballos.yaml` o puede abrir todo el directorio en VSCode con el comando `code .` (debe estar dentro del directorio "Proyecto_bioinformatica") El kernel debería estar instalado, pero tal vez no está registrado, si es que no lo está puede registrarlo con el comando `python -m ipykernel install --user --name=proyecto_final --display-name "Python (proyecto_final)"`

#### Los Datos
El análisis utiliza datos en formato .xlsx que son proprocionados en el repositorio bajo el nombre `Datos_proyecto.xlsx`, pero si es que hay problemas al correr Excel, entonces el repositorio también incluye los datos en formato .csv bajo el nombre `Datos_proyecto.csv`. Estos datos contienen mediciones de análisis de diversidad alfa de microoranismos en muestras de suelos sometidos a diferentes condiciones llamadas claves (CTB, CTB-N, PBB, PBB-N, PBR y PBR-N) y tratamientos (con trigo y sin trigo).

Las muestras de suelo se agruparon y analizaron según estos factores, permitiendo evaluar los efectos del cultivo en la composición microbiana.

#### El script
El script realiza las siguientes tareas:
- Importar paquetes necesarios para el análisis
- Cargar y ordenar datos para un análisis más sencillo y rápido
- Pruebas estadísticas:
  - Estadística descriptiva agrupada según claves y tratamientos
  - Determinación de la normalidad de los datos con la prueba de Shapiro-Wilk
  - ANOVA para datos con distribución normal.
  - Análisis post hoc con la prueba de Tukey para identificar diferencias significativas entre tratamientos
- Visualización generando gráficos
 
#### Resultados
A pesar de tener celdas unidas en la base de datos original, el script fácilmente la ordena para no tener "casillas vacías" NaN. La prueba de Shapiro muestra que la mayoría de los datos presentan una distribución normal, ya que solo algunos datos que podrían considerarse valores atípicos son los que se muestran no normales.
Las pruebas de ANOVA muestran que el No. de Secuencias y las OTUs observadas no se ven afectadas por lo que son las claves, los tratamientos y el conjunto de clave:tratamiento. Sin embargo, la Riqueza si parece ser un poco afectada, por lo que entra al análsis post-hoc conla prueba de Tukey. Es en este análisis donde vemos que no hay diferencias significativas a pesar de que la ANOVA nos decía que si. Todos los gráficos ayudan en la visualización de los resultados.
En resumen, este script permite explorar, analizar y visualizar datos de diversidad microbiana de manera estadísticamente robusta, proporcionando una herramienta un tanto simple, pero valiosa para estudios otros estudios de ecología del suelo
