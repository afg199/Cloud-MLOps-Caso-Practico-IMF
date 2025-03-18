# Cloud-MLOps-Caso-Practico-IMF
Trabajo final para la asignatura de Cloud - ML Ops del Máster de Inteligencia Artificial 

Importante



En esta práctica se va a usar Microsoft Azure para realizar los ejercicios. Para ello hay que crear una cuenta de prueba en https://azure.microsoft.com/es-es/free/. Se dispondrá de 170 € de gasto durante un mes completo.

Para poder acceder a esta prueba gratuita se pedirá una tarjeta de crédito. Aquí hay que hacer varias consideraciones:



Una vez dado de alta, se cargará 1 € en la cuenta de la tarjeta que se devolverá inmediatamente. No hay por qué alarmarse, este procedimiento es normal y simplemente se hace a efectos de comprobar que la tarjeta de crédito proporcionada es correcta.


El tener que proporcionar un número de tarjeta no significará que una vez agotado el crédito se hagan cargos de forma automática. Si se agota el crédito de 170 €, Azure avisará y preguntará si se desea a partir de ese momento pasar a la modalidad de pago por uso. En caso de no querer pasar a la modalidad de pago por uso, se borrará todo el trabajo hecho hasta ese momento (máquinas virtuales creadas, espacios de almacenamiento, bases de datos…).


Además de los 170 € de crédito mensual, se tiene acceso a una capa de servicios gratuitos durante 12 meses de forma limitada.


Se pueden consultar las dudas acerca de este periodo de prueba, así como los servicios gratuitos a los que se tiene acceso durante un año y sus limitaciones, en: https://azure.microsoft.com/es-es/free/free-account-faq/ 

Para asegurarse de que se ha concedido el crédito, al entrar deberá haber un botón en la parte superior que pedirá actualizar. No hay que pulsar ese botón, tan solo localizarlo como indicador de que se ha concedido el crédito de 170 € durante un mes.



Enunciado



Una empresa de 15 trabajadores con sus sistemas albergados en la nube (ERP, CRM, control de stock…) quiere implantar una estrategia de analítica también en la nube (Azure).



Para ello desarrolla una serie de funciones serverless que se ejecutan periódicamente a las 2:00 am, y donde se copia la información de las bases de datos a ficheros CSV en un almacenamiento distribuido y se puede desde ahí leerlo con cualquier herramienta (notebook, diseñadores, AutoML…) e incluso enviar datos a aplicaciones de BI como Celonis y PowerBI.



En cuanto a sus necesidades de IA, necesitan un sistema predictivo para las ventas futuras, para así poder determinar el stock que necesitarán, otro que les prediga los clientes con una alta probabilidad de contratar un producto vía telefónica y, por último, varios algoritmos que se entrenan y se ejecutan de forma puntual para determinar determinados aspectos del negocio (como qué clientes tienen más propensión a aceptar una determinada oferta o un estudio especial de algún aspecto del negocio).



Considérese que el dataset que indica si un cliente va a contratar o no un producto vía telefónica es bank marketing, ubicado en https://archive.ics.uci.edu/ml/datasets/Bank%2BMarketing, y en concreto, “bank-full.csv”.





Se pide



Contestar justificando todas y cada uno de los apartados y las decisiones tomadas:



1 - Describir la forma de productivizar cada modelo. ¿Qué tipo de herramienta se debería elegir para desarrollar cada modelo y por qué se ha elegido? ¿Cuál sería la forma de acceder a los modelos por parte de los usuarios? ¿Cada cuánto tendrían que reentrenarse?



2 - Describir el flujo de trabajo MLOps de los modelos. ¿Sería necesario en todos los modelos?



3 - ¿Qué cambios habría que hacer en los apartados anteriores si la empresa, en vez de 15 trabajadores, tuviese 10000?



4 - Productivizar el modelo de bank marketing. Hay dos opciones para elegir: mediante el diseñador de Azure o bien de forma manual en su propia máquina (serializando los modelos/transformaciones con Pickle).



Si el objetivo del modelo es lograr predecir previo a que se realice la llamada qué personas tienen una alta probabilidad de contratar, ¿se podría decir si hay alguna variable que no sea posible incluir en el modelo en producción?, ¿Cuáles son?
Probar varios modelos e ingeniería de características y dar con el modelo que mejor métrica presente.


Una vez elegido el mejor modelo, crear una llamada API para consultar el modelo. En caso de haber elegido hacer un modelo de forma manual, se tendrá que generar el código para responder a la llamada GET o POST con los nuevos datos. En caso de haber elegido hacerlo con Azure, se deberá crear el endpoint (hay que recordar que, posiblemente, al usar una cuenta gratuita, no se pueda ejecutar debido a que necesitaría más CPU de las que está permitido usar; no obstante, se deberá plantear la canalización y adjuntar captura de pantalla de ella aunque dé error).
