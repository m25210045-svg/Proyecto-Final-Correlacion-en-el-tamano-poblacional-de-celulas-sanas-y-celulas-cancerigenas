[![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](https://matlab.mathworks.com/open/github/v1?repo=m25210045-svg/ProyectoGD)

# Proyecto: Correlación en el tamaño poblacional de células sanas y células cancerígenas con respecto a sus tasas de absorción de nutrientes.

## Información de la estudiante
Oscar González Ramírez \[M25210050]; M25210050@tectijuana.edu.mx

Vincent Alejandro Villela Salinas \[M25210045]; M25210045@tectijuana.edu.mx

Gemelos Digitales

Ingeniería Biomédica

## Docente
Dr. Paul Antonio Valle Trujillo; paul.valle@tectijuana.edu.mx

Departamento de Ingeniería Eléctrica y Electrónica, Tecnológico Nacional de México/IT Tijuana, Blvd. Alberto Limón Padilla s/n, Tijuana, C.P. 22454, B.C., México.

## Descripción de la asignatura
La asignatura de Gemelos Digitales forma parte del plan de estudios de la carrera en Ingeniería Biomédica con la siguiente competencia general del curso: Formula el gemelo digital a través de datos experimentales para el desarrollo estrategias de control mediante teorías de sistemas dinámicos no lineales y la experimentación in silico. Esta asignatura pretende aportar al perfil del Ingeniero Biomédico la capacidad de realizar investigación científica en el área de Biología de Sistemas con la finalidad de dirigir y participar en equipos de trabajo interdisciplinarios en contextos nacionales e internacionales, así como de proporcionar soluciones informáticas para resolver problemas en el campo de la Ingeniería Biomédica con ética profesional.

En el contexto de sistemas dinámicos que describen sistemas biológicos o fisiológicos, el modelizado in silico es una extensión lógica de la experimentación in vitro controlada, es el resultado natural del gran aumento de la potencia computacional disponible a un costo que disminuye continuamente, combinando las ventajas de la experimentación in vivo e in vitro, sin someterse a las consideraciones éticas y la falta de control asociadas con los experimentos in vivo. A diferencia de los experimentos in vitro, que existen de forma aislada, los modelos in silico permiten incluir un conjunto prácticamente ilimitado de variables y parámetros, lo que hace que los resultados sean más aplicables en problemas del mundo real. La experimentación in silico ha dado lugar al paradigma denominado como "gemelos digitales" (en inglés digital twins); en esencia, los gemelos digitales son una réplica o representación digital de un proceso o sistema del mundo real, donde por replica se refiere a un modelo computacional desarrollado con base en datos experimentales y características especiales que le permiten conectar lo físico con lo virtual con el propósito de mejorar el rendimiento de un sistema, detectar y prevenir fallas, y realizar predicciones sobre su respuesta ante diferentes estímulos o escenarios de operación; una definición más formal establece que: un gemelo digital es un conjunto de modelos adaptativos que emulan el comportamiento de un sistema físico en un sistema virtual obteniendo datos en tiempo real para actualizarse a lo largo de su ciclo de vida; replica al sistema físico para predecir fallas y oportunidades de cambio, prescribir acciones en tiempo real para optimizar y/o mitigar eventos inesperados observando y evaluando el perfil operativo del sistema. En el campo particular de la Biología de Sistemas, un gemelo digital se presenta como un algoritmo o conjunto de algoritmos computacionales desarrollados con base en modelos mecanicistas de un organismo vivo, esto con el objetivo de emular su fisiología para ilustrar su dinámica en el corto y en el largo plazo, así como predecir su respuesta a diferentes estímulos endógenos y exógenos.

## Objetivo y descripción del sistema
A continuación se presenta una tabla de datos que muestra la dinámica de tres conjuntos de variables biólogicas y su evolución con el tiempo, medido en días.
<img width="1256" height="517" alt="base de datos" src="https://github.com/user-attachments/assets/ba455cc8-2e96-4153-9824-ae208b655554" />

Se debe escoger uno de estos 3 conjuntos de datos, escoger un contexto para el comportamiento de sus variables y aplicar las técnicas de modelado y análisis matemático visto a lo largo de la materia para encontrar el sistema de ecuaciones correspondientes a dicho conjunto y dicho contexto.

Palabras clave: Sistema no lineal; Células sanas; Células cancerígenas; Simulaciones numéricas; Tamaño poblacional células.

## Actividades a realizar
1. Seleccionar grupo de datos y obtener ecuaciones mediante Eureqa de cada conjunto de datos.
2. Suavizar y normalizar los datos para ser graficados en MATLAB.
3. Otorgar contexto a las ecuaciones para representar un sistema biológico.
4. Modelar las ecuaciones y obtener bioestadísticas con MATLAB.
5. Graficar en MATLAB la predicción a 2t con base en las ecuaciones obtenidas con Eureqa.
6. Calcular los puntos de equilibio y la matriz jacobiana con MATLAB.
7. Determinar puntos de equilibio estables mediante MATLAB.
8. Expresar las ecuaciones obtenidas con Eureqa en diagrama a bloques mediante Simulink, agregar variable de control y exportar datos a MATLAB para el análisis de sus bioestadísticas.
9. Implementar en MATLAB la variable de control y graficar el sistema de ecuaciones considerando la variable.
10. Realizar el análisis matemático en Scientific WorkPlace, reportando el modelo matemático, el análisis de positividad del sistema, los puntos de equilibrio estables y estabilidad local.
11. Diseñar un diagrama biológico sobre la dinámica del sistema y la interacción entre sus variables con las figuras de https://bioart.niaid.nih.gov/ o https://www.biorender.com/.

## Desarrollo

Se seleccionó el segundo conjunto de datos, los cuales fueron interpretados como la cantidad de nutrientes que eran repartidas y absorbidas por dos poblaciones de células dentro de un organismo. La representación del sistema se observa a continuación con la figura hecha en BioRender.

<p align="center">
<img width="720" height="504" alt="Modelo_Biologico_Proyecto (1)" src="https://github.com/user-attachments/assets/e5ab358b-79ad-4474-8e4f-917cc9469482">
</p>

A partir de los datos brindados en la tabla que corresponden con el segundo conjunto, se utilizó Eureqa para obtener las siguientes ecuaciones que corresponden con este sistema:

        dx/dt = rho1*x + rho2*x*y*z - rho3*x^{3} - rho4*x^{2}*y + u;        	(1)
        dy/dt = rho5*y + rho6*y^{2}*z + rho7*y^{2}*z^{2} - rho8*y*z;        	(2)
        dz/dt = rho9*z + rho10*z^{3} - rho11*z^{2} - rho12*x*z^{3};        	(3)

donde cada rho representa un número real y son los parámetros para el sistema de ecuaciones, y u es la variable de control.

La ecuación (1) representa la tasa de absorción de nutrientes por parte de la población de células sanas en el organismo, la ecuación (2) a la tasa de agotamiento de los nutrientes disponibles dentro del organismo y la ecuación (3) es la tasa de absorción de nutrientes por parte de la población de células cancerígenas. Conforme el sistema opera, la cantidad de nutrientes absorbidos por ambas poblaciones aumenta conforme la cantidad de nutrientes disponibles disminuye; notando que la población de células cancerígenas consume más nutrientes que la población de células sanas, infireindo a que conforme pasa el tiempo la población de células cancerígenas crece a una velocidad más alta que las células sanas. Notesé que, a partir de la tabla de datos, la cantidad de nutrientes en la células cancerígenas se reduce un poco mientras que la de células sanas aumenta un poco cerca de cuando ya casi se agotaron todos los nutrientes disponibles en el organismo. Por lo que, si se aplica una técnica que permita reducir la cantidad de nutrientes disponibles para estas células, debería ser posible reducir su población celular gradualmente.

Por ello, dentro de la ecuación (1) se incluye una variable de control u en la forma de una rampa unitaria. Para esto, se tomó como referencia el tratamiento contra el cáncer a partir del uso de células CAR-T, en donde se toma una pequeña cantidad de células T por parte del organismo infectado, se modifican géneticamente en un laboratorio para que puedan detectar, atacar y destruir células cancerígenas; se múltiplican en masa y se inyectan de vuelta en el organismo para superar en números a la población de células cancerígenas de golpe, atacándolas mientras que, a la vez, reducen la cantidad de nutrientes que tienen disponibles para seguir creciendo en tamaño poblacional. Es por este motivo que en el modelo matemático implementado se refleja como una señal de rampa, ya que se incrementa gradualmente las dosis de células modificadas en el organismo para observar su comportamiento conforme pasan los días, resultando en un intercambio notable entre los tamaños de las células sanas con respecto a las células cancerígenas pasados los 70 días; así como una diferencia en la cantidad de nutrientes restantes en dicho organismo debido a estos cambios.

## Conclusiones


## Lista de archivos incluidos en el repositorio
1. Cuaderno computacional de MATLAB [.mlx].
2. Carpeta con imágenes de las simulaciones [.pdf].
3. Análisis matemático proyecto [.pdf].
4. Modelo de Simulink [.slx].
5. Datos del sistema biológico [.csv].
6. Archivo Eureqa [.fxp].

## Referencias
\[1] P. A. Valle, Syllabus para Gemelos Digitales, Tecnológico Nacional de México / Instituto Tecnológico de Tijuana, Tijuana, B.C., México, 2025. Permalink: https://biomath.xyz/course/

\[2] American Cancer Society. Terapia de células CAR-T y sus efectos secundarios. Cancer.org, 2022. Permalink: https://www.cancer.org/es/cancer/como-sobrellevar-el-cancer/tipos-de-tratamiento/inmunoterapia/terapia-de-celulas-t.html 


1. Biorender
2. Explicar modelo
3. Explicar variable de control
4. Sacar conclusiones
