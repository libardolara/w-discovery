# Comenzando a usar Watson Discovery

El Servicio Watson Discovery permite extraer valor de tu información, al convertir, normalizar y enriquecerla. Utiliza una consulta simple para explorar tus datos y obtener insights ocultos en tu información no estructurada, así como embeber estas capacidades directo en tus aplicaciones.

## Componentes Incluidos
* [Watson Discovery](https://cloud.ibm.com/catalog/services/watson-studio): Watson Studio es una herramienta end-to-end que permite desarrollar modelos de machine learning y deep learning combinando los principales proyectos Open Source y herramientas propias de IBM en la nube.
* [Jupyter Notebook](http://jupyter.org/): Es una aplicación web Open Source que le permite crear y compartir documentos que contienen código en vivo, ecuaciones, visualizaciones y texto narrativo.

# Prerequisitos
* Cuenta activa de [IBM Cloud](https://cloud.ibm.com)

# Paso a Paso

## 1. Clonar el repo

Descarga o clona el repositorio `watson-studio` localmente. 
En una terminal, puedes ejecutar:

```
$ git clone https://github.com/libardolara/watson-studio
```

## 2. Crear los servicios en IBM Cloud
* Crea el servicio [Watson Discovery](https://cloud.ibm.com/catalog/services/discovery)

## 3. Cargar la información
* Haz click e el boton _Launch Tool_ o _Lanzar Herramienta_
* Haz click en el boton **Upload your own Data** para crear una nueva colección. 
* Llama a la colección `workshop-collection`y escoge el idioma **Spanish**
* Carga un documento de ejemplo, utilice el archivo **airbnb2.json**. Para esto es suficiente con arrastrarlo hacia la herramienta web del Watson Discovery.
* Haz click en el boton **Configure Data** para modificar la configuración con que el Watson Discovery lee, almacena y enriquece los documentos. Para mayor información revisa la documentación de [Smart Document Understanding](https://cloud.ibm.com/docs/services/discovery?topic=discovery-sdu)
* Nota que la pestaña **Identify Fields** es usada para convertir y normalizar los documentos de tal forma que se puedan identificar los campos que puedan venir en la data no estructurada. Para nuestro caso los documentos son `JSON`y son considerados data estructurada por lo cual no trabajaremos con esta pestaña.
* En la pestaña **Manage Fields** seleccionamos los campos que queremos que sean indexados en el Watson Discovery. Campos que no tengan información util los puedes de-seleccionar. Para nuestro ejercisio vamos a dejar todos los campos.
* En la pestaña **Enrich Fields** vamos a seleccionar que campos y que enriquiecimientos utilizar. Para mayor información revisa la documentación de como [Agregar Enriquecimientos](https://cloud.ibm.com/docs/services/discovery?topic=discovery-configservice#adding-enrichments)
* Borra el campo _Text_, como campo ha ser enriquecido.
* Selecciona el campo `comments`en la lista **Add a Field to Enrich**
* Haz click en el link _+ Add Enrichment_
* Selecciona los enriquecimientos **Entity Extraction** y **Sentiment Analysis**
* Finalmente haz click en el boton **Apply changes to collection** para que los cambios se apliquen sobre los documentos ya cargados y los que vamos a cargar.
* Arrastra los demas documentos ha la ventana emergente que te permite agregar nuevos documentos a la colección.
* Espera a que los 60 documentes sean agregados y procesando.

## 4. Realizar Consultas
* Haz click en el link _Build your own query_
* Haz click en la sección **Search for Documents**
* En la pestaña _Use natural language_ has una consulta como `apartamanetos en manhattan con vista` y haz click en el boton **Run query**
* Observa los resultados en la pestaña **Summary** y en la pestaña **JSON**
* Haz click en la sección **Filter which documents you query**
* Selecciona _enriched_comments.sentiment.document.label_ 



