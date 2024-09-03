# Análisis de Datos
Preguntas y respuestas comunes sobre análisis de datos y SQL.

### ¿Qué es un dataset?
Un dataset es una colección de datos, generalmente organizados en forma de tabla con filas y columnas, donde cada fila representa un registro individual y cada columna representa una característica o variable de esos registros.

### ¿Cuál es la diferencia entre datos estructurados y no estructurados?
Los datos estructurados están altamente organizados y tienen un formato predecible (como bases de datos SQL), lo que facilita su análisis. Los datos no estructurados son más desorganizados y pueden incluir formatos como texto libre, videos, imágenes y correos electrónicos, los cuales requieren procesamiento adicional para extraer información útil.

### ¿Qué es un histograma y para qué se utiliza?
Un histograma es un tipo de gráfico de barras que representa la distribución de una variable numérica mediante la agrupación de datos en intervalos. Se utiliza para obtener una vista general de la distribución de los datos, identificar la centralidad, dispersión y la presencia de cualquier sesgo en los datos.

### Explica qué es la limpieza de datos y por qué es importante.
La limpieza de datos implica procesos de detección y corrección (o eliminación) de datos corruptos o inexactos de un dataset. Es crucial porque datos incorrectos o incompletos pueden llevar a conclusiones erróneas y afectar negativamente la calidad de los resultados del análisis.

### ¿Qué es un "outlier" y cómo puede afectar tu análisis?
Un "outlier" es un punto de dato que difiere significativamente de otros datos en un dataset. Puede ser el resultado de un error o de una variación natural. Los outliers pueden afectar el resultado de los análisis estadísticos y los modelos predictivos, distorsionando medias, desviaciones estándar y otras medidas estadísticas.

### ¿Cómo se realiza una regresión lineal y qué interpretas de sus resultados?
Una regresión lineal es un análisis estadístico que intenta modelar la relación entre una variable dependiente y una o más variables independientes especificando una ecuación lineal. De sus resultados, interpretamos el coeficiente para cada variable independiente que indica cómo afecta al valor esperado de la variable dependiente, así como el valor de R-cuadrado que mide qué tan bien los datos se ajustan al modelo.

### ¿Qué son los métodos de clustering y cuáles son algunos ejemplos comunes?
Los métodos de clustering son técnicas de aprendizaje automático no supervisado que agrupan un conjunto de objetos de tal manera que los objetos en el mismo grupo (o cluster) son más similares entre sí que con los de otros grupos. Ejemplos comunes incluyen K-means, clustering jerárquico y DBSCAN.

### Explica qué es el análisis de componentes principales (PCA) y cómo se utiliza en el análisis de datos.
El análisis de componentes principales (PCA) es una técnica de reducción de dimensionalidad que transforma un conjunto de variables posiblemente correlacionadas en un conjunto más pequeño de variables no correlacionadas llamadas componentes principales. PCA se utiliza para simplificar la complejidad en conjuntos de datos de alta dimensión preservando la mayor cantidad de información posible.

### ¿Qué es el aprendizaje supervisado y cómo difiere del no supervisado?
El aprendizaje supervisado es una técnica de machine learning que aprende un modelo a partir de datos de entrada etiquetados, intentando predecir salidas para nuevas instancias basándose en ese aprendizaje. En contraste, el aprendizaje no supervisado trabaja con datos no etiquetados y se utiliza para encontrar patrones o estructuras intrínsecas en los datos sin instrucciones explícitas sobre qué es lo que se busca.

### ¿Cómo se utiliza la validación cruzada en la construcción de modelos predictivos y cuál es su beneficio principal?
La validación cruzada es un método de evaluación de modelos que implica dividir un conjunto de datos en subconjuntos múltiples y realizar el entrenamiento y la prueba en estos de manera iterativa. El beneficio principal de la validación cruzada es que proporciona una medida robusta del rendimiento del modelo y ayuda a evitar el sobreajuste, asegurando que el modelo sea generalizable a nuevos datos.

# Preguntas Básicas de SQL

### ¿Cómo realizas subconjuntos o filtras datos en SQL?
Para crear subconjuntos o filtrar datos en SQL, utilizo la cláusula `WHERE`. Esta cláusula permite especificar condiciones que las filas deben cumplir para ser seleccionadas. Por ejemplo, `SELECT * FROM clientes WHERE edad > 30;` selecciona todas las filas en la tabla `clientes` donde la columna `edad` es mayor que 30.

### ¿Cuál es la diferencia entre las cláusulas WHERE y HAVING en SQL?
La diferencia principal entre `WHERE` y `HAVING` en SQL es que `WHERE` se utiliza para filtrar filas antes de que se realicen agregaciones de grupo, mientras que `HAVING` se utiliza para filtrar grupos después de que se han formado y calculado las funciones agregadas. Por ejemplo, `WHERE` se usa para filtrar registros individuales, como `SELECT * FROM ventas WHERE cantidad > 2;`. En cambio, `HAVING` se usa en consultas que involucran funciones agregadas, como `SELECT vendedor_id, COUNT(*) FROM ventas GROUP BY vendedor_id HAVING COUNT(*) > 10;`, donde se filtran los vendedores con más de 10 ventas.

### ¿Cómo escribes un procedimiento almacenado en SQL?
Un procedimiento almacenado en SQL es un conjunto de instrucciones SQL que puedes definir y almacenar en la base de datos para ejecutarlas múltiples veces. Aquí te muestro un ejemplo básico de cómo escribir uno en SQL Server:
```sql
CREATE PROCEDURE sp_GetEmployeeData 
  @EmployeeID INT
AS
BEGIN
  SELECT FirstName, LastName, JobTitle
  FROM Employees
  WHERE EmployeeID = @EmployeeID;
END;
