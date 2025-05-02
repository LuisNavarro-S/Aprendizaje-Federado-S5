# Aprendizaje-Federado-S5
(CLOUD COMPUTING) Aprendizaje Federado

# Requisitos Previos  
Python y dependencias necesarias 🐍
* numpy
* matplotlib
*tensorflow
*scikit-learn
*json
*tqdm

Acceso a los datos segmentados en formato 'data_part_#.json' (proporcionados en conjunto con su código confidencial en la entrega de Canvas)

#Instrucciones de Uso

## Clonar el repositorio
```bash
gh fork LuisNavarro-S/Aprendizaje-Federado-S5
cd clase5_ComputoNube
```

## Configuración al archivo de datos entrenamiento
Mueve los fragmentos de datos en base a la cantidad "n" de integrantes y secciones disponibles (localizado en el comentario de Canvas) al directorio del proyecto:

## Creación de los modelos

Para preparar y entrenar el modelo, ejecuta el notebook:

```bash
jupyter notebook Entrenamiento_Local.ipynb
```
  Este notebook utiliza los fragmentos formato json proporcionados anteriormente, donde se incluye la implementación de aprendizaje federado y el entrenamiento independiente de 
  cada modelo (en conjunto con su exportación individual)


## Evaluación de los modelos

Para validar los modelos, ejecuta el notebook:
```bash
jupyter notebook Evaluacion_Modelo.ipynb
```
  Se evalua cada uno de los segmentos de datos con su validación individuañ
  Se evualua un modelo global al concertar los modelos y sus pesos mediante FedAvg, FedProx y FedMax 
  Se entrena y valida el modelo completo como formato comparativa vs el aprendizaje federado.

## Explicación FedAvg, FedProx y FedMax

Posterior a cada integrante entrenará su partición de la información, se importan los modelos para posteriormente "combinar" los pesos y armar un modelo globalizado
FedAvg: Promedia los pesos de los modelos, dentro de la implementación los obtiene en base a la arquitectura de 'TheModelFinalFinalV2.ipynb'

FedProx: Esta implementación añade una variable de regulación dentro del código, dado que busca que los pesos del modelo global no se alejan del modelo localmente entrenado mediante la obtención de promedios (como FedAvg) y 
los pesos locales. De forma coloquial, es una resta entre los pesos promedios y la diferencia entre los locales y este último. Esta manera de manejar el aprendizaje federado y juntarlos es frecuente cuando los datos se encuentran desbalanceados.

FedMax:Esta implementación extrae los pesos de los modelos y los revisa para conservar el valor máximo, 







