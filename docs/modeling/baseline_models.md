# Reporte del Modelo Baseline

Este documento contiene los resultados del modelo baseline.

## Descripción del modelo

El modelo baseline corresponde a una Regresión Logística que nos permite validar el resultado del modelo de clasificación. Se utiliza la característica de Balanceo de clases, incluida como un parámetro de dicho algoritmo.

## Variables de entrada

Edad,	Activ_económica,	Estado_civil,	Nivel_educativo,	Mora_actual,	Créd_vivienda,	Créd_personal,	Medio_contacto,	Mes_contacto,	Día_contacto,	Duración_últcontacto, 	Contactos_vigente, 	Resultado_anterior,	Indice_confianza,	Euribor3m.

## Variable objetivo

Acepta_CDT.

## Evaluación del modelo

### Métricas de evaluación

Matriz de confusión, Score F1. Se usa esta métrica debido al desbalanceo en la distribución de la variable objetivo.

### Resultados de evaluación

Score F1 promedio Macro 75%
![image](https://github.com/AndreaRubianoM/proyecto/assets/135787751/b121de42-0053-4912-9abe-5448e62aa220)


## Análisis de los resultados

La métrica de desempeño nos arroja un resultado aceptable (se encuentra por encima del 70%). Se observa un buen nivel de predicción para ambas clases, donde el Si tiene un % de predicciones acertadas es del 88%. Para la clase Noel % de predicciones correctas es del 86%.

## Conclusiones

Sería importante alcanzar un número de predicciones acertadas más alto para la clase Si. Teniendo en cuenta el objetivo del modelo, y la naturaleza del probelma analizado, no es tna crítico un número alto de Falsos Negativos.
