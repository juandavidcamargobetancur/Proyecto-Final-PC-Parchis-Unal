# Proyecto-Final-PC-Parchis-Unal
Este repositorio contiene un juego de Parchís en Python con modo consola y gráfico usando Tkinter. Permite partidas de hasta cuatro jugadores, gestionando movimientos, capturas y condiciones de victoria automáticamente. El código es modular y fácil de entender. ¡Clona el repositorio y disfruta de una partida!

*NOTA: Dentro de la interfaz gráfica, siempre borrar todo el texto ya existente y ahi si escriibir el nuevo texto, ya sea número de jugadores, nombre de cada jugaro, etc*

Del tablero
El cual maneja la siguiente lógica:
68 casillas en las que todas las fichas pueden avanzar numeradas del 1 al 68 empezando por uno de los colores/equipos que escoja. Estas 68 casillas son todas
las casillas “externas” del tablero que se muestra, formalmente serían todas las casillas que colindan con uno de los cuatro cuadrados que están en las esquinas,
excepto por la casilla de seguro que se encuentra en medio.

De los dados
1) Los dados son dados usuales que están numerados del 1 al 6 (inclusive) y se lanzan
dos dados una vez por cada turno.

De cómo salen las fichas
1) Las fichas salen a su respectiva salida que está exactamente a 5 casillas del seguro inmediatamente anterior, en la imagen de referencia de la anterior sección se encuentra marcada como “Salida 1”.
2) Cada ficha sale con un cinco en los dados, ya sea repartido entre los dos dados o con el dígito completo en uno de los dos dados.
3) Solo se permiten dos fichas máximo por cada casilla. En caso de que ya haya dos fichas en la salida del respectivo equipo, las fichas solo podrán hacer movimientos. No obstante, las fichas también pueden moverse y desocupar el espacio para que salga otra ficha. Ejemplo: Supongamos que tenemos 2 fichas en la
salida 1, y tenemos en los dados 4 y 5, podemos mover 4 con una de las fichas y usar el otro 5 para sacar otra ficha.

De las reglas
1) Es obligatorio sacar una ficha de la cárcel cuando un 5 lo permita.

2) Si una ficha se encuentra en una salida o en un seguro, esta ficha no puede ser capturada por ninguna otra. Esta regla no se cumple cuando una ficha se encuentra en la salida de un equipo enemigo junto a una ficha del equipo enemigo y el equipo enemigo saca una ficha en su turno, éste capturará a la ficha que no pertenece a dicha salida. Por ejemplo: una ficha azul y una ficha roja se encuentran en la salida del equipo azul, es el turno del equipo azul y éste saca una ficha de la cárcel en este turno, la ficha roja es devuelta a la cárcel y se aplica la regla número 7 de esta sección.
3) Si dos fichas se encuentran en una casilla, tenemos estas posibilidades:
a) Son del mismo color/equipo, y por ende, forman un bloqueo siempre.
b) Son de diferente color/equipo pero se encuentran en un seguro o en una salida y entonces forman un bloqueo.
c) Son de diferente equipo y no se encuentran en ninguna casilla especial, por lo que la que la ficha que llega en segundo lugar a la casilla captura a la primera ficha y la envía a su respectiva cárcel.

4) Si existe un bloqueo en la casilla n, cualquier ficha (inclusive si es del mismo equipo) solo puede mover n-1 casillas máximo.
5) 5) Para mover una ficha a la llegada de cada respectivo equipo se necesita un número exacto de movimientos.
6) Si no existe un movimiento posible para ninguna de las fichas, ya sea porque existe un bloqueo o porque la casilla de llegada está a menos movimientos de lo que se obtuvo en los dados, entonces el turno simplemente pasa.
7) Si una ficha captura a otra, se pueden efectuar 20 movimientos con cualquier ficha de dicho equipo, siempre y cuando sea posible, considerando las reglas anteriores.
8) Si una ficha llega a su llegada, entonces se pueden efectuar 10 movimientos con cualquier ficha de dicho equipo, siempre y cuando sea posible, considerando las
reglas anteriores.
9) Los 20 movimientos o 10 movimientos otorgados por las anteriores dos reglas deben hacerse antes de cualquier otro movimiento.
10) Si el lanzamiento de los dados resulta en dados iguales (si los dados son par) entonces el lanzamiento del equipo actual se repite
11) Si un equipo saca tres pares consecutivos, la úlitma ficha que haya movido deberá regresar a la cárcel.

De la victoria
1) Un equipo ganará si todas sus fichas están en la llegada.

De los modos de juego
El juego se podrá jugar de dos formas:
1) En modo real: en dónde cada lanzamiento de los dados corresponde a un número aleatorio entre 1 y 6, y dónde pueden suceder una de estas cosas:
a) Se le da a escoger al jugador cuál ficha quiere mover con cada dado (cuando sea posible).
b) Se mueve automáticamente las fichas que estén obligadas a mover cuando exista solo una opción de movimiento.
c) No se hace ningún movimiento porque no es posible.
2) En modo desarrollador: dónde se escoge hacer un lanzamiento real, o bien, cuál es el número de los dados.
