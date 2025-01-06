# Proyecto de práctica 6: Proyecto para trabajar en consola con los logs y la base de datos para una aplicación de taxis.

## Instrucciones para el Desarrollo del Proyecto
Este proyecto consta de dos partes. Consola y en Base de datos.

## Consola -  indicaciones:

## Ejercicio 1
Averiguar qué solicitudes han venido de una dirección IP. Una dirección IP consta de cuatro números separados por un punto. Necesitas direcciones que comiencen con "233.201".

Los logs están en un servidor remoto en logs/2019/12. No sabes qué día ocurrió el error.

Tu tarea es averiguar qué solicitudes fueron enviadas.

## Ejercicio 2
Se ha detectado un error en el sistema. Estaba activo el 12.30.2019. En ese momento, había errores 400 y 500. Tu tarea consiste en guardar los logs que se registraron durante este periodo en un archivo independiente.  

Después, debes poner estos logs en archivos por separado con base en los errores.

En el directorio de inicio del servidor remoto, crea un directorio llamado bug1.<br>
Pon todas las solicitudes que ocurrieron en el archivo main.txt en el directorio bug1.<br>
Dentro del directorio bug1 , crea un directorio events.<br>
Dentro del directorio events, crea archivos de error 400 y 500. Llama a estos archivos 400.txt y 500.txt, respectivamente. Identifica en ellos los logs utilizando el error correspondiente del archivo main.txt.

## Base de datos -  indicaciones:

🤷‍♀️ Base de datos de los viajes en taxi de Chicago:

<img src="https://raw.githubusercontent.com/Sandrarodriguezrey/Proyecto6_SQL/main/Cuadro%20Taxi%20relacional.JPG" alt="Cuadro relacional de datos de taxi" width="600"/>


**La tabla neighborhoods, con información sobre los barrios de la ciudad:** <br>

**neighborhood_id:** código del vecindario.<br>
**name:** nombre del vecindario.<br>

**La tabla cabs, con información sobre los taxis:** <br>

**cab_id:** código único del vehículo.<br>
**vehicle_id:** identificador técnico del vehículo.<br>
**company_name:** la compañía dueña del automóvil.<br>

**La tabla trips, con información sobre viajes:** <br>

**trip_id:** código de viaje. <br>
**cab_id:** el código del automóvil usado para el viaje.<br>
**start_ts:** fecha y hora del inicio del viaje (tiempo redondeado a la hora más próxima).<br>
**end_ts:** fecha y hora del fin del viaje (tiempo redondeado a la hora más próxima).<br>
**duration_seconds:** la duración del viaje en segundos.<br>
**distance_miles:** la distancia del viaje en millas.<br>
**pickup_location_id:** el código del vecindario donde inició el viaje.<br>
**dropoff_location_id:** el código del vecindario donde terminó el viaje.<br>

**La tabla weather_records (registros meteorológicos), con información sobre el clima:** <br>

**record_id:** código del registro de observación meteorológica.<br>
**ts:** fecha y hora de la observación (tiempo redondeado a la hora más próxima).<br>
**temperature:** temperatura a la hora de la observación.<br>
**description:** una breve descripción de las condiciones meteorológicas (p. ej., lluvia ligera o nubes dispersas).<br>

## Ejercicio 1
Tienes una base de datos con los viajes en taxi. El plan era tener 10,550 vehículos disponibles, lo que cubre la demanda del usuario; sin embargo, el equipo recibió muchas quejas de que no había vehículos suficientes. ¿Cuántos taxis hay actualmente en las calles? La información sobre todos los automóviles suficientes está en la tabla cabs.<br>

Ve al servidor remoto.<br>
Conéctate a la base de datos chicago_taxi <br>
Cuenta el número total de automóviles en la tabla cabs. Recuerda que un automóvil podría pertenecer a distintas compañías.

## Ejercicio 2
En la tabla cabs, cuenta el número de automóviles de cada compañía. Ordena los valores en orden descendente. El equipo piensa que algunas compañías no tuvieron suficientes automóviles disponibles.<br>

Devuelve las compañías con menos de 100 automóviles. Llama cnt (contados) al campo con el número de automóviles, y company_name al campo con el nombre de la compañía.<br>

Para resolver el problema, utiliza el operador HAVING, una analogía de WHERE para las funciones agregadas. Estudia la documentación para aprender cómo funciona el operador:<br>

## Ejercicio 3
La aplicación de taxis calcula el coeficiente del costo del viaje. Si el clima es bueno, el valor del coeficiente es 1. Si llueve o hay tormentas en el exterior, el coeficiente aumenta a 2. El equipo tiene una hipótesis de que hay un error en el cálculo del coeficiente. Para revisar el cálculo del coeficiente, el equipo necesita una selección de datos: el área de desarrollo puede comparar el coeficiente con los datos en los logs y corregir el bug. Tu tarea es obtener una selección.

Para hacerlo:<br>

Obtén una descripción de las condiciones meteorológicas de la tabla weather_records para cada hora.<br>
Divide todas las horas en dos grupos a través del operador CASE: Está Bad ("mal") si el campo description contiene las palabras "rain" (lluvia) o "storm" (tormenta); Good ("bien"), para todas las demás horas.<br>
Pon el nombre weather_conditions al campo resultante.<br>
La tabla resultante debe tener dos campos: fecha y hora (ts) y weather_conditions.<br>

Haz una selección para el periodo entre 11-05-2017 12:00 a. m. a 11-06-2017 12:00 a. m.

## Ejercicio 4
La compañía de taxis comienza a reportar que la ganancia que reciben no coincide con los datos que proporciona la aplicación. El equipo de desarrollo sugiere que el problema puede estar en los datos sobre el número de viajes.

Para determinar si hay un bug, debes obtener la selección del número de viajes de cada compañía de taxi para los días 15 y 16 de noviembre de 2017.

Devuelve el campo company_name. Nombra trips_amount (cantidad de viajes) al campo con el número de viajes y devuélvelo.<br>
Organiza en orden descendente los resultados obtenidos en el campo trips_amount.

## Se adjunta Respuesta en PDF   

<img src="https://github.com/Sandrarodriguezrey/Proyecto6_SQL/blob/main/Proyecto%20Sprint%206%20Sandra%20Rodriguez.pdf">

## Herramientas utilizadas:

**SQL** Para el diseño de casos de pruebas y la gestión de errores.

**Hojas de calculo** Google sheets.

# CONCLUSIÓN

En este proyecto he fortalecido mis competencias en bases de datos y en análisis de logs, conociendo un enfoque más integral sobre cómo manejar la calidad del software desde diferentes perspectivas.
Me ha proporcionado una valiosa experiencia práctica en la aplicación de SQL y en la gestión de bases de datos, que son habilidades importantes para cualquier ingeniero de calidad.

************


:sparkles: **GRACIAS** por visitar este proyecto. 

**MUCHAS ESTRELLITAS DE LUZ PARA TI** :star2::star2::star2::star2:

**Si tienes preguntas puedes contactarme en mi Linkedln. :point_right: www.linkedin.com/in/sandrarodriguez461428179**





