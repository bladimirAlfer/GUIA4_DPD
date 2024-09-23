# Proyecto: Análisis de Negocios y Reseñas

![Portada del Proyecto](images/logo.png)

## Descripción del Proyecto

Este proyecto tiene como objetivo principal el análisis de la relación entre los negocios y las reseñas de usuarios, utilizando dos datasets principales: uno que contiene información sobre los negocios y otro con reseñas. La idea es explorar los patrones y las tendencias que influyen en las calificaciones, el número de reseñas, la utilidad de las reseñas y otros factores, como la ubicación, las categorías del negocio y los horarios de operación.

## Objetivos

1. **Comprender los factores clave que influyen en la cantidad y calidad de las reseñas de un negocio.**
2. **Identificar patrones de calificación promedio por categorías de negocio, horas de operación y ubicación geográfica.**
3. **Explorar la relación entre los atributos del negocio y las reseñas útiles, divertidas o "cool".**
4. **Analizar la relación entre las horas de operación y la cantidad de reseñas.**

## Dataset

![Dataset](images/datasetyelp.png)

### Datos de Negocios

El primer dataset contiene información detallada sobre los negocios. Este dataset tiene un total de **150,346 registros** y **14 columnas**. Las variables clave de este dataset son:

- **business_id** (string): Identificador único del negocio.
- **name** (string): Nombre del negocio.
- **address** (string): Dirección del negocio.
- **city** (string): Ciudad donde está ubicado el negocio.
- **state** (string): Estado del negocio.
- **postal_code** (string): Código postal del negocio.
- **latitude** (float): Latitud de la ubicación geográfica del negocio.
- **longitude** (float): Longitud de la ubicación geográfica del negocio.
- **stars** (float): Calificación promedio del negocio basada en las reseñas (valor entre 1 y 5).
- **review_count** (int): Número total de reseñas que ha recibido el negocio.
- **is_open** (int): Indica si el negocio está abierto (1) o cerrado (0).
- **attributes** (object): Atributos adicionales del negocio (comida para llevar, estacionamiento, etc.).
- **categories** (object): Categorías a las que pertenece el negocio (por ejemplo, restaurantes, bares, etc.).
- **hours** (object): Horarios de apertura y cierre de los negocios por día de la semana.

### Datos de Reseñas

El segundo dataset contiene información sobre las reseñas de los usuarios. Este dataset cuenta con **500,000 registros** y **9 columnas**. Las variables clave de este dataset son:

- **review_id** (string): Identificador único de la reseña.
- **user_id** (string): Identificador único del usuario que escribió la reseña.
- **business_id** (string): Identificador único del negocio al que corresponde la reseña (relacionado con el dataset de negocios).
- **stars** (int): Calificación otorgada en la reseña (valor entre 1 y 5).
- **useful** (int): Número de votos indicando cuán útil fue la reseña.
- **funny** (int): Número de votos indicando cuán divertida fue la reseña.
- **cool** (int): Número de votos indicando cuán "cool" fue la reseña.
- **text** (string): Texto completo de la reseña.
- **date** (string): Fecha en la que se escribió la reseña.

## Variables Importantes

- **Variables geográficas**: `city`, `state`, `latitude`, `longitude`.
- **Variables de negocio**: `stars`, `review_count`, `categories`, `hours`.
- **Variables de reseñas**: `stars`, `useful`, `funny`, `cool`, `text`, `date`.

## Exploración y Análisis de Datos

### Preguntas de Investigación Iniciales

1. **¿Cómo varía el número de reseñas según las categorías de los negocios?**
   - Se explorará si ciertos tipos de negocios (Restaurantes, Bares, Shopping, etc.) tienden a recibir más reseñas que otros.
   - Variables a utilizar: `categories`, `review_count`.

2. **¿Existe alguna relación entre las horas de operación de un negocio y la cantidad de reseñas que recibe?**
   - Se investigará si los negocios que están abiertos por más horas o que abren en días específicos (fines de semana, por ejemplo) tienden a recibir más reseñas.
   - Variables a utilizar: `hours`, `review_count`, `stars`.

3. **¿Qué atributos de los negocios influyen más en la utilidad de las reseñas?**
   - Se analizarán atributos como `RestaurantsTakeOut`, `WiFi`, y `BusinessParking` para entender cómo estos factores influyen en las reseñas consideradas útiles.
   - Variables a utilizar: `attributes`, `useful`, `stars`.

4. **¿Cuáles son los patrones geográficos en las reseñas y calificaciones de los negocios?**
   - Se buscará identificar patrones geográficos en la calificación de los negocios y en la cantidad de reseñas por ubicación.
   - Variables a utilizar: `city`, `state`, `latitude`, `longitude`, `stars`, `review_count`.

5. **¿Cómo influyen los días de la semana en las calificaciones de las reseñas?**
   - Se analizará si existen variaciones en las calificaciones de los clientes dependiendo del día de la semana y las horas de operación.
   - Variables a utilizar: `Monday_hours`, `Tuesday_hours`, `stars`, `useful`, `funny`.

### Metodología de Análisis

1. **Limpieza y preparación de los datos:**
   - Se revisarán y limpiarán las variables de horas y atributos para asegurar su correcto análisis.
   - Se normalizarán las horas de operación para que puedan ser utilizadas en el análisis.

2. **Análisis de correlaciones:**
   - Se utilizarán métodos de correlación para investigar las relaciones entre las variables (por ejemplo, si los negocios con mayor calificación tienden a recibir más reseñas útiles).

3. **Visualización de los datos:**
   - Se crearán gráficos para visualizar cómo las diferentes variables afectan el número y tipo de reseñas.
   - Mapas de calor para representar la relación entre las reseñas y las horas de operación o la ubicación.

4. **Feature Scaling:**
   - Se aplicará `standardization` o `normalization` en variables como `review_count`, `stars`, `useful` para mejorar la interpretación en los modelos de predicción.

5. **Modelado predictivo:**
   - Se implementará un modelo de clasificación para predecir qué reseñas serán útiles o "cool" basándose en los atributos del negocio y las características de la reseña.

## Resultados Esperados

- Identificación de los atributos de los negocios que influyen en obtener reseñas útiles o con buenas calificaciones.
- Descubrimiento de patrones de horarios que favorezcan más interacción de los usuarios.
- Generación de insights para la optimización de los horarios de operación y atributos que mejoran la satisfacción del cliente.

Este análisis permitirá comprender mejor las dinámicas entre los negocios y las reseñas, ayudando a los propietarios a optimizar la operación y a generar mejores experiencias para los clientes.
