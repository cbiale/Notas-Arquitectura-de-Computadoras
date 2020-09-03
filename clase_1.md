# Arquitectura de Computadoras

## Grupo de trabajo

- Adjunto: Claudio Omar Biale (Teoría y lógica digital)
- Jefe de Trabajos Prácticos: Roberto Anibal Miño (Lógica digital)
- Ayudante de Primera: Viviana Arenhatch (Ensamblador usando RISC-V)
- Ayudante de Segunda: Melissa Kolb (Ensamblador usando RISC-V)

## Libro de Referencia

El libro de referencia es: **Computer Organization and Design: The Hardware/Software Interface, RISC-V edition** de *Hennessy* y *Patterson*.

El cuerpo principal del libro asume que han tenido un curso completo de diseño lógico. **:)**

No es nuestro caso, por ello comenzaremos con el apéndice B, que realiza una revisión sobre diseño lógico o lógica digital.

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

![](ondas.png)

Figura 1: Ejemplo de ondas cuadradas

Recordemos que la palabra **Bit** es la abreviatura de **Binary digIT** y binary significa base 2, no 10.

0 y 1 se denominan complementos entre sí, como lo es verdaderos y falsos (también activados / desactivados).

### Bloques lógicos: combinacionales vs secuenciales

Se puede pensar en un bloque lógico como una caja negra que recibe señales eléctricas y emite otras señales eléctricas. Hay dos tipos de bloques:

1- **Combinacional**: NO tiene elementos de memoria. Es mucho más simple que los circuitos con memoria ya que las salidas son una función solo de las entradas y no de cualquier estado preexistente. Es decir, si se presentan las mismas entradas, se obtendrán las mismas salidas.

2- **Secuencial**: Contiene memoria. El valor actual en la memoria se llama estado del bloque. La salida depende de la entrada Y del estado. Consideren, por ejemplo, leer una memoria RAM. Hay dos entradas: la dirección de memoria y la operación *(lectura vs escritura)*. Ciertamente, leer la ubicación 1011001 el lunes no necesariamente da el mismo resultado que leer la misma ubicación el martes.

Primero estudiaremos **bloques combinacionales** y luego estudiaremos **bloques secuenciales**. 
