# Proyecto: Análisis de Negocios y Reseñas

![Portada del Proyecto](images/logo.png)

## Descripción del Proyecto

Este proyecto tiene como objetivo analizar los datos de negocios y sus reseñas para descubrir patrones y generar insights valiosos para la toma de decisiones de los propietarios de negocios. Utilizando un conjunto de datos de negocios y reseñas, se realizarán varias preguntas de investigación para explorar las interacciones entre los clientes y los negocios, así como las características que influyen en las calificaciones y la cantidad de reseñas.


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


# Exploración y Análisis de Datos de Negocios

## Preguntas de Investigación Iniciales

### 1. **¿Los negocios que cuentan con servicios adicionales como WiFi, TV, estacionamiento, entre otros, tienden a recibir mejores calificaciones de los clientes?**
   - **Variables clave**: 
     - `WiFi`, `HasTV`, `BusinessParking`, `OutdoorSeating`, `Alcohol`, `RestaurantsReservations`
     - `stars` (calificación promedio).
   - **Objetivo**: 
     - Determinar si los negocios que ofrecen servicios adicionales (como WiFi, TV, estacionamiento, etc.) reciben mejores calificaciones, lo cual puede sugerir que estos servicios aumentan la satisfacción del cliente.
   - **Análisis**: 
     - Se realizaron gráficos de boxplot para comparar las calificaciones promedio de negocios con y sin estos servicios adicionales. También se analizaron correlaciones entre las facilidades y la calificación promedio.

### 2. **¿Cómo varían las calificaciones y la cantidad de reseñas dependiendo de la ubicación geográfica del negocio?**
   - **Variables clave**: 
     - `city`, `state`, `latitude`, `longitude`, `stars` (calificación promedio), `review_count` (número de reseñas).
   - **Objetivo**: 
     - Identificar si la ubicación geográfica del negocio (grandes ciudades o zonas rurales) tiene un impacto en las calificaciones y la cantidad de reseñas que recibe un negocio.
   - **Análisis**: 
     - Se generó un mapa coroplético para visualizar la distribución geográfica de las reseñas y las calificaciones. Se analizaron los porcentajes de reseñas con calificación mayor a 4 por estado, destacando cuáles estados tienden a tener una mejor satisfacción general de los clientes.

### 3. **¿Los negocios con más años de operación tienden a tener calificaciones más estables o superiores en comparación con los negocios más nuevos?**
   - **Variables clave**: 
     - `year_opened`, `stars`, `review_count`, `is_open`.
   - **Objetivo**: 
     - Evaluar si los negocios más antiguos (con más años de operación) tienen calificaciones más estables o superiores a lo largo del tiempo en comparación con los negocios más nuevos.
   - **Análisis**: 
     - Se realizaron gráficos de línea que comparan la evolución de las calificaciones promedio a lo largo de los años para negocios nuevos (desde 2018) y antiguos. Además, se analizaron las tendencias de reseñas y calificaciones para cada grupo de negocios.

### 4. **¿Qué categorías de negocios tienen un mayor porcentaje de locales cerrados y cómo ha sido el comportamiento de las calificaciones de estas categorías en los últimos años?**
   - **Variables clave**: 
     - `categories` (categorías de negocio), `is_open`, `stars`, `review_count`.
   - **Objetivo**: 
     - Identificar las categorías de negocio que tienen un mayor porcentaje de locales cerrados y analizar cómo han cambiado sus calificaciones a lo largo del tiempo, en comparación con los negocios que permanecen abiertos.
   - **Análisis**: 
     - Se realizó un gráfico de barras que muestra el porcentaje de cierre por categoría de negocio. También se creó un gráfico de línea para visualizar la evolución de las calificaciones promedio de negocios cerrados versus abiertos en los últimos años.

### 5. **¿Qué factores contribuyen a que una reseña sea considerada "útil" por otros usuarios?**
   - **Variables clave**: 
     - `useful` (votos útiles en la reseña), `cool`, `funny`, `text_length` (longitud de la reseña).
   - **Objetivo**: 
     - Investigar los factores que influyen en que una reseña sea votada como "útil" por otros usuarios, analizando características como la longitud de la reseña o el tipo de contenido.
   - **Análisis**: 
     - Se generó un gráfico de dispersión para analizar la relación entre la longitud de las reseñas y la cantidad de votos útiles recibidos. También se exploraron las correlaciones entre las calificaciones, la longitud y los votos útiles de las reseñas.

---

## Metodología de Análisis

1. **Limpieza y preparación de los datos**:
   - Se eliminaron valores faltantes y se imputaron datos cuando fue necesario.
   - Se transformaron los atributos booleanos en formato adecuado para el análisis.
   - Se generaron nuevas variables como `year_opened` para categorizar los negocios según su antigüedad.

2. **Análisis de correlaciones**:
   - Se utilizaron métodos de correlación para investigar la relación entre las calificaciones, el número de reseñas y los atributos clave del negocio, como la accesibilidad, los servicios adicionales, y la ubicación.

3. **Visualización de los datos**:
   - Se crearon gráficos de correlaciones, mapas coropléticos y gráficos de barras para representar cómo la ubicación geográfica, los años de operación, y las categorías de los negocios influyen en las calificaciones y las reseñas.
   - Se utilizaron gráficos de dispersión para analizar la relación entre la longitud de las reseñas y los votos útiles.

4. **Feature Scaling**:
   - Se aplicó **estandarización** o **normalización** a las variables numéricas como `review_count`, `stars`, `useful` para asegurar que las variables estén en la misma escala y evitar sesgos en el análisis predictivo.

5. **Modelado predictivo**:
   - Se implementó un modelo de clasificación utilizando métodos de filtro como **Ganancia de Información** para predecir si una reseña será considerada "útil" basándose en las características del negocio y la reseña.

---

## Resultados Esperados

1. **Servicios adicionales y calificaciones**: 
   - Los negocios que ofrecen facilidades adicionales como WiFi, TV y estacionamiento deberían mostrar una tendencia hacia mejores calificaciones, lo cual sugiere que estas facilidades influyen positivamente en la experiencia del cliente.

2. **Ubicación y reseñas**: 
   - Los negocios en grandes ciudades y áreas turísticas tienden a recibir más reseñas y calificaciones más altas en comparación con aquellos en zonas rurales o menos pobladas.

3. **Años de operación y calificaciones**: 
   - Los negocios más antiguos probablemente tengan calificaciones más estables a lo largo del tiempo, mientras que los negocios nuevos podrían mostrar variaciones más marcadas en sus primeras reseñas.

4. **Categorías con más cierres**: 
   - Se espera que las categorías como **Restaurantes** y **Nightlife** tengan un mayor porcentaje de locales cerrados, posiblemente debido a las altas exigencias de la competencia. También se espera que estas categorías tengan variaciones más notables en sus calificaciones a lo largo del tiempo.

5. **Factores de utilidad en las reseñas**: 
   - Reseñas más largas y detalladas tienden a recibir más votos útiles, lo que sugiere que el contenido y la profundidad de la reseña son factores clave en cómo los usuarios perciben su utilidad.

---

Este análisis proporcionará **insights clave** para los propietarios de negocios, ayudándolos a optimizar sus servicios y mejorar la experiencia del cliente, basada en los patrones de reseñas y calificaciones.
