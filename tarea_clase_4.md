# Tareas clase 4

Veamos un ejemplo de Speedup:

El tiempo que tarda en ejecutarse un programa en A es 10 seg. y 15 seg. en B.

```
Tiempo de ejecución B / Tiempo de ejecución A = 15 seg. / 10 seg. = 1.5
```

**Entonces, A es 1.5 veces más rápido que B**.

Ahora, pasemos a los ejercicios:

1. Un programa tarda 10 segundos en
ejecutarse en el ordenador A, que tiene una frecuencia de reloj de 2 GHz Queremos que el computador B tarde 6 segundos en ejecutar el mismo programa. En este caso, se puede introducir una mejora para incrementar la frecuencia de reloj, pero esto supone que el ordenador B necesitará 1,2 veces más ciclos de reloj que el A para ejecutar el mismo programa. ¿Cuál es la frecuencia de reloj que cumple con estas condiciones?
2. Tenemos dos implementaciones del mismo ISA. La implementación A tiene un periodo de reloj de 250 ps y un CPI de 2 para un programa, mientras que la B tiene un periodo de reloj de 500 ps y un CPI de 1,2 para el mismo programa. ¿Qué ordenador es más rápido ejecutando este programa y por cuánto?
3. Un diseñador de compiladores se tienen que decidir entre dos secuencias de código para un computador particular. Se proporcionan los siguientes datos:

    | Tipo de instrucción | A | B | C | 
    |:-------------------:|:-:|:-:|:-:| 
    | CPI                 | 1 | 2 | 3 |

    Número de instrucciones por cada clase de instrucción:
 
    
    | Secuencia de código  | A | B | C |
    |:-------------------:|:-:|:-:|:-:| 
    | 1 | 2 | 1 | 2 |  
    | 2 | 4 | 1 | 1 |

    ¿Qué secuencia de código ejecuta más instrucciones?
    ¿Cuál es el CPI de cada secuencia? ¿Cuál es más rápida?
