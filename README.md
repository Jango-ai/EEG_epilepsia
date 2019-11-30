# EEG_epilepsia
Machine Learning aplicado al diagnóstico de la epilepsia

Este notebook los que hace es procesar los datos de EEG de las muestras de la página https://www.isip.piconepress.com/projects/tuh_eeg/

Para ejecutarlo requiere descargar los archivos y organizarlos en 4 carpetas: 
"/noepi" --> carpeta con archivos edf de no epilepticos para entrenar el modelo
"/epi" --> carpeta con archivos edf de epilepticos para entrenar el modelo
"/test_noepis" --> carpeta con archivos edf de no epilepticos para testar el modelo
"/test_epis" --> carpeta con archivos edf de epilepticos para testar el modelo

Una vez tienes los archivos bajados e indicas la ruta adecuada en el código, al ejecutarlo transforma los edf a 
formato lista de Python y luego una tabla Pandas para poder aplicar los algoritmos de inteligencia artificial
