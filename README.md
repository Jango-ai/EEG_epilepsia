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
