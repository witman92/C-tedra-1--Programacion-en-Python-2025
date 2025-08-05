## Problema 1: Exploración y validación de estructura del archivo (20 pts)
1. Carga el archivo `health_lifestyle_classification.csv` utilizando funciones integradas (`open`, `readlines`, `split`, etc.) — sin `pandas`.
2. Imprime:
    * Los nombres de las columnas
    * El número total de registros
    * El tipo de dato de cada columna
3. Valida que todas las filas tengan el mismo número de columnas que el encabezado.
3. Asegúrate de que los valores de `gender` y `smoking_level` sean válidos.
4. Crea una función `verificar_fila(fila: list) -> bool` que devuelva `True` si la fila es válida.
5. Imprime cuántas filas son inválidas.

## Problema 2: Clasificación de riesgo con múltiples condiciones (20 pts)
1. Define una función `clasificar_riesgo(fila)` que devuelva:
 * "Alto" si la persona tiene bmi >= 30, Smoking == Yes y physical_activity == No
 * "Medio" si solo cumple dos de esas condiciones.
 * "Bajo" si solo cumple una.
 * "Muy bajo" si no cumple ninguna.
2. Usa un bucle para clasificar cada individuo del dataset (puedes hacerlo con map o for) y guarda los resultados en una nueva lista.
3. Muestra el porcentaje de personas poco saludables respecto al total.

**Nota**: Si es necesario agragar columnas al dataframe hacerlo.

## Problema 3: Agregación y análisis por grupo (20 pts)
1. Escribe una función `contar_por_genero` que reciba el dataset y devuelva un diccionario con la cantidad de personas por género.
2. Agrega un parámetro opcional que permita filtrar solo a las personas por `diet_type` y por `education_level`.
3. Contesta:
* Cuantas masculinos tienen posgrado y ademas una vegana?
* Cual es el porcentaje de personas con estudios no universitarios que ademas tienen una dieta keto?
    * Cuantas son mujeres y cuantos hombres?
* Hay una tendencia de personas con posgrados y dietas veganas o vegetarianas?

* ## Problema 4: Transformaciones funcionales avanzadas (20 pts)
1. Usa `map()` y/o  `lambda` para crear una nueva lista con el BMI (Índice de Masa Corporal) transformado a texto:
* "Normal" si 18.5 ≤ BMI < 25
* "Sobrepeso" si 25 ≤ BMI < 30
* "Obesidad" si BMI ≥ 30
* "Bajo peso" si BMI < 18.5

2. Usa `filter()` para quedarte solo con los individuos categorizados como "Obesidad" en el paso anterior.
3.  Usa `reduce()` para contar cuántos individuos hay por categoría.

## Problema 5: Manejo de excepciones y robustez del código (20 pts)
1. Implementa una función `cargar_y_procesar(path: str)` que:
* Intente abrir y leer un archivo `.csv`.
* Detecte errores como:
    * Archivo no encontrado
    * Columnas incompletas
    * Errores comunes (`FileNotFoundError`, errores de tipo, etc.) con `try/except/finally` (por ejemplo, un BMI que no sea numérico)
* Genere mensajes específicos usando try/except y bloques finally.
* Devuelva None en caso de fallo, o una estructura de datos limpia si todo fue correcto.
