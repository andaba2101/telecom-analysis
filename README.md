# telecom-analysis
sprint7-final-project

# Objetivo del proyecto

Como analista de datos en ConnectaTel, una empresa de telecomunicaciones con operaciones en México y Colombia, el equipo de trabajo debe entregar un reporte para entender cómo los clientes usan realmente los servicios móviles (llamadas y mensajes). El objetivo es identificar patrones de uso, detectar comportamientos atípicos y comprender qué segmentos de clientes muestran necesidades diferenciadas, con el fin de optimizar la oferta comercial y mejorar la experiencia del usuario cumpliendo a su vez con:

- Integrar y limpiar bases de datos provenientes de tres fuentes distintas.
- Aplicar técnicas de validación, estandarización de tipos de datos y detección de valores inconsistentes.
- Construir un perfil estadístico del uso (llamadas y mensajes) por cliente y por segmentos demográficos.
- Detectar outliers y comportamientos atípicos mediante métodos estadísticos y visuales.
- Crear segmentaciones de clientes basadas en edad, país y comportamiento de uso.
- Visualizar diferencias entre segmentos y extraer insights comerciales relevantes.
- Documentar todo el proceso en un Jupyter Notebook, junto con un README reproducible para subirlo a GitHub.

# Datasets utilizados

Para ello, se trabajó con tres fuentes de datos:

[plans.csv](https://drive.google.com/uc?export=download&id=17Mkcs9rRWwiC_gaqVBYuFieON7s9v7Bn): los planes actuales (precio, minutos incluidos, GB incluidos, costo por extra).
[users_latam.csv](https://drive.google.com/uc?export=download&id=17wuqxalUsUnw9PXvCN2_UaAz6xeS9B0T): información de clientes con edad, ciudad, fecha de registro, plan contratado.
[usage.csv](https://drive.google.com/uc?export=download&id=11T8MQf-ouxJu9tia4F8aNpY7M_fb9O4h): el detalle de uso real: llamadas (duración) y mensajes (longitud).

Se exploraron, limpiaron y analizaron estas bases de datos para construir una visión clara, confiable y accionable sobre el comportamiento de uso de los clientes y cómo varía entre diferentes grupos de usuarios.


# Etapas del análisis realizadas

Paso	Acción	Resultado para el negocio
1. Cargar y explorar:	Cargar y explorar plans, users_latam, usage.	Visión clara de la estructura y tipos de columna de cada dataset.
2. Identificación de problemas de calidad	Contar nulos, detectar sentinels, revisar fechas fuera de rango.	Lista priorizada de problemas que pueden sesgar decisiones.
3. Limpieza básica:	Reemplazar sentinels, convertir fechas, imputar o marcar NA según reglas.	Datos consistentes y listos para análisis estadístico.
4. Summary statistics:	Revisar las medidas clave en variables categóricas y numéricas.	Medidas clave (media, mediana, percentiles) que muestran el comportamiento típico y extremo
5. Visualización & outliers:	Creación de histogramas y boxplots.	Visualización de sesgos, patrones de usuarios o datos atípicos.
6. Segmentación:	Crear segmentaciones basadas en reglas claras; visualizar proporciones con countplots.	Segmentos accionables que permiten diseñar ofertas, campañas y migraciones de plan.
7. Insight ejecutivo:	Redactar conclusiones y recomendaciones comerciales basadas en los pasos anteriores.	Responder a las preguntas del negocio y proponer acciones concretas.
8. Publicación:	Subir tu notebook + README a GitHub.	Entrega reproducible para revisión y ejecución por stakeholders.


# Cómo ejecutar el notebook
- Abrirlo en Google Colab
- Si se desea de pueden cargar los datasets manualmente descargando los archivos desde los links anexados inicialmente o simplemente ejecutar las lineas mencionadas



# Guía breve de reproducción
- Para validar la calidad general de un dataset antes de analizarlo, revisar tipos de datos, rangos válidos y valores fuera de lógica. Un dataset puede estar completo, pero aún así contener valores imposibles (rangos incorrectos o tipos mal asignados) que afectan cualquier análisis.

- Para identificar la forma de una distribución (normal, sesgada, uniforme), generar histogramas y comparar mean vs. median puesto que los histogramas muestran la forma real de la distribución, y comparar mean vs median revela si hay sesgo.

- Para detectar valores faltantes, sentinels y datos inconsistentes, usar .isna(), .isin() para buscar valores como -999, “NA”, “?”, y validar reglas lógicas del dataset esto porque los errores no siempre son NaN: también aparecen como códigos especiales o valores imposibles que deben capturarse con reglas.

- Para identificar outliers de forma estadística, calcular el IQR y contrastarlo con boxplots. El método IQR es el estándar para detectar valores atípicos y los boxplots permiten validarlos visualmente.

- El flujo de trabajo correcto para este proyecto fue:

Cargar → Explorar → Detectar problemas → Limpiar → Calcular estadísticas → Visualizar → Detectar outliers → Segmentar → Generar insights → Publicar en GitHub

Sigue el orden lógico del análisis: primero entender y limpiar los datos, luego analizarlos, obtener insights y finalmente documentar y publicar el trabajo.
