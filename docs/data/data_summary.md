# Reporte de Datos

Este documento contiene los resultados del análisis exploratorio de datos.

## Resumen general de los datos

* El dataset contine un total de 41.188 registros.
* En total se cuenta con 21 variables: 10 de tipo numérico (5 entero y 5 decimal) y 11 de tipo cualitativo o categórico (incluida la variable objetivo).
* No se registran valores nulos o faltantes en ninguna de las variables del dataset.
* Se cambia el nombre de las variables para un mejor entendimiento del contenido de cada una de ellas.

## Resumen de calidad de los datos

La calidad de la data contenida en el dataset es aceptable, ya que no registra valores nulos o faltantes.

En cuanto a los valores extremos en las variables numéricas:
* Edad: Los valores atípicos para esta variable son tolerables, teniendo en cuenta que solo se tienen 5 registros de personas menores de 18 años. De igual forma, teniendo en cuenta la esperanza de vida en los países europeos, es normal tener 10 registros de personas mayores de 90 años.
* Duración_últcontacto: La cantidad de registros con valores atípicos para esta variable son mínimos (Duración igual a 0 min o Duración mayor a 30 min), por lo cual no es necesario retirarlos de la base.
* Contactos_vigente:El número de contactos de la última campaña que superan las 20 llamadas (1 llamada por día hábil mes) no es representativa, por lo cual no es necesario eliminarlo de la base.
* Días_últcontacto: No registra valores atípicos.
* Contactos_anterior: No registra valores atípicos.
* Variables de mercado (Var_empleo, Indice_precios, Indice_confianza, Euribor3m,	Nro_Empleados): No registran valores atípicos.

## Variable objetivo

La variable objetivo corresponde a la columna Acepta_CDT, es una variable booleana con las opciones de Si (yes) y No. La distribución de la variable está desbalanceada, debido a que la opción No representa el 88,7% de la distribución versus el 11,3% que corresponde al Si.

![image](https://github.com/AndreaRubianoM/proyecto/assets/135787751/97bfc387-e118-4c7a-97b3-d3f01f23ddcf)

## Variables individuales

Variables Cuantitativas Cliente
* Edad: El promedio de edad de la base es de 40 años, se observa un mínimo de 17 años y un máximo de 98 años.
* Duración_últcontacto: El promedio es de 4,3 minutos con una variación muy alta. El contacto que más tiempo duró fue de 82 minutos.
* Contactos_vigente: Por lo menos en la última campaña se ha realizado un intento de contadto a los clientes. El promedio es aproximadamente 3 contactos.
* Días_últcontacto: Los valores de la mayoría de cuantiles corresponden a 999, lo cual implica que no ha habido un contacto reciente. Por lo anterior, esta variable no se tendrá en cuenta para el entrenamiento del modelo.
* Contactos_anterior: Los valores de la mayoría de cuantiles corresponden a 0, lo cual indica que la mayoría de clientes de esta base no fueron contactados en la campaña anterior; por lo cual, esta variable no se tendrá en cuenta para el entrenamiento del modelo.

![image](https://github.com/AndreaRubianoM/proyecto/assets/135787751/2fd034b8-e7a7-460b-9635-b501dd52ed6e)

![image](https://github.com/AndreaRubianoM/proyecto/assets/135787751/ce918a04-a0fc-4e79-a5c5-d20c01ceb416)

![image](https://github.com/AndreaRubianoM/proyecto/assets/135787751/f2957097-368a-4e5a-9a2c-f4061f13225a)


Variables Cuantitativas Mercado
Var_empleo, Indice_precios, Indice_confianza, Euribor3m,	Nro_Empleados

Validando el gráfico de correlaciones se encuentra que la siguientes variables están relacionadas con magnitud positiva:
* Var_Empleo y Euribor3m: 0.97
* Var_Empleo y Nro_Empleados: 0.91
* Euribor3m y Nro_Empleados: 0.95

Es normal que estás variables estén relacionadas ya que son indicadores macroeconómicos que dependen unos de otros. Si hay empleo, hay flujo de dinero, por tanto hay más demanda de producto y por tanto de crédito; lo cual se aprovecha para aumentar la tasa de interés interbancaria y, en consecuencia, la tasa de interés al consumidor.

Para este caso, y por tener una relación más directa con la decisión de si el cliente acepta o no el CDT (de acuerdo a lo visto gráficamente), se dejará únicamente como variable de estudio Euribor3m; es decir, se eliminarán para la fase de entrenamiento las variables Var_Empleo y Nro_Empleados.

Así mismo, validando el gráfico de correlaciones se encuentra que la siguientes variables están relacionadas con magnitud positiva:
* Euribor3m e Indice_precios: 0.69
* Var_Empleo e Indice_precios: 0.78

En este caso, y de acuerdo a lo explicado anteriormente, al tener también una correlación positiva con Euribor3m, se eliminará la variable Indice_precios.

![image](https://github.com/AndreaRubianoM/proyecto/assets/135787751/64b8b472-69f9-4431-ab4d-5c71e504f8ed)

![image](https://github.com/AndreaRubianoM/proyecto/assets/135787751/1b0463d2-de91-4958-bef5-d38e029bcc58)
![image](https://github.com/AndreaRubianoM/proyecto/assets/135787751/5e29ee23-c47a-40f5-9fd7-0844a5fad7c9)

Variables Cualitativas Clientes
* Activ_económica: Las actividades de mayor participación son las administrativas, operativas y técnicas.
* Estado_civil: Un poco más del 50% de la población es casada.
* Nivel _educativo: La mitad de la población se ubica entre universitarios y bachilleres.
* Mora_actual: A pesar de que la mayoría de la población tiene un indicador positivo en cartera, el nivel de despoblamiento de la variable es alto. Por lo cual se puede considerar su eliminación del análisis.
* Créd_vivienda: La mayoría de los contactados tiene crédito de vivienda.
* Créd_personal: La mayoría de los contactados no tiene este crédito personal.
* Medio_contacto: La mayoría fue contactada a través del número celular.
* Mes_contacto: Al parecer la mayor parte de la campaña se llevó a cabo en el mes de mayo.
* Día_contacto: Todos los días de la semana el número de contactos es muy similar.
* Resultado anterior: La mayoría de personas no tenía un resultado previo, lo que nos lleva a pensar que son campañas de primera vez.

![image](https://github.com/AndreaRubianoM/proyecto/assets/135787751/ec27dfbe-1440-4776-809f-26d638ece14a)
![image](https://github.com/AndreaRubianoM/proyecto/assets/135787751/e1c27ea8-eed1-4d80-88c8-166aa00b89d6)

![image](https://github.com/AndreaRubianoM/proyecto/assets/135787751/4f262db4-5d40-4a57-88b1-ea93a1287114)
![image](https://github.com/AndreaRubianoM/proyecto/assets/135787751/077aaca3-ffd8-4bd1-a5be-ae7599b8e0c0)

## Relación entre variables explicativas y variable objetivo

A contnuación se encuentra el gráfico de análisis de correlaciones para el total de variables numéricas del dataset. Este análisis nos permitió validar la relación directa existente entre las variables de mercado.

![image](https://github.com/AndreaRubianoM/proyecto/assets/135787751/b8ee37c9-3f8a-4d52-aa30-c6a4684947bf)


