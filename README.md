# PRÁCTICA 4. VISIÓN POR COMPUTADOR

> Trabajo realizado por:
> - David Koschel Henríquez
> - Pablo Nicolás Santana Hernández

## ENTRENAMIENTO DEL MODELO

Primero que nada, buscamos un dataset que se ajustase a lo que necesitábamos, para ello estuvimos buscando en Kaggle y
Roboflow. Cuando
encontramos un [dataset que valiera](https://universe.roboflow.com/manoworkspace/license-planes/dataset/5/images) para
la construcción del modelo que queríamos, preparamos el entorno y empezamos a
entrenarlo.
Se juntaron todas las imágenes en una única clase, ya que al principio estaban divididos en dos y se dividió en tres
conjuntos, entrenamiento, validación y test.
Con el dataset que obtuvimos entrenamos el modelo en Kaggle para aprovechar de su potencia de GPU. Para ello, fuimos
ajustando
los valores de _batch_ e _imgsize_ para obtener un modelo que funcionase bien sobre el vídeo de prueba.

El entrenamiento no nos dio los resultados que esperábamos (el modelo todavía cometía bastantes fallos), pero lo
suficientemente decentes como para realizar la práctica.

En el siguiente [link](https://www.kaggle.com/code/user06092111/notebook3da451b170) se puede encontrar la instancia de
Kaggle y el dataset
que empleamos. Además, en el apartado ouptut están los resultados de los entrenamientos. El empleado en la práctica fue
el último que
se entrenó.

Una vez entrenado el modelo, se adjuntó al proyecto en el siguiente [archivo](best.pt).

## DESARROLLO DEL CÓDIGO

El código desarrollado realiza una detección usando el [modelo general de yolo](yolo11n.pt) en cada frame
para las clases definidas en la variable `yolo_classes`. Cuando el modelo detecta una clase, la dibuja en el frame
con un rectángulo, la equitqueta y añade al total de clases el objeto encontrado según su id de rastreo (para así
evitar duplicaciones).

Además, cuando se detecta un vehículo, se escanea únicamente la imagen correspondiente al vehículo para detectar la
matrícula y señalarla en el frame.

Todos estos datos de detección se vuelcan en un [archivo csv](datos.csv), además
del [video final](https://alumnosulpgc-my.sharepoint.com/:v:/g/personal/david_koschel101_alu_ulpgc_es/EeZrEN3Og3hBjhjzVuJBoEIBEtEWwhR3WA0jh522aG8wiA?e=CEMbvL)
con los rectángulos y el conteo por clase.

Todas las funciones implementadas en el código junto con una breve explicación de su utilidad se pueden encontrar en el
[cuaderno Jupyter](VC_P4.ipynb).
