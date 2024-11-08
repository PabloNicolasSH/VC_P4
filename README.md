# PRÁCTICA 4. VISIÓN POR COMPUTADOR

> Trabajo realizado por:
> - David Koschel Henríquez
> - Pablo Nicolás Santana Hernández

## ENTRENAMIENTO DEL MODELO

Primero que nada, buscamos un dataset que se ajustase a lo que necesitábamos, para ello estuvimos buscando en Kaggle y
Roboflow. Cuando
encontramos un dataset que valiera para la construcción del modelo que queríamos, preparamos el entorno y empezamos a
entrenarlo.
Con el dataset que obtuvimos entrenamos el modelo en Kaggle para aprovechar de su potencia de GPU. Para ello, fuimos
ajustando
los valores de _batch_ e _imgsize_ para obtener un modelo que funcionase bien sobre el vídeo de prueba. El dataset usado
fue el adjuntado en el siguiente
[link](https://universe.roboflow.com/manoworkspace/license-planes/dataset/5/images).
Se juntaron todas las imágenes en una única clase, ya que al principio estaban divididos en dos y se dividió en tres
conjuntos, entrenamiento, validación y test.

Posteriormente, se comenzó a realizar el entrenamiento del modelo. Esta parte de la práctica
fue la que más problemas nos causó, ya que nuestros ordenadores personales tardaban mucho en realizar los
entrenamientos.
Por ello decidimos realizar el entrenamiento en Kaggle,
el
cual no nos dio los resultados que esperábamos (porque el modelo todavía cometía bastantes fallos), pero lo
suficientemente
decentes como para realizar la práctica.

En el siguiente [link](https://www.kaggle.com/code/user06092111/notebook3da451b170) puede encontrar la instancia de
Kaggle
que empleamos y el dataset.

Una vez entrenado el modelo, se adjuntó al proyecto en el siguiente [archivo.pt](best.pt).

## DESARROLLO DEL CÓDIGO

El código desarrollado realiza una detección usando el [modelo general de yolo](yolo11n.pt) en cada frame
para las clases definidas en la variable `yolo_classes`. Cuando el modelo detectaba una clase, la dibujaba en el frame
con un rectángulo, le añadía su nombre y añadía al total de clases el objeto encontrado según su id de rastreo (para así
evitar duplicaciones).

Además, cuando detectaba un vehículo, escaneaba únicamente la imagen correspondiente al vehículo para detectar la
matrícula señalarla en el frame.

Todos estos datos de detección se iban volcando en un [archivo csv](datos.csv), además
del [video final](https://alumnosulpgc-my.sharepoint.com/:v:/g/personal/david_koschel101_alu_ulpgc_es/EeZrEN3Og3hBjhjzVuJBoEIBEtEWwhR3WA0jh522aG8wiA?e=CEMbvL)
con los
rectángulos y el conteo por clase.

Todas las funciones implementas en el código junto con una breve explicación de su utilidad se pueden encontrar en el
[cuaderno Jupyter](VC_P4.ipynb).