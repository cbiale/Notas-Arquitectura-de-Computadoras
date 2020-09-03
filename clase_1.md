# Arquitectura de Computadoras

## Grupo de trabajo

- Adjunto: Claudio Omar Biale (Teoría y lógica digital)
- Jefe de Trabajos Prácticos: Roberto Anibal Miño (Lógica digital)
- Ayudante de Primera: Viviana María Arenhardt (Ensamblador usando RISC-V)
- Ayudante de Segunda: Melissa Kolb (Ensamblador usando RISC-V)

--------------------------------------------------------

## Libro de Referencia

El libro de referencia es: **Computer Organization and Design: The Hardware/Software Interface, RISC-V edition** de *Hennessy* y *Patterson*.

El cuerpo principal del libro asume que han tenido un curso completo de diseño lógico. **:)**

No es nuestro caso, por ello comenzaremos con el apéndice B, que realiza una revisión sobre diseño lógico o lógica digital.

--------------------------------------------------------

## Lógica digital

**Tarea**: deben descargar el simulador de lógica digital denominado **logisim-evolution** *(lo encuentran en el aula virtual)* y jugar con él. El botón de ayuda ofrece un tutorial, léanlo.

Ejecutar logisim *(asumo se encuentran en el directorio donde descargaron el archivo)*:
```
$ java -jar logisim-evolution.jar
```

Si no funciona, deben instalar `java` previamente. 

## Puertas, tablas de verdad y ecuaciones lógicas

*Tip: usamos de forma indistinta el nombre puertas o compuertas*

La palabra digital, cuando se usa en lógica digital significa discreto. Es decir, los valores eléctricos *(por ejemplo, voltajes)* de las señales en un circuito se tratan como números enteros *(normalmente solo 0 y 1)*. 

La alternativa es analógica, donde los valores eléctricos se tratan como números reales.

Para resumir, usaremos solo dos voltajes: **alto** y **bajo**. Una señal de alto voltaje se denomina: 1 o verdadera o establecida o afirmada. Una señal de bajo voltaje se denomina: 0 o falsa o no configurada o desactivada.

La suposición de que en cualquier momento todas las señales son 1 o 0 esconde una gran cantidad de ingeniería. Las ondas no son realmente cuadradas, pero como esto no es un curso de ingeniería, ignoraremos estos problemas y asumiremos ondas cuadradas.

![](./figuras/ondas.png)

Figura 1: Ejemplo de ondas cuadradas

Recordemos que la palabra **Bit** es la abreviatura de **Binary digIT** y binary significa base 2, no 10.

0 y 1 se denominan complementos entre sí, como lo es verdaderos y falsos (también activados / desactivados).

### Bloques lógicos: combinacionales vs secuenciales

Se puede pensar en un bloque lógico como una caja negra que recibe señales eléctricas y emite otras señales eléctricas. Hay dos tipos de bloques:

1- **Combinacional**: NO tiene elementos de memoria. Es mucho más simple que los circuitos con memoria ya que las salidas son una función solo de las entradas y no de cualquier estado preexistente. Es decir, si se presentan las mismas entradas, se obtendrán las mismas salidas.

2- **Secuencial**: Contiene memoria. El valor actual en la memoria se llama estado del bloque. La salida depende de la entrada Y del estado. Consideren, por ejemplo, leer una memoria RAM. Hay dos entradas: la dirección de memoria y la operación *(lectura vs escritura)*. Ciertamente, leer la ubicación 1011001 el lunes no necesariamente da el mismo resultado que leer la misma ubicación el martes.

Primero estudiaremos **bloques combinacionales** y luego estudiaremos **bloques secuenciales**. 

--------------------------------------------------------

## Tablas de verdad

Dado que la lógica combinatoria o combinacional no tiene memoria, es simplemente una función *(matemática)* de sus entradas a sus salidas.

