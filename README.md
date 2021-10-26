# Neural Network - Verificación Biométrica Facial Mediante Codificador Automático


Lea las carpetas y las imágenes usando el comando cd::<br/>
 fn = cd(['C:\Users\Ritika\Desktop\Neural Networks\Ritika_Chowdri_AE\s' num2str(i)]);<br/>
<br/>
Normalizado las imágenes entre valores 0 y 1. <br/>
 img = double(img)/256; <br/>
 <br/>
 Creó un vector de celda de fila para entrenar y probar imágenes (112 * 92 píxeles cada una). <br/>
  Train_cell = mat2cell(img,112,92); <br/>
		 Test_cell = mat2cell(img,112,92); <br/>
 <br/>
 
## Variaciones En los Parámetros de Aprendizaje
Para el primer auto encoder <br/>
	       ‘Hidden_layer1’ = 100 <br/>
	       'MaxEpochs‘ = 400 <br/>
          <br/>
PAra el segundo auto encoder <br/>
		‘Hidden_layer2’ = 50 <br/>
		‘MaxEpochs’ = 100 <br/>
                'L2WeightRegularization‘ = 0.006 and 0.008 <br/>
                'SparsityRegularization‘ = 1 and 3 <br/>
                'SparsityProportion‘ = 0.15 and 0.30 <br/>
Total 8 combinaciones de L2WR,  SR y SP <br/>

## Usando diferentes combinaciones de los parámetros de aprendizaje, encuentre las mejores representaciones profundas usando codificadores automáticos apilados que maximizan las variaciones entre clases e intraclase (d ') en el sentido -MSE
Primero entrenamos el codificador automático disperso en los datos de entrenamiento sin usar las etiquetas.<br/>
Los pesos se inicializan aleatoriamente antes del entrenamiento.<br/>
El vector de características se genera y se pasa al segundo codificador automático.<br/>
Entrene la capa softmax para clasificar el vector de características de 50 dimensiones.<br/>
  Puntajes genuinos = 600<br/>
  Puntuaciones de impostor = 28080<br/>
  
<p align="center">
  <img src="4.jpg" />
</p>

<p align="center">
  <img src="5.jpg" />
</p>

<p align="center">
  <img src="6.jpg" />
</p>

<p align="center">
  <img src="7.jpg" />
</p>

<p align="center">
  <img src="8.jpg" />
</p>

## Área bajo la curva

<p align="center">
  <img src="area.png" />
</p>

## Deepnet Usando Dos Codificadores Automáticos y Una Capa Softmax

<p align="center">
  <img src="deep.png" />
</p>

Tomando la mejor configuración entrenamos la red neuronal y generamos curvas roc para imágenes de prueba
<p align="center">
  <img src="n1.png" />
</p>

## Conclusiones

-La normalización de los datos se realiza para mejorar el rendimiento de la red.<br/>
-Cuanto mayor es la regularización de la dispersión, peor es la curva ROC.<br/>
-Cuanto mayor es la disminución del peso, menor es el efecto de la regularización de la dispersión en la ROC.<br/>
-El ajuste fino de la red mejora el rendimiento.<br/>

## Referencias
Inspirado en el proyecto de: RITIKA CHOWDRI
<p align="center">
  <img src="https://user-images.githubusercontent.com/81122669/123591935-3a779c80-d7b2-11eb-919d-573247b80faa.JPG" />
</p>

Ramírez Cotonieto Luis Ferando 
Redes Neuronales 
2020630417
