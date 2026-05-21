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
Un tipo particular de sistema din\'{a}mico es aquel que exhibe diferentes conjuntos compactos invariantes para diferentes valores en sus parámetros y/o condiciones iniciales. A continuación, se presenta un modelo matemático desarrollado con base en el sistema presa-depredador de Lotka-Volterra y el sistema de Itik y Banks 2010, el cual está compuesto por las siguientes tres EDOs de primer orden:

        dx = r1*x*(1 - b1*x) - a12*x*y - a13*x*z; 	(1)
        dy = r2*y*(1 - b2*y) - a21*x*y;			(2)
        dz = (r3 - a31)*x*z - d3*z + rho;		(3)

donde la Ecuación (1) representa la población de células anormales o patalógicas, la Ecuación (2) la población de células normales o sanas y la Ecuación (3) la población de células efectoras (citotóxicas o NK). La descripción de cada ecuación del sistema se realiza a continuación. Primero, se observa en la estructura de las Ecuaciones (1) y (2) que el desarrollo de las poblaciones de c\'{e}lulas patológicas y células sanas se describe por la ley de crecimiento logístico con tasas de crecimiento definidas por r1 y r2, y las capacidades de carga máxima establecidas por b1^-1 y b2^-1, respectivamente; mientras que en la Ecuación (3) describe el crecimiento de las células efectoras mediante la ley de acción de masas con una tasa r3. Los términos xy representan la competencia
de recursos entre células patológicas y células sanas, ambas se eliminan a unas tasas dadas por a12 y a21, respectivamente. La eliminación de células patológicas por células efectoras y la supresión inmune se representan por los términos xz a unas tasas dadas por a13 y a31, respectivamente. Adicionalmente, las células efectoras tienen una muerte natural con una tasa d3. El parámetro de control rho representa la aplicación externa de un
tratamiento de inmunoterapia.


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

## Lista de archivos incluidos en el repositorio
1. Cuaderno computacional de MATLAB [.mlx].
2. Carpeta con imágenes de las simulaciones [.pdf].
3. Análisis matemático proyecto [.pdf].
4. Modelo de Simulink [.slx].
5. Datos del sistema biológico [.csv].
6. Archivo Eureqa [.fxp].

## Referencias
\[1] P. A. Valle, Syllabus para Gemelos Digitales, Tecnológico Nacional de México / Instituto Tecnológico de Tijuana, Tijuana, B.C., México, 2025. Permalink: https://biomath.xyz/course/

\[2] Itik, M., & Banks, S. P. (2010). Chaos in a three-dimensional cancer model. international Journal of bifurcation and chaos, 20(01), 71-79. https://doi.org/10.1142/S0218127410025417

\[3] Bryan, Kurt. Differential equations: A toolbox for modeling the world. Simiode, 2022. Permalink: https://www.simiode.org/resources/8307 
