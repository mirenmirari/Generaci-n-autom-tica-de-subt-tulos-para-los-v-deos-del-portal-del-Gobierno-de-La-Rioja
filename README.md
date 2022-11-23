# Generación automática de subtítulos para los vídeos del portal del Gobierno de La Rioja

Este repositorio es parte del Trabajo de Fin de Máster del Máster de Ciencia de Datos y Aprendizaje Automático de la Universidad de La Rioja. En él contamos con los cuadernos wav2vec, pocketsphinx, whisper_funciones, fine-tuning_small, tiempos y tiemposWhisper. 

En el notebook wav2vec lo que hacemos es crear una serie de funciones que se encarguen de realizar los distintos pasos necesarios para transcribir un vídeo utilizando el modelo wav2vec. Después, se define una función que se encargue de ir llamando a dichas funciones y, además, de calcular el error cometido tanto con el texto normalizado como sin normalizar. Para acabar, lo que se hace es cargar los 74 vídeos del dataset junto con el texto escrito a mano y calcular, por medio de la última función definida, tanto los textos transcritos por el modelo como el error cometido por el mismo haciendo la media del error de cada vídeo.

En los notebooks pocketsphinx y whisper_funciones la idea es la misma, solo que para los modelos PocketSphinx y Whisper respectivamente. Además, en el notebook relativo a Whisper se hace el mismo proceso para cada uno de los 5 tamaños de arquitectura posibles (Tiny, Base, Small, Medium y Large). 

Por otro lado, debido a que el modelo Whisper con el tamaño Medium es el que mejores resultados obtiene, se ha creado el repositorio https://github.com/mirenmirari/subtitulos_canalgobierno donde se encuentran los subtítulos generados por dicho modelo para los 74 vídeos del dataset.

Además, en el notebook fine-tuning_small se entrena el modelo de Whisper con el dataset de CommonVoice https://huggingface.co/datasets/mozilla-foundation/common_voice_11_0/viewer/es/train. 

Respecto al notebook llamado tiempos, volvemos a definir una serie de funciones que se encarguen de realizar los pasos necesarios para hacer la transcripción, pero en este caso tanto para el modelo Wav2Vec como para el PocketSphinx. Además, definimos una función que se encargue de transcribir el vídeo y que funcione para ambos modelos, pero en este caso no calculará la métrica ya que no contamos con unos subtítulos originales con los que comparar. Sin embargo,  sí que mediremos el tiempo que tarda en crear el texto. Después, cargamos un vídeo y calculamos su transcripción y el tiempo que tarda en llevarla a cabo.

Por último, en el notebook tiemposWhisper creamos las funciones análogas a las del notebook tiempos solo que para el modelo de Whisper. Además, al igual que pasaba con el notebook whisper_funciones, calculamos los resultados para los 5 posibles tamaños.
