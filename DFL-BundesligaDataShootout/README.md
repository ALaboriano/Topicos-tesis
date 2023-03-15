

# **[DFL - Bundesliga Data Shootout](https://www.kaggle.com/competitions/dfl-bundesliga-data-shootout).**
*Identificar jugadas de fútbol a partir de secuencias de video.*

**1.	Objetivo.**
	Detectar los pases dados en un partido de fútbol (incluyendo los laterales o saques de banda y los centros) y retos en partidos originales de la Bundesliga.
	Desarrollar un modelo de Visión Computacional que puede clasificar automáticamente estos eventos en largas grabaciones de video.

**2.	Contexto.**
	Actualmente, la mayoría de los datos de eventos son recopilados manualmente por operadores humanos, quienes recopilan datos en varios pasos y a través de numerosos empleados involucrados. Este proceso manual tiene espacio para la innovación, ya que en su forma actual implica una gran cantidad de recursos y múltiples iteraciones/verificaciones de calidad. Como resultado, la recopilación de datos de eventos generalmente se reserva solo para competencias profesionales.

**3. Métrica de evaluación**

**4. Descripción de los eventos.**
	Una jugada (Play), describe el intento de un jugador de cambiar el control del balón a otro jugador de su equipo. Una jugada puede ejecutarse como un Pase (Pass) o un centro (Cross).  
	**Cross**. El hecho de que una jugada sea un centro, depende de las posiciones del jugador que centra y del jugador que recepciona el centro. El jugador que realiza el centro, debe estar ubicado aproximadamente dentro de una de las cuatro zonas de las cuales se puede centrar (Crossing Player Zone). Las cuatro zonas están delimitadas por las líneas de banda, la prolongación paralela a las líneas de banda de las líneas de penal, las líneas de meta y  las líneas imaginarias que se forman en el último cuarto del campo de fútbol tomando como base la línea central. El jugador destinatario o el que recibe el centro, debe estar ubicado aproximadamente dentro del área de penal. Además la longitud de la distancia recorrida por el balón debe ser entre media (10-30 metros)  o larga (más de 30 metros) y la altura de la pelota jugada debe ser alta (Se debe jugar por encima de la rodilla de los jugadores). Para clasificar una jugada como centro, cuando la pelota es interceptada por un rival, no es decisiva la altura real o distancia recorrida, sino la altura o distancia prevista.  
	**Pass**. Un pase es cualquier intento de cambiar el control del balón a otro miembro de su equipo, que no tiene las características necesarias para ser un centro.  
	Además, cada acción de juego, ya sea un pase o un centro se ejecuta dentro de un contexto, lo que convierte en una jugada  con balón en movimiento = Open Play, o en una jugada con balón parado (tiros de esquina o corners = Corner Kick, tiros libres = Free Kick.)    
	Un corner se refiere a la situación en la que se ejecuta la jugada para reiniciar el juego, después de que el balón saliera sobre la línea de meta tras el toque o roce en un jugador del equipo rival. La pelota debe patearse desde la esquina del banderín de lcorner por la que salió el balón y debe estar totalmente quieta al momento de ejecutar el corner.    
	Una jugada abierta = Open Play se refiere a cualquier jugada con balón en movimiento.  
	**4.2. Trow-Ins= Saque de Banda.**  
	Se refiere a una situación en la cual el juego se reinicia, después de que el balón salió por la línea de banda tras el toque o roce en un jugador del equipo contrario. El balón debe lanzarse con las manos, por detrás y por encima de la cabeza del jugador ejecutor.  
	**4.3. Challenge = Desafíos =Recuperos.**  
	Un desafío o un reto, es una acción de juego en la que un jugador intenta recuperar el balón para su equipo. Una recuperación requiere que uno de los dos jugadores que disputan el balón consiga su objetivo, ya sea consiguiendo la posesión del balón o cometiendo una falta al jugador contrario.
	Hay diferentes tipos de recuperaciones o desafíos:  
	●	**Opponent rounded = Oponente superado** (regate, sombrerito), Cuando el jugador que tiene el control del balón, permanece con él después del reto o jugada, es decir ha superado a su rival. También se consideran situaciones en las que el oponente no puede recuperar el balón (Los famosos sombreritos)   
	●	**Ball action carried Out = Balones Divididos.** Está acción se da cuando ninguno de los jugadores que intervienen tienen el control del balón, y al final uno de ellos consigue ganar el balón para su equipo.   
	●	**Fouled = Faltas**. Esta acción se da cuando el árbitro sanciona falta.   
	●	**Opponent dispossessed =  Recuperación del balón**. Un jugador que no tiene el balón le quita al otro que lo posee.   
	●	**Challenge during release of the ball = Despejes o bloques**. Se da cuando un jugador que no posee el balón lo intercepta o lo despeja.    
	●	**Possession retained during challenge = Retenciones de balón**. Se da cuando el jugador que posee el balón en una jugada de juego abierto no mueve el balón por un instante prolongado.

**5. Descripción de scripts**  
- ***1. Data download.ipynb***   
Código para descargar la data y almacenar en Google Drive 
- ***2. Data Understand.ipynb***   
Análisis exploratorio de la data, con el fin de entender la distribución de los eventos etiquetados en cada video.
- ***3. Image_Annotation.ipynb***  
Obtener una imagen por segundo de cada uno de los videos de entrenamiento, y almacenarlas en una carpeta dependiendo de la acción que ocurre en dicho segundo.
- ***Resumen Kaggle Competition.docx***   
Breve descripción de la competencia de Kaggle.
- ***tests***  
Carpeta dónde se almacena los scripts de validación de los procesos implementados.
- ***capturas***  
Imágenes auxiliares que sirven para la documentación.
