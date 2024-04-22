# Leccion 1:

```bash
La variable que ya es categorica, puede discretizarse numericamente? Sabiendo que al hacer esto introducimos orden, tiene sentido el orden? si la respuesta es afirmativa entonces la variable puede mapearse a numeros discretos. Si la respuesta es negativa ===> ONE HOT ENCODING
```

# Leccion 2:

```bash
Como reemplazo valores nulos:

=> Variables categoricas: En este caso, creamos una categoria nueva y se la imputamos a los valores faltantes.

=> Variable Numerica: Discretizamos la variable en rangos de datos (por frecuencia, por igual rango o algun criterio personalizado) creamos una categoria nueva y se la imputamos a los valores faltantes.
```

# Leccion 3: 

```bash
Tanto OneHotEncoder de Scikit-learn como get_dummies de Pandas se utilizan para convertir variables categóricas en variables binarias, pero cada uno maneja las variables categoricas que estas discretizadas (son numeros) de manera diferente.

# OneHotEncoder
OneHotEncoder primero debes convertir estas variables numéricas a tipo cadena o usarlas directamente como categóricas, configurando el encoder adecuadamente.

# get_dummies
get_dummies de Pandas es más flexible con los tipos de datos y automáticamente convierte cualquier variable categórica detectada en dummies, incluidas las numéricas si se interpretan como categóricas. No necesitas especificar el tipo de dato; get_dummies hará el trabajo por ti.

===> GUARDAR EL ENCODING EN UN .pickle
===> get_dummies no soporta la aparicion de variables categoricas nuevas, se pueden ignorar, se puede hacer que se lance una excepcion
===> OneHotEncoding si soporta nuevas variables categoricas 
```

# Leccion 4:

```python
pd.qcut(data['category'], q=number, retbins=True) ===> igual frecuencia, el retbins devuelve los puntos de corte

pd.cut(data['category'], bins=number) ===> igual rango

===> Guardar puntos de corte como .pickle

Como se usan de nuevo los puntos de corte?

pd.cut(data_training['category'], bins=saved_bins, include_lowest=True)
```

# Leccion 5:

```bash
===> Para convertir una variable categorica en forma numerica convertirla a string.
```