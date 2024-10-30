# PRÁCTICA 4. VISIÓN POR COMPUTADOR

> Trabajo realizado por:
> - David Koschel Henríquez
> - Pablo Nicolás Santana Hernández

## ENTRENAMIENTO DEL MODELO
Primero que nada, buscamos un dataset que se ajustase a lo que necesitábamos, para ello estuvimos buscando en Kaggle y Roboflow. Cuando
encontramos un dataset que valiera para la construcción del modelo que queríamos, preparamos el entorno y empezamos a entrenarlo.
Con el dataset que obtuvimos entrenamos el modelo en Kaggle para aprovechar de su potencia de GPU. Para ello, fuimos ajustando
los valores de _batch_ e _imgsize_ para obtener un modelo que funcionase bien sobre el vídeo de prueba. 