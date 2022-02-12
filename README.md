# TFM-Cepheids

A continuación se detalla el contenido de este repositorio, perteneciente al Trabajo de Fin de Máster de Sara Muñoz Torres, titulado "".


## Breve descripción 📖

El objetivo de este trabajo es comprobar la validez de las metalicidades en estrellas Cefeidas determinadas por el proyecto SH0ES para el cálculo de la constante de Hubble [A. Riess, 2016](https://iopscience.iop.org/article/10.3847/0004-637X/826/1/56). Así, se emplean 5 de las galaxias hospedadoras de estrellas Cefeidas utilizadas en el proyecto SH0ES, observadas con espectroscopía de campo integral. La metodología seguida para la determinación de las metalicidades es:

 1. Extracción de los espectros en las posiciones de las Cefeidas
 2. Correción de la extinción de la Vía Láctea y del corrimmiento al rojo
 3. Síntesis de los espectros
 4. Sustracción del espectro estelar
 5. Ajustes gaussianos de las líneas de emisión de Hβ, Hα, OIII[5007] y NII[6583] para medir el flujo
 6. Determinación y corrección de la extinción de la galaxia anfitriona
 7. Cálculo de metalicidades mediante la calibración de [Pettini & Pagel 2004](https://academic.oup.com/mnras/article/348/3/L59/1280428)



## Requisitos para ejecutar los códigos ⚙️

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




## Estructura del repositorio 📋 

### Gráficos

Los gráficos de todas las galaxias mostrados en el trabajo se han determinado mediante el código `galaxies_graphics.ipynb`, que se encuentra en la rama principal. 


### Metodología

Los pasos especificados en la [descripción](https://github.com/saramunoztorres/TFM-Cepheids#breve-descripci%C3%B3n) se ejecutan en códigos individuales para cada galaxia, que se encuentran dentro de las respectivas carpetas. Estos se ordenan tal que:

- Los puntos 1 y 2 están dentro del código `extract_spectrum_x.ipynb`. El output de este código, que a su vez es input para *STARLIGHT* (a expectión del archivo `m_Riess.txt`) se guarda en la respectiva subcarpeta `\emited_spectrum` con la extensión `.txt`
- El punto 3 queda fuera de este repositorio, pero los resultados de la síntesis se encuentran en las subcarpetas `\emited_spectrum` con la extensión `.BN`
- Los puntos 4, y 5 se encuentran en el código `adj_spectrum_x.ipynb`, cuyos inputs son los archivos de la respectiva subcarpeta `\emited_spectrum` y los outputs se guardan en la subcarpeta `\adjusted_spectrum`
- Finalmente, los puntos 6 y 7 se ejecutan con el código `metallicity_calculate_x.ipynb`, que tiene como input el archivo `flujos.txt` generado en el código anterior y almacenado en la subcarpeta `\adjusted_spectrum`, y los outputs son los archivos `.txt` con la información de las metalicidades determinadas y sus errores.

La *x* se refiere a la respectiva galaxia. Dentro de los archivos se encuentran descritos los códigos en mayor profundidad. Por otro lado, las posiciones de las Cefeidas, cribadas entre los códigos `extract_spectrum_x.ipynb` y  `galaxies_graphics.ipynb`, se guardan en la carpeta base de cada galaxia como `cefeidasx_final.txt`, así como las metalicidades del proyecto SH0ES, `met_x_Riess.txt`, que se criban en los códigos `extract_spectrum_x.ipynb` y `metallicity_calculate_x.ipynb`.


### Resultados y discusión

Finalmente, en el código `results_discussion.ipynb` se encuentran los gráficos y cálculos finales para obtener los resultados de la galaxia NGC 7250, así como los empleados en la discusión este trabajo. Los archivos de la rama principal `tabla_final.csv`, `tabla_final.txt` y `pos_met_latex.txt` son obtenidos en este código. Los dos primeros guardan la información de las metalicidades calculas en las distintas calibraciones con los respectivos errores, mientras que el último tiene la información relativa a la metalicidad en cada posición (en RA y DEC).
