El proceso comenzó con la importación de los datos desde un archivo JSON alojado en GitHub. Los datos presentaban una estructura anidada, con información de customer, phone, internet y account agrupada en diccionarios dentro de las columnas principales.

Los pasos de limpieza y tratamiento incluyeron:

Desanidamiento de Columnas: Las columnas anidadas (customer, phone, internet, account) fueron desglosadas en columnas individuales para facilitar el acceso a los datos.
Verificación de Tipos de Datos: Se inspeccionaron los tipos de datos para asegurar su correcta interpretación, identificando que las columnas de cargos (Charges.Monthly, Charges.Total) estaban como tipo 'object' debido a la presencia de valores no numéricos.
Manejo de Valores Ausentes y Duplicados: Se verificó la presencia de valores nulos (identificando algunos en TotalCharges) y filas duplicadas (ninguna encontrada). Las filas con cadenas vacías en la variable objetivo Churn fueron eliminadas para asegurar la calidad de los datos para el análisis de evasión.
Conversión de Tipos de Datos: Las columnas Charges.Monthly y Charges.Total fueron convertidas a tipo numérico. Los valores no numéricos en TotalCharges fueron tratados como errores y se imputaron con 0, asumiendo que un cargo total de 0 indica una cuenta nueva o un error similar.
Verificación de Consistencia Categórica: Se examinaron los valores únicos en las columnas categóricas para identificar posibles inconsistencias o errores de formato.
Normalización de Variables Numéricas: Las columnas numéricas tenure, Charges.Monthly, y Charges.Total fueron normalizadas utilizando MinMaxScaler. Esto es crucial para futuros modelos de aprendizaje automático que sean sensibles a la escala de las variables.
Creación de Nueva Variable: Se calculó una nueva variable, cargos_diarios, dividiendo los cargos_mensuales por 30.
Renombrado de Columnas: Las columnas se renombraron a nombres más descriptivos en español para una mejor comprensión.
Codificación Binaria: Las columnas categóricas binarias ('Yes'/'No') fueron convertidas a formato numérico (1/0) para su uso en análisis cuantitativos y visualizaciones.
Este proceso de limpieza y transformación aseguró que los datos estuvieran en un formato adecuado para el análisis exploratorio y la modelización futura.
