# Reporte del Modelo Final

## Resumen Ejecutivo

En esta sección se presentará un resumen de los resultados obtenidos del modelo final. Es importante incluir los resultados de las métricas de evaluación y la interpretación de los mismos.

## Descripción del Problema

Justificación

La entidad sobre la cual se desea realizar el análisis de la información es un banco de Portugal.
Al respecto es importante entender la dinámica de negocio de una institución finaciera cuyas tareas principales consisten es administrar el dinero que reciben de parte de sus clientes y otorgar préstamos haciendo uso de los mismos recursos, lo cual se conoce como intermediación financiera.
Para poder llevar a cabo esas actividades, estas entidades le cobran un interés a quienes requieren dichos préstamos; y a su vez, le otorgan un rendimiento a quienes depositan su dinero con ellos.La diferencia entre estos dos valores, es la ganancia del negocio.

Objetivo principal

Teniendo en cuenta la importancia de la captación en el equilibrio financiero de un banco, este proyecto tiene como objetivo realizar un análisis detallado del resultado de las campañas de marketing telefónico realizadas previamente para el ofrecimiento de CDT's (Certificados de depósito a término) a clientes activos del banco con productos de crédito.

Objetivos específicos

*   Encontrar características de cliente que permitan determinar un perfil con mayor interés en la adquisición de este producto (CDT).
*   Validar patrones en las campañas de marketing que influyan en la efectividad de la aceptación del CDT.

## Descripción del Modelo

El modelo final que se usó corresponde a un SVC, una máquina de soporte vectorial para clasificación. Teniendo en cuenta que la variable objetivo se encuentra desbalanceada, se usó el parámetro del algotitmo que nos permite ajustar este tema.

## Evaluación del Modelo

Matriz de confusión: Score F1. Se utliza esta métrica teniendo en cuenta que es la recomendada para problemas de clasificación con desbalanceo de clases.

![image](https://github.com/AndreaRubianoM/proyecto/assets/135787751/369b87ec-b9bc-44d3-9da5-71468e328c8e)

## Conclusiones y Recomendaciones

Si bien la métrica Score F1, se encuentra 1 punto por debajo del valor alcanzado para el Modelo de regresión logística (74% vs 75%), se observa una mejora en el % de predicciones correctas para la clase Si, la cual corresponde a 92% vs 88% alcanzado con el modelo base. Para la clase No este % disminuyó a 84% vs 86% alcanzado con el modelo base. Como se explicaba anteriormente, de acuerdo al objetivo a alcanzar, conviene más la mejora en las predicciones correctas para la clase Si. Por lo anterior este modelo se ajusta a las necesidades actuales de la empresa y el objetivo del proyecto en particular.
