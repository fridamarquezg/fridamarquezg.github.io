---
layout: post
title: Algoritmo Agricultor
date: 2024-04-30 00:00:00 +0300
description: Segundo proyecto de la matería de Inteligencia Artificial # Add post description (optional)
img: ae.jpg # Add image post (optional)
tags: [AI, EvolutionaryAlgorithms, ClimateChange] # add tag
---
Segundo proyecto para la materia de Inteligencia Artificial.
Lo hice junto con mis amigos: Majo Velázquez (https://github.com/Majo2103) y Gerardo Guerrero (https://github.com/mellamanelpoeta)

### Objetivo

El objetivo principal del algoritmo evolutivo agrícola es maximizar el valor esperado de la utilidad del agricultor. Esto se logra optimizando cómo se distribuyen los cultivos en el campo, tomando en cuenta aspectos como el precio de mercado de cada producto, los costos de producción y la probabilidad de éxito en el crecimiento de los cultivos bajo diversas condiciones climáticas, incluyendo la necesidad de luz y agua para cada tipo de cultivo, así como la temporada óptima para su desarrollo.

![AE_1]({{site.baseurl}}/assets/img/motivo.JPG)


### Contexto

La agricultura en México se caracteriza por su variedad, la fuerza laboral que emplea y la alta calidad de sus productos. No obstante, el sector enfrenta desafíos significativos debido a su baja productividad en comparación con otros países, lo que limita su desarrollo. Además, la creciente vulnerabilidad al cambio climático podría incrementar la pérdida de cosechas y disminuir los recursos para el mantenimiento de cultivos cada año. Ante esta situación, el país no está plenamente preparado para atender las demandas de los agricultores o las necesidades alimentarias de su población. Estos desafíos pueden combatirse a través de la adopción de tecnologías que permitan la optimización de los recursos en el campo. Es esencial desarrollar proyectos que evalúen cómo las variaciones climáticas y las precipitaciones influyen en las cosechas, la producción agrícola y los ingresos de los trabajadores del campo.


### Marco Teórico

En México, algunos de los vegetales más consumidos y comercializados incluyen una variedad notable que se adapta tanto a los gustos culinarios locales como a las condiciones climáticas del país. Entre estos destacan el jitomate, la cebolla y el maíz, que son pilares en la dieta mexicana. También son muy populares el pepino, el chile y el pimiento, que no solo son esenciales para numerosos platillos tradicionales, sino que también tienen una fuerte presencia en los mercados locales. La zanahoria, la lechuga y la papa complementan esta lista, ofreciendo versatilidad tanto en la cocina como en la agricultura. Además, la calabaza, la espinaca, el nopal, el ajo, el betabel y la albahaca son ampliamente valorados por sus propiedades nutritivas y su adaptabilidad al suelo mexicano, consolidando su estatus como algunos de los vegetales más vendidos y preferidos en el país. La gama de precios por kilo de esta lista de vegetales oscila entre $10 y $120 pesos. La zanahoria se destaca como la opción más económica, mientras que la albahaca, se posiciona como la más cara. La mayoría de estos vegetales se encuentran en un rango de precio más común, entre los $30 y $50 pesos, lo que refleja una accesibilidad general para los consumidores en el mercado local.


En el ámbito de la optimización agrícola, existen varios modelos que se han desarrollado para abordar distintos aspectos de la planificación y la gestión de recursos. Algunos de estos modelos son los siguientes:

* Modelo de optimización de la cadena de suministro desarrollado por la empresa McKinsey & Company. Este modelo se centra en mejorar la eficiencia de las cadenas de suministro agrícolas mediante el uso de gemelos digitales, que simulan la cadena de suministro física para optimizar la planificación y programación en tiempo real, permitiendo así una respuesta rápida a los cambios inesperados y mejorando la toma de decisiones​.


* Uso de sistemas predictivos para la optimización de terrenos agrícolas desarrollados por la empresa Hindawi. Utilizando el aprendizaje de máquina, estos sistemas permiten optimizar el uso del terreno agrícola. Los modelos predictivos pueden ayudar a tomar decisiones basadas en datos sobre la gestión del terreno y el seguimiento del estado de los cultivos, lo que resulta una mejor gestión de los recursos​ disponibles.

Estos modelos se aplican con el objetivo de maximizar la eficiencia, reducir el desperdicio, y mejorar los rendimientos agrícolas, adaptándose a las condiciones de cada entorno y tomando en cuenta la necesidad agrícola. Nosotros decidimos enfocarnos en la utilización de algoritmos evolutivos para optimizar la utilidad del agricultor por medio de encontrar la distribución ideal de cultivos en su campo.


### Descripción de las Clases

La clase ‘Vegetal’ se utiliza para modelar las características esenciales de los vegetales en nuestro contexto agrícola. Cada objeto de esta clase representa un vegetal específico con atributos como nombre, cantidad de luz necesaria, cantidad de agua requerida, temporada de crecimiento, nivel de cuidado, precio por kilo y peso producido por metro cuadrado. 

La clase ‘Genotipo’ encapsula un conjunto de vegetales que representan la distribución de cultivos en un campo. Los objetos de esta clase están formados por un diccionario de vegetales como llave y el porcentaje del área que cada uno ocupa como su respectivo valor, y un valor numérico de utilidad que indica la eficiencia del genotipo bajo ciertas condiciones. La clase ofrece métodos para presentar la utilidad y detalles de los cultivos.

La clase ‘ParametrosAlgoritmo’ se encarga de gestionar los parámetros operativos del algoritmo evolutivo. Esta clase configura el número inicial de individuos en la población y el número de generaciones que el algoritmo ejecutará. 

![AE_2]({{site.baseurl}}/assets/img/clases.JPG)


### Implementación del algoritmo

Algunas funciones auxiliares son: ‘genera_numeros_random’ que genera una lista de n números aleatorios no negativos que suman 1.0. Y ‘crear_combinacion_aleatoria’, la cual crea un genotipo aleatorio con n vegetales de la lista proporcionada.

La función ‘evaluar’ determina la utilidad esperada de un genotipo de cultivos dados ciertos parámetros ambientales como la cantidad de luz solar, el agua disponible y la temporada. Para ello, calcula los costos de producción y la ganancia estimada, multiplicándola por la probabilidad de éxito del cultivo, calculada mediante la función ‘probabilidad_crecimiento’.

‘inicializar_poblacion’ crea una población inicial de n individuos, con genotipos generados aleatoriamente: una combinación aleatoria de cultivos con porcentajes asignados aleatoriamente, asegurando que la suma de los porcentajes sea igual a 100%.

La función ‘seleccionar’ evalúa la utilidad de cada individuo en la población y selecciona los mejores para el cruzamiento, devolviendo dos listas: los individuos seleccionados y los no seleccionados. ‘cruza_genotipo’, toma dos padres, cruza sus genotipos en un punto medio, y genera descendientes con porcentajes de cultivos ajustados. Por otro lado, ‘normalizar’, normaliza los porcentajes modificados durante la cruza para mantener la suma en uno
El ‘algoritmo_evolutivo’ utiliza las operaciones de inicialización, selección y cruzamiento para buscar el mejor genotipo, después de k generaciones. 


![AE_3]({{site.baseurl}}/assets/img/funciones.JPG)


Para el funcionamiento de ‘meta_algoritmo_evolutivo’ se utilizan: ‘evaluar_parametros’, función que evalúa un conjunto de parámetros del algoritmo evolutivo con base en la variación porcentual de las utilidades de k simulaciones bajo dichos parámetros, y termina la ejecución una vez que esta variación es menor al 1%. Mientras esta cota no se alcance, se usa ‘mutar_parametros’, la cual muta los parámetros del algoritmo evolutivo para explorar nuevas soluciones. El fin del meta algoritmo es encontrar una dupla de parámetros para el tamaño de la población y el número de generaciones que garantice la convergencia en el promedio de utilidad esperada en un tiempo óptimo.
El usuario interactúa con el sistema a través de un método llamado ‘ejecutar_meta_algoritmo_interactivo’. Este método sirve como interfaz central para todas las funciones del programa, proporcionando una experiencia interactiva que guía al usuario a través de cada etapa del proceso. Funciona como un manual interactivo, permitiendo al agricultor ingresar los datos requeridos de manera estructurada. Al finalizar el proceso, el método proporciona al usuario el resultado deseado.

Los parámetros que recibe el programa se dividen en dos: los parámetros del algoritmo evolutivo, como el tamaño de la población y la cantidad de generaciones, y los parámetros que ingresa el usuario para describir la situación del campo en donde se plantarán los vegetales. El método ‘ejecutar_meta_algoritmo_interactivo’ pide al usuario ingresar los siguientes parámetros:

* m2: área del terreno en metros cuadrados. 
* sol: la cantidad de luz solar que recibe el campo (Pleno sol o Media).
* agua: el nivel de agua que recibe el campo (Alto, Medio o Bajo).
* temp: temporada en la que interesa plantar los vegetales (Primavera/Verano u Otoño/Invierno)

Una vez ingresados los datos del campo, la función ‘meta_algoritmo_evolutivo’ calcula los parámetros óptimos que más adelante utilizará la función ‘algoritmo evolutivo’. Los parámetros que recibe la función ‘meta_algoritmo_evolutivo’ son los siguientes:

* min_cult: número mínimo de cultivos diferentes en cada genotipo. 
* m2, sol, agua, temp: parámetros anteriormente descritos, son dados por el usuario 


![AE_4]({{site.baseurl}}/assets/img/meta.JPG)


Los  parámetros que recibe la función ‘algoritmo_evolutivo’ son los siguientes:
* min_cult: número mínimo de cultivos diferentes en cada genotipo.
* pob_inicial: tamaño inicial de la población. Valor óptimo calculado por la función ‘meta_algoritmo_evolutivo’
* num_generaciones: número de generaciones del algoritmo evolutivo. Valor óptimo calculado por la función ‘meta_algoritmo_evolutivo’
* m2, sol, agua, temp: parámetros anteriormente descritos, son dados por el usuario


![AE_5]({{site.baseurl}}/assets/img/base.JPG)


Finalmente, el método proporciona al agricultor la distribución óptima de vegetales que se recomienda plantar para maximizar su utilidad bajo las condiciones especificadas.


![AE_6]({{site.baseurl}}/assets/img/funcionamiento.JPG)


### Resultados

Para realizar la evaluación del desempeño del algoritmo evolutivo consideramos la eficacia y la eficiencia: A través de las gráficas 1 y 2, se observa que al realizar pruebas con diferentes configuraciones en los parámetros (en el caso de las visualizaciones, al modificar la cantidad de agua disponible en el campo) es que la utilidad promedio alcanzada tienen una proporción directa dada por el tamaño de la población y el número de generaciones, además de que consistenteme se alcanza un valor óptimo cuando cualquiera de estos valores crece, lo que nos permite asegurar la convergencia. Por otro lado, la eficiencia también es un factor clave pues se espera que la solución aproximada dada por el algoritmo pueda alcanzarse en un tiempo razonable de tiempo. Afortunadamente, a través de la implementación del meta algoritmo que permite aproximar los parámetros óptimos mediante otro algoritmo evolutivo, logramos tener un buen comportamiento, permitiendo la ejecución en el orden de segundos para las 12 diferentes configuraciones que permitimos en cada campo.

![AE_3]({{site.baseurl}}/assets/img/convergencia.JPG)


### Discusión 

La mejor distribución del campo corresponde con el monocultivo sin importar los parámetros dados. Al encontrar un cultivo con altas probabilidades de crecimiento y un precio alto o razonable, el agricultor tiene incentivos a plantar más de dicho vegetal para maximizar su utilidad esperada. Sin embargo, no consideramos realista esta solución al representar un riesgo inherente el dedicar el 100% del área cosechable en un único cultivo, de manera que introdujimos la restricción de cultivos mínimos para garantizar la diversidad de la cosecha.

La sensibilidad del algoritmo al parámetro de población inicial es, en nuestra implementación,  equivalente a la que presenta el número de generaciones. Esto significa que la utilidad esperada converge a la misma razón a través del aumento de población inicial o el número de generaciones. 


### Limitaciones del estudio

El funcionamiento del algoritmo evolutivo agrícola presenta limitaciones que deben ser consideradas para una interpretación y aplicación responsables. La cantidad de vegetales registrados, las simplificaciones hechas en lo que respecta a la probabilidad de crecimiento y las necesidades de los cultivos, las consideraciones éticas y sociales, y la necesidad de evolución continua (en precios) son aspectos clave a tener en cuenta.


### Sugerencias para mejoras futuras

El algoritmo evolutivo agrícola se presenta como una herramienta valiosa para la agricultura sostenible y resiliente, ya que permite a los agricultores tomar decisiones estratégicas para adaptarse a los cambios climáticos y optimizar su producción. Sin embargo, para alcanzar su máximo potencial, el algoritmo requiere mejoras en tres aspectos principales:

* Incorporación de nuevos parámetros: El algoritmo debe ampliarse para considerar una gama más amplia de factores ambientales, como la temperatura del aire, la humedad, la radiación solar y la precipitación. Estos datos son cruciales para modelar con mayor precisión el crecimiento de los cultivos y los riesgos asociados a las condiciones climáticas adversas.


* Mejora de la precisión de la información: Es necesario refinar la información sobre los recursos disponibles, como la cantidad de agua, luz, mano de obra, así como de las probabilidades de éxito asociadas a cada escenario. Esto implica la integración de datos históricos de diversas fuentes, como sensores, registros agrícolas y estudios científicos.


* Desarrollo de simulaciones más precisas: Las simulaciones realizadas por el algoritmo deben ser más sofisticadas para reflejar con mayor exactitud las complejidades de los sistemas agrícolas. Esto incluye la consideración de factores como la interacción entre cultivos, la influencia de las prácticas de manejo y el impacto de las plagas y enfermedades.


### Resumen de hallazgos

El algoritmo evolutivo agrícola ofrece una solución prometedora para abordar los desafíos agrícolas contemporáneos, priorizando la optimización de la distribución de cultivos para maximizar la utilidad del agricultor. Si bien revela tendencias hacia el monocultivo, también destaca la importancia de mantener la diversidad para mitigar riesgos. Aunque se identifican áreas de mejora, como la expansión de parámetros y la precisión de datos, se espera que estas evoluciones fortalezcan aún más la efectividad y adaptabilidad del algoritmo. 


### Impacto del proyecto

El algoritmo puede ayudar a diversos agricultores mexicanos a enfrentar los efectos negativos del cambio climático mediante la selección adecuada de cultivos, un uso más eficiente de los recursos y la reducción de riesgos asociados a condiciones climáticas adversas. Fomentar una agricultura basada en la diversidad promueve la sostenibilidad agrícola al contribuir a la protección del suelo y, por ende, prolongar su vida productiva. Sin embargo, los agricultores no son los únicos beneficiarios potenciales del uso de este algoritmo, ya que toda oferta agrícola responde a una demanda. Nuestro proyecto puede contribuir al presentar alternativas para el cómputo de utilidades esperadas ante diferentes escenarios.



### Referencias

* Arce, S. (2020). “Análisis Comparativo de Precios y Costos de Producción de Hortalizas Cultivadas de Manera Orgánica y Convencional”. Recuperado de: https://www.scielo.sa.cr/pdf/ac/v44n2/0377-9424-ac-44-02-81.pdf

* McKinsey & Company. (2022). “Agriculture supply-chain optimization and value creation”. Recuperado de: https://www.mckinsey.com/industries/agriculture/our-insights/agriculture-supply-chain-optimization-and-value-creation

* HINDAWI. (2020).“Machine Learning–Based Predictive Farmland Optimization and Crop Monitoring System”. Recuperado de: https://www.hindawi.com/journals/scientifica/2020/9428281/

* World Bank. (2019). Agricultural innovation & technology hold key to poverty reduction in developing countries. Recuperado de https://www.worldbank.org/en/news/press-release/2019/09/16/agricultural-innovation-technology-hold-key-to-poverty-reduction-in-developing-countries-says-world-bank-report
