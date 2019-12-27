![Iron Hack](https://github.com/rogerzadi/ModeloSupervivencia/blob/master/images/ironhack.png)
# Predicción de Precios Airbnb (Competencia Kaggle)
Este modelo es creado para predecir el precio de más de 9000 registros (en este caso, alojamientos) de airbnb utilizando modelos de predicción



### Modelos Utilizados
- Se utiliza PCA para disminuir dimensiones 
-- como métrica de error se utiliza: mean_squared_error
- LinearRegression
From Sklearn
- GradientBoostingRegressor
- ExtraTreeRegressor
- RandomForestRegressor
- Lasso
- Ridge
- SVR
- SGDRegressor 
- KNeighborsRegressor 
Tambien se utilizan estas librerias:
- xgboost
- catboost
- lightgbm

### Modelo

El modelo tiene como entrada:
Un database dado por el profesor en el cual se encuentran mas de 20,000 registros

La cual contiene mas de 20 columnas y el precio.

### Limpieza

Lo primero que hacemos es quitar outliers, sin embargo se quitan muy pocos, ya que por la naturaleza de los regstros estos pueden llegar a ser muy subjetivos, posteriormente se normalizan los datos que tienen como metrica de 0 a 100 para que sean de 0 a 1, esto ayuda mucho, las variables que estan como "t" y "f" se cambian a 1 y 0 
Se hace drop a las columnas que para este estudio no son necesarias
se cambian los distintos tipos de datos, tambien cambiando a un tipo mas apto para cada distanta columna.
Al final se crean 4 Datasets diferentes, uno donde estan todas las variables numéricas, uno donde estan las variables categóricas tansformadas a Dummies, uno donde podemos encontrar las variables con atributo Time y uno final donde se encuentran juntos los el dataset numérico y categótico

### Predicción 

Se genera un pipeline el cual contiene todos los modelos antes mencionados, esto se prueba con los distintos datasets, el resultado de su métrica de error se almacena en una tabla para ver cuales son los mejores, posteriormente se eligen los 5 mejores modelos y se saca una media

Se utilizo **Grid Searching Bayesiano** para optimizar el modelo de XBoost

se puede ver la competencia en este [link.](https://www.kaggle.com/c/datamex-1019/leaderboard)
