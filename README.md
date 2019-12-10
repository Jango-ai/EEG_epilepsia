# EEG_epilepsia
Machine Learning aplicado al diagnóstico de la epilepsia

Este proyecto se realizó como parte del curso de machine learning AI Saturdays Madrid de 2019.

El objetivo era producir un algoritmo que pudiera predecir si un paciente es o no epiléptico en base a un escaner de electroencefalografía (EEG).

# Dataset

Este notebook los que hace es procesar los datos de EEG de las muestras en formato edf de la página https://www.isip.piconepress.com/projects/tuh_eeg/

Para ejecutarlo requiere descargar los archivos y organizarlos en 4 carpetas: 
"/noepi" --> carpeta con archivos edf de no epilepticos para entrenar el modelo
"/epi" --> carpeta con archivos edf de epilepticos para entrenar el modelo
"/test_noepis" --> carpeta con archivos edf de no epilepticos para testar el modelo
"/test_epis" --> carpeta con archivos edf de epilepticos para testar el modelo

Una vez tienes los archivos bajados e indicas la ruta adecuada en el código, al ejecutarlo transforma los edf a 
formato lista de Python y luego una tabla Pandas para poder aplicar los algoritmos de inteligencia artificial. 

Inicialmente usamos los datos en bruto, sin realizar ninguna operación con ellos, excepto por un PCA para reducir la carga computacional manteniendo el 99.999% de la información.

# Modelo de Machine Learning

Hemos aplicado el modelo random forest para realizar la predicción sobre si el paciente es epiléptico. Los resultados salen en el notebook.

# Próximos pasos

- Hacer un tratamiento inicial de los datos para obtener valores que puedan ser más relevantes, como amplitud o distancia entre picos
- Probar otros algoritmos de Machine Learning de cara a aumentar la fiabilidad de la predicción

# Referencia

https://www.isip.piconepress.com/projects/tuh_eeg/

# Participantes
- José María Martín Brezmes
- Javier Visedo

# Introduccion al ML utilizando como ejemplo tratamiento de encefalogramas para distinguir personas sanas y personas con epilepsia

- ML

pendiente

- RF

pendiente

- EEQ

Los electroencefalogramas son el registro de la actividad electrica tomada sobre el cuero cabelludo.

Esta actividad se produce como consecuencia del funcionamiento de bloques de neuronas. 

Una lectura normal de EEQ es un proceso de 20 minutos. 

La dificultad de este ejemplo radica en que una persona con una enfermedad neuronal no siempre dara 

resultados anormales, siendo generalmente necesaria varios tests para ello.

Ademas lo que es anormal para una edad o genero puede ser normal en otra distinta.

Para nuestro "experimento" hemos tomado solo casos de adultos.

- EDF+

el formato de los eeq que utilizamos es el EDF+, formato publicado en el 2003 en Elsivier.

EDF+ es una evolucion del Formato de Datos Europe (EDF)para la transmision de EEQs entre distintos grupos academicos

El EDF+ permite almacenar mas datos que los EEG, como las condiciones de temperatura, luz y sonido. Lo que nos permite

hacer una reproducion del experimento mas fiel, o al menos poder tener estos factores en cuenta.

los ficheros EDF/EDF+ se pueden tratar con librerias Opensource ya que este formato se creo para poder transmitir la informacion entre los distintos grupos, no por fines comerciales.

para nuestro experimento utilizamos la biblioteca pyedflib. 

En el cuaderno learn se puede ver el código utilizado para trabajar con los ficheros EDF

Los ficheros EDF tienen tres bloques Cabecera Sesion, Cabecera canales y Datos

La cabecera de la sesion es un bloque de 256 bytes en formato ASCII 

con version del formato (8 bytes) nombre del paciente (80 caracteres) identificador de la grabacion (80 caracteres) fecha(DD MM YY h24 mm ss)

44 bytes de espacio reservado, numero de muestras (8 bytes, -1 indicara que no se conoce) durcion (8B) numero de canales (4B)

- Cabecera de canal

habra una cabecera de canal por cada uno de los canales que hayamos indicado en el campo numero de canales de la cabecera de sesion

cada uno de ellos sera un bloque de 256 bytes

donde se indicara el nombre del canal, tipode transductor, escala de los datos, medicion fisica maxima y minima posible, amplitud maxima y minima digital, prefiltrado si se esta usando, frecuencia de muestreo y 32 bytes reservados

- Datos 

Son los registros generados por las tomas de informacion 
