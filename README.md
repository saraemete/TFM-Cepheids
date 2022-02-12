# TFM-Cepheids

A continuación se detalla el contenido de este repositorio, perteneciente al Trabajo de Fin de Máster de Sara Muñoz Torres, titulado "".


## Breve descripción 

El objetivo de este trabajo es comprobar la validez de las metalicidades en estrellas Cefeidas determinadas por el proyecto SH0ES para el cálculo de la constante de Hubble [A. Riess, 2016](https://iopscience.iop.org/article/10.3847/0004-637X/826/1/56). Así, se emplean 5 de las galaxias hospedadoras de estrellas Cefeidas utilizadas en el proyecto SH0ES, observadas con espectroscopía de cmapo integral. La metodología seguida para la determinación de las metalicidades es:

 1. Extracción de los espectros en las posiciones de las Cefeidas
 2. Correción de la extinción de la Vía Láctea y del corrimmiento al rojo
 3. Síntesis de los espectros
 4. Ajustes gaussianos de las líneas de emisión de Hβ, Hα, OIII[5007] y NII[6583] para medir el flujo
 5. Determinación y corrección de la extinción de la galaxia anfitriona
 6. Cálculo de metalicidades mediante la calibración de [Pettini & Pagel 2004](https://academic.oup.com/mnras/article/348/3/L59/1280428)


## Requisitos para ejecutar los códigos 📋

Para el correcto funcionamiento de los códigos se han de emplazar los archivos grandes, que se pueden encontrar en este [drive](https://drive.google.com/drive/u/5/folders/1AHKIRPcjnqzH8-04cx5OZ3LoRAEzcBXj) de manera pública, en las correspondientes carpetas como se detalla acontinuación:

```
NGC3021/ NGC3021.V500.rscube.fits
         ic1376010_drz.fits

NGC3972/ NGC3972.V500.rscube.fits
         icjf12020_drz.fits
         
NGC3982/ NGC3982.V500.rscube.fits
         ib1f22040_drz.fits
         
NGC7250/ NGC7250.V500.rscube.fits
         ic130c020_drz.fits
         
NGC7250_new/ NGC7250_new.V500.rscube.fits
             ic130c020_drz.fits
             
UGC09391/ UGC09391.V500.rscube.fits
          ic1360uzq_drz.fits
          adj_spectrum_UGC9391.ipynb
```          

Los paquetes de terceros de Python que deben tener instalados para la ejecución de los códigos son:

- [numpy](https://numpy.org/)
- [matplotlib](https://matplotlib.org/)
- [pandas](https://pandas.pydata.org/)
- [astropy](https://www.astropy.org/)
- [scipy](https://scipy.org/)
- [extinction](https://extinction.readthedocs.io/en/latest/)
- [emcee](https://emcee.readthedocs.io/en/stable/)
- [corner](https://corner.readthedocs.io/en/latest/)
- [IPython](https://ipython.org/)
- [seaborn](https://seaborn.pydata.org/)
- [sklearn](https://scikit-learn.org/stable/)
- [aplpy](https://aplpy.readthedocs.io/en/stable/)




## Estructura del repositorio

Los 




Se van a encontrar tanto los códigos empleados para determinar la metalicidad, comparar resultados y crear gráficos, como los archivos de salida y entrada a estos códigos (p.e. las tablas finales).