Una forma común de representar una función es usar una tabla de verdad. Una tabla de verdad tiene una columna para cada entrada y una columna para cada salida. Tiene una fila para cada posible conjunto de valores de entrada. 

Entonces, si hay **N** entradas , hay **2N** filas. En cada una de estas filas, las columnas de salida tienen la salida para esa entrada.

*Pregunta: porque si hay N entradas voy a tener 2N filas*.

Una tabla de este tipo es posible solo porque hay solamente un número finito de valores de entrada posibles. Consideren intentar producir una tabla para la función matemática:

```
  y = f(x) = x^3 + 6x^2 - 12x - 3.5
```

Solo habría dos columnas *(una para x y otra para y)*, ¡pero sería necesario que hubiera un número infinito de filas!


### Un juego de números: ¿cuántas tablas de verdad posibles hay?

Comencemos con una tabla de verdad realmente simple, una correspondiente a un bloque lógico con una entrada y una salida.

¿Cuántas tablas de verdad diferentes existen para un bloque lógico de "una entrada y una salida" ?

Hay dos columnas *(1 entrada + 1 salida)* y dos filas *(2^1)*. Por lo tanto, la tabla de verdad se parece a la siguiente con los signos de interrogación completados.


| Entrada |	Salida |
|:---:|:---:|
| 0	| ? |
| 1 | ? |

Tabla 1: Tabla de verdad de 1 entrada y 1 salida.

Como hay dos signos de interrogación y cada uno puede tener uno de dos valores, solo hay 2 * 2 = 4 tablas de verdad posibles. Las mismas son:

1. La función constante 1, que tiene salida 1 *(es decir, verdadera)* para cualquier valor de entrada.
2. La función constante 0.
3. La función de identidad, es decir, la función cuya salida es igual a su entrada. Este bloque lógico a veces se denomina búfer.
4. Un inversor. Esta función tiene una salida opuesta a la entrada.

Muy pronto veremos símbolos para las dos últimas posibilidades.

**Tablas de verdad de 2 entradas y 1 salida**: Tres columnas *(2 + 1)* y 4 filas *(2 ^ 2)*.

¿Cuántas tablas de verdad existen? Es solo el número de formas en que puede completar las entradas de salida, es decir, los signos de interrogación. Hay 4 entradas de salida, por lo que la respuesta es 2 ^ 4 = 16.

| Entrada 1 | Entrada 2 |	Salida |
|:---:|:---:|:---:|
| 0	| 0	| ? |
| 0	| 1 | ? |
| 1	| 0	| ? |
| 1	| 1 | ? |

Tabla 2: Tabla de verdad de 2 entradas y 1 salida.

**Tablas de verdad más grandes**: en general, el número de signos de interrogación es el número de filas multiplicado por el número de columnas de salida.

¿Qué tal 2 entradas y 3 salidas?

- 2 + 3 = 5 columnas *(3 de ellas columnas de salida, donde aparecen los signos de interrogación)*.
- 2 ^ 2 = 4 filas.
- 4 * 3 = 12 signos de interrogación.
- 2 ^ 12 = 4096 posibilidades.

¿3 entradas y 7 salidas?

- 10 columnas *(3 de entrada y 7 de salida)*.
- 2 ^ 3 = 8 filas.
- 8 * 7 = 56 signos de interrogación.
- 2 ^ 56 posibilidades.

¿n entradas y k salidas?

- n + k columnas.
- 2 ^ n filas.
- n * k signos de interrogación.
- 2 ^ (2 n * k) posibilidades.

--------------------------------------------------------

## Álgebra de Boole

Vamos a usar una notación que se parece al álgebra para expresar funciones lógicas y expresiones que las involucran.

La notación se llama **álgebra booleana** en honor a **George Boole**.

Un **valor booleano** es un 1 o un 0.

Una **variable booleana** toma valores booleanos.

Una **función booleana** toma variables booleanas y produce valores booleanos.


https://cs.nyu.edu/courses/fall17/CSCI-UA.0436-001/class-notes.html

