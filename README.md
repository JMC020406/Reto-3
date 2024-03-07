# Reto-3
## Pseudocódigo y Diagramas de flujo
Este reto consiste en utilizar los metodos de Pseudocódigo y de Diagramas de Flujo para demostrar dos diferentes problematicas de naturaleza matemática las cuales son: ¿es n un número primo? y ¿a n se le puede aplicar la raíz cuadrada?, n siendo un número entero cualquiera.

## Números Primos
### Pseudocódigo 1
Antes que nada quiero aclarar que el pseudocódico es un tipo de lenguaje más que nada casual y no tan riguroso en la programación. Se usa principalmente para generar una planeación de un códico cualquiera y que sea fácil de entender.

Para iniciar un pseudocódigo se coloca en una fila tres "acentos graves" (`) y eso seguido de la palabra "pseudocode", y para cerrar se pasa a una fila distinta y se colocan únicamente otros tres "acentos graves".

Ahora si voy a pasar a la parte de definir el pseudocódico de ¿cómo saber si un número cualuqiera n es un primo?

```pseudocode
  [Variables]
n:entero
i:entero

  [A calcular]
Inicio
Para i:= 2
  Mientras (i<n) Entonces
    Si modulo(n,i) == 0 Entonces
      Escribir("n no es un número primo")
    Sino
      si modulo (n,i) > 0 Entonces
        Escribir ("n si es un número primo")
  Fin Mientras
Fin
```
### Diagrama de flujo 1
Los diagramas son una representación más gráfica de lo que explica el pseudocódico, además se crean de una forma similar a estos: lo que se hace es colocar las mismas especificaciones de los tres "acentos graves" al inicio y al final y lo único diferente que toca hacer es cambiar "pseudocode" por un "mermaid".

```mermaid
graph TD;
    A(Inicio)--> B(número n)
    B(número n)--> C(i = 2)
    C(i = 2)--> D(i es menor que n)
    D(i es menor que n)-->E{¿Es el residuo de n/i = 0?}
    E{¿Es el residuo de n/i = 0?}-->|si|F(n no es un número primo)
    E{¿Es el residuo de n/i = 0?}-->|no|G(Hacer i+1 =i)
    G(Hacer i+1 =i)--> H{¿es i menor a n-1?}
    H{¿es i menor a n-1?}-->|si|E{¿Es el residuo de n/i = 0?}
    H{¿es i menor a n-1?}-->|no|I(n si es un número primo)
    I(n si es un número primo)-->J(fin)
    F(n no es un número primo)-->J(fin)
```

## Raices cuadradas
Ya que estos cálculos se vuelven un poco complejos al momento de hacerlo con decimales entonces pense en solo hacerlo con números enteros positivos (ya que los negativos no se les puede sacar raíz en los reales). Así que tanto el radicando como la raíz en estos calculos van a ser enteros positivos y aproximaciones a los valores reales.

### pseudocódigo 2
```pseudocode
  [Variables]
x:entero
d:parejas de dígitos de x hechas de derecha a izquierda
b:entero
r:entero
i:entero en el rango 1 hasta 9

  [A calcular]
Inicio
Dividir x en parejas de derecha a izquierda
Tomar primera pareja de la izquierda y denominarla d
Hacer d-b**2 == r y b**2 > r
  Si x tiene otra pareja (d) Entonces
    Hacer 100*r + d == d
    Hacer d-(20b+i)*i == r y 20B+i > r
    Hacer 10b + i == b
    Si x tiene otra pareja (d) Entonces
    Repetir
  Si no
    Escribir ("El número b es la raíz de x)
  Fin Mientras
Fin  
```

### Diagrama de flujo 2
```mermaid
graph TD;
  Z(inicio)-->A(número x es número entero)
  A-->B(número d es pareja de digitos sacados de separar x de
  derecha a izquierda en parejas de dígitos)
  B-->C(número b es la raíz)
  C-->D(número r es el residuo)
  D-->E(número i varia de 1 a 9)
  E-->F(Definir x)
  F-->H(Separar x en parejas de dígitos de derecha a izquierda)
  H-->I(Tomar primera pareja de dígitos a la izquierda y denominarla d)
  I-->J(Buscar b tal que d-b**2 == r , donde b**2 > r)
  J-->K{¿Aun quedan más parejas de dígitos?}
  K-->|si|L(Tomar siguiente pareja de la izquierda y hacer 100*r + d = d)
  K-->|no|M(El valor de b es la raíz de x)
  M-->|r == 0|N(b es la raíz exacta)
  M-->|r > 0|O(b es una aproximado de la raíz)
  L-->P(Tomar el resultado y calcular d-20b+i *i == r ,
  donde 20b+i > r .Para el calculo primero hay que resolver el
  20b+i y luego si seguir la jerarquía como siempre)
  P-->Q(Tomar resultado y hacer 10b + i == b)
  Q-->K
  O-->R(Fin)
  N-->R
```
