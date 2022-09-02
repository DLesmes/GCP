

# Definitions

* Sistema legacy (sistema heredado)
> Un  es un sistema, tecnología o aplicación de software antiguo o desactualizado que sigue en uso dentro de una organización porque sigue desempeñando las funciones para las que fue diseñado"

* Big Query:
> Es un servicio serverless totalmente escalable que permite trabajar con petabytes de información y lo más importante permite separar el cómputo del procesamiento.

* Pub-Sub:
> Permite trabajar a través de tópicos, esos tópicos permiten conectarnos con distintas fuentes de información y obtener éstos elementos en tiempo real. Éstos elementos pueden llevarse hasta un DataFlow para poder hacer filtrado, poder hacer ordenamiento de éstos registros y luego cargarlos en Big Query.

* DataFlow:
> Es un servicio de extracción, transformación y carga de datos que puede funcionar tanto Batch como Near Real Time. Éste servicio permite trabajar en base a jobs y éstos pueden ser a través de un Template y ya vienen pre configurados distintos Templates.

* Data Catalog:
> Es un servicio totalmente escalable que permite administrar la metadata que tu tienes en tu organización. Ésta metadata recuerda que se genera desde los procesos de ingesta hasta los repositorios de datos, por lo tanto es bastante útil que puedas conectar tus sistemas y poder almacenar ésta data para que distintos usuarios dentro de tu organización puedan conocer cual es la información que tienes cargado en Google Cloud.

* Vertex AI:
> Almacena todas las funcionalidades para poder hacer y crear Datasets, hacer ingesta, hacer entrenamiento, deployement de éstos modelos de una forma asistida con AutoML Tables o de una forma programática con Jupyter Notebook. Éstas dos opciones están disponibles en Vertex AI.

* Vision:
> Nos permite resolver una serie de casos de uso enfocados en la detección tanto de video como de imégenes para detectar elementos.

* Document AI:
> Permite tomar información no estructurada desde distintos formularios, PDF, correo electrónico, y poder extraer ésta información para poder procesarla de una forma ordenada y encontrar insight de éstos textos.

* Speech to Text:
> Permite resolver casos de uso donde tengo audio, y ese audio necesito hacer una transcripción a texto para después analizarlo con los servicios de lenguaje natural.

* Natural Lenguage:
> Permite analizar, extraer sentimientos, extraer entidades y todo eso gracias al análisis semántico de información de texto.

* Cloud Dataflow
> Es un servicio de procesamiento de datos totalmente administrado, que simplifica el desarrollo y la administración de flujos y pipelines.
> * Acelera el desarrollo de streaming y bach
> * Gestion y operaciones simplificadas
> * Construir sobre una base para machine learning
> * Posee templates que ya tienen armado un flujo de trabajo con determinado origen y determinado destino.

* Tipos de pipelines:
> * Tiempo real: todos los datos van siendo procesados en el momento (Pub/Sub – Dataflow)
> * Scheduled Batch: primero se acumulan los datos, y luego se programa el procesamiento de los mismos, generalmente en las noches (Dataflow)
> * Triggered Batch: cuando tengo determinadas señales en mis datos, eso dispara o activan un flujo de ingesta de datos (Cloud Functions)

# Google Cloud Pub/Sub

Mensajería impulsada por eventos para la ingesta de datos y el movimiento de los mismos.

* Ingestion y entrega de eventos escalables/ persistentes.
* Patrón de publicación.
* Servicio global.
* Integrado con otras herramientas.

