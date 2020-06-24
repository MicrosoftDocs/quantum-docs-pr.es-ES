---
title: Qubit en Quantum Computing
description: Obtenga información sobre qubits, la unidad fundamental de información en la informática Quantum.
author: QuantumWriter
uid: microsoft.quantum.concepts.qubit
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 0b768190137aa4effe0fbac9c764dff60ec00e16
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269582"
---
# <a name="the-qubit"></a>Qubit

Del mismo modo que los bits son el objeto fundamental de la información en informática clásica, [*qubits*](https://en.wikipedia.org/wiki/Qubit) (bits de Quantum) son el objeto fundamental de la información en la informática Quantum.  Para comprender esta correspondencia, echemos un vistazo al ejemplo más simple: un único qubit.

## <a name="representing-a-qubit"></a>Representar un qubit

Aunque un bit o un dígito binario, puede tener un valor $ de $0 o $1 $ , un qubit puede tener un valor que sea cualquiera de estos o una superposición de quantum de $0 $ y $1 $ .

El estado de un único qubit se puede describir mediante un vector de columna bidimensional de normalización de unidad, es decir, la magnitud cuadrada de sus entradas debe sumar a $1 $ . Este vector, denominado Vector de estado de Quantum, contiene toda la información necesaria para describir el sistema Quantum de un solo qubit como un solo bit contiene toda la información necesaria para describir el estado de una variable binaria.

Cualquier vector de columna bidimensional de números reales o complejos con la norma $1 $ representa un posible estado de Quantum mantenido por un qubit. Por lo tanto, $ \begin{ bmatrix } \alpha \\ \\ \beta \end{ bmatrix } $ representa un estado qubit si $ \alpha $ y $ \beta $ son números complejos que satisfacen $ | \alpha | ^ 2 + | \beta | ^ 2 = 1 $ . Algunos ejemplos de vectores de estado de Quantum válidos que representan qubits incluyen

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } , \begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac{1 } {\sqrt{2 } } \end{ bmatrix } , \begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac { -1 } {\sqrt{2 } } \end{ bmatrix } , \text { y} \begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac{i } {\sqrt{2 } } \end{ bmatrix } . $ $

Los vectores de estado Quantum $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ y $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $ toman un rol especial. Estos dos vectores forman una base para el espacio vectorial que describe el estado de qubit. Esto significa que cualquier vector de estado de Quantum se puede escribir como una suma de estos vectores de base. En concreto, se puede escribir el vector $ \begin{ bmatrix } x \\ \\ y \end{ bmatrix } $ como $x \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } + y \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $. Si bien cualquier rotación de estos vectores serviría como una base perfectamente válida para el qubit, optamos por aplicar el privilegio a este, llamando al *cálculo*.

Tomamos estos dos Estados de Quantum para que correspondan a los dos Estados de un bit clásico, es decir, $0 $ y $1 $ . La Convención estándar es elegir

$ $0 \equiv \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \qquad 1 \equiv \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } , $ $

Aunque la opción opuesta se podría tomar igualmente bien. Por lo tanto, fuera del número infinito de vectores de estado de Quantum de un solo qubit posible, solo dos se corresponden con los Estados de los bits clásico; el resto de Estados de Quantum no lo hacen.

## <a name="measuring-a-qubit"></a>Medición de un qubit

Ahora que sabemos cómo representar un qubit, podemos obtener algunos Intuition por lo que estos Estados representan tratando el concepto de [*medición*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics). Una medida corresponde a la idea informal de "mirar" en un qubit, que contrae inmediatamente el estado de cuanto a uno de los dos Estados clásico $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ o $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $. Cuando se mide un qubit proporcionado por el vector de estado de Quantum $ \begin{ bmatrix } \alpha \\ \\ \beta \end{ bmatrix } $, obtenemos el resultado $0 $ con la probabilidad $ | \alpha | ^ 2 $ y el resultado $1 $ con la probabilidad $ | \beta | ^ 2 $ . En el resultado $0 $ , el nuevo estado del qubit es $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $; en el resultado $1 $ su estado es $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $. Tenga en cuenta que estas probabilidades suman hasta $1 $ debido a la condición de normalización $ | \alpha | ^ 2 + | \beta | ^ 2 = 1 $ .

Las propiedades de medición también significan que el signo global del vector de estado de Quantum es irrelevante. Negar un vector es equivalente a $ \alpha \rightarrow-\alpha $ y $ \beta \rightarrow-\beta $ . Dado que la probabilidad de medir $0 $ y $1 $ depende de la magnitud cuadrada de los términos, al insertar tales signos no se cambian las probabilidades. Estas fases se denominan normalmente [ `` *fases globales*' '](https://en.wikipedia.org/wiki/Phase_factor) y, por lo general, pueden tener el formato $e ^ {i \phi } $ en lugar de $ \pm 1 $ .

Una propiedad importante final de la medición es que no necesariamente daña todos los vectores de estado de Quantum. Si comenzamos con una qubit en el estado $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $, que corresponde al estado clásico $0 $ , la medición de este estado siempre producirá el resultado $0 $ y dejará el estado del cuanto sin cambios. En este sentido, si solo tenemos bits clásico (es decir, qubits que son $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ o $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $), la medición no daña el sistema. Esto significa que se pueden replicar los datos clásico y manipularlos en un equipo Quantum del mismo modo que en un equipo clásico. La capacidad, sin embargo, para almacenar información en ambos Estados a la vez es lo que eleva la informática Quantum más allá de lo que es posible de forma Robs y más equipos Quantum de la capacidad de copiar datos Quantum de forma indiscriminada, vea también [el teorema sin clonación](https://en.wikipedia.org/wiki/No-cloning_theorem).

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>Visualización de qubits y transformaciones mediante la esfera Bloch

Qubits también se puede mostrar en $3 $ D mediante la representación de la [*esfera Bloch*](https://en.wikipedia.org/wiki/Bloch_sphere) .  La esfera Bloch proporciona una manera de describir un estado de Quantum de un solo qubit (que es un vector complejo bidimensional) como un vector de valor real de tres dimensiones.  Esto es importante porque nos permite visualizar los Estados de qubit único y, por lo tanto, desarrollar un razonamiento que pueda ser muy valioso en la comprensión de los Estados de varios qubit (por desgracia, la representación de la esfera Bloch se interrumpe).  La esfera Bloch se puede visualizar de la siguiente manera:

<!--- ![](.\media\bloch.svg){ width=50% } --->
![Esfera Bloch](~/media/concepts_bloch.png)

Las flechas de este diagrama muestran la dirección en la que apunta el vector de estado de Quantum y cada transformación de la flecha puede considerarse como una rotación sobre uno de los ejes cardinales.
Aunque pensar en un cálculo de Quantum como una secuencia de giros es un Intuition eficaz, es difícil usar este Intuition para diseñar y describir algoritmos. Q # alivia este problema proporcionando un lenguaje para describir tales giros.

## <a name="single-qubit-operations"></a>Operaciones de qubit único

Los equipos Quantum procesan los datos aplicando un conjunto universal de las puertas de Quantum que pueden emular cualquier rotación del vector de estado de Quantum.
Esta noción de universalidad es similar a la noción de universalidad para la informática tradicional (es decir, clásica) en la que se considera que un conjunto de puertas es universal si se pueden realizar todas las transformaciones de los bits de entrada mediante un circuito de longitud finita.
En el cálculo de Quantum Computing, las transformaciones válidas que se pueden realizar en un qubit son las transformaciones y la medida de la unitario.
La *operación* de "contiguo" o la transposición de conjugada compleja es de importancia fundamental para la informática Quantum porque es necesario invertir transformaciones Quantum.
Q # refleja esto al proporcionar métodos para compilar automáticamente las secuencias de la puerta en su método contiguo, lo que evita que el programador tenga que controlar los contiguos de código en muchos casos. A continuación se muestra un ejemplo de esto:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Adj { // Auto-generate the adjoint of the operation
    H(qubit);
}
```

Aunque se trata de una operación de ejemplo trivial (como <xref:microsoft.quantum.intrinsic.h> , se puede ver cómo esto resulta muy útil para operaciones qubit más complicadas.
Para obtener más información, vea [operaciones y funciones](xref:microsoft.quantum.guide.operationsfunctions).

Solo hay cuatro funciones que se asignan de un bit a un bit en un equipo clásico. Por el contrario, hay un número infinito de transformaciones unitarios en un único qubit en un equipo Quantum. Por lo tanto, ningún conjunto finito de operaciones de cuantos primitivos, denominados [*puertas*](https://en.wikipedia.org/wiki/Quantum_logic_gate), puede replicar exactamente el conjunto infinito de transformaciones unitarios que se permiten en Quantum Computing. Esto significa que, a diferencia de la informática clásica, no es posible que un equipo Quantum implemente todos los programas Quantum posibles con un número finito de puertas. Por lo tanto, los equipos Quantum no pueden ser universales en el mismo sentido que los equipos clásico. Como resultado, cuando decimos que un conjunto de puertas es *universal* para la informática Quantum, realmente nos referimos a algo ligeramente más débil de lo que nos referimos a la informática clásica.
En cuanto a la universalidad, es necesario que un equipo Quantum solo *aproxime* cada matriz de unitarios dentro de un error finito mediante una secuencia de barrera de longitud finita.
En otras palabras, un conjunto de puertas es un conjunto de puerta universal si cualquier transformación de cuantificación se puede escribir aproximadamente como un producto de las puertas de este conjunto. Se requiere que, en el caso de los errores prescritos, existan las puertas $G _ {1 } , G_ {2, } \ldots, G_N $ del conjunto de puertas, tal que

$ $ G_N G_ {N-1 } \cdots G_2 G_1 \Approx U. $ $

Tenga en cuenta que, dado que la Convención para la multiplicación de matrices es multiplicar de derecha a izquierda la primera operación de la puerta en esta secuencia, $G _N $ , es en realidad la última que se aplica al vector de estado de Quantum. Lo que es más formalmente, suponemos que este conjunto de puertas es universal si por cada tolerancia de errores $ \epsilon>0 $ existe $G _ 1, G_N de $ modo que la distancia entre $G _N \ldots G_1 $ y $U es como $ máximo $ \epsilon $ . Idealmente, el valor de $N $ necesario para alcanzar esta distancia de $ \epsilon $ debe escalarse de poliles con un valor de $1/\ épsilon $ .

¿Qué aspecto tiene este conjunto de puerta universal en la práctica?  La forma más sencilla de este conjunto de la puerta universal para las puertas de qubit solo consta de dos puertas: la puerta Hadamard $H $ y la puerta de $T $ -Gate (también conocida como la puerta $ \ PI/8 $ ):

$ $ H = \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 & 1 \\ \\ 1 &-1 \end{ bmatrix } , \qquad T = \begin{ bmatrix } 1 & 0 \\ \\ 0 & e ^ {i \ PI/4 } \end{ bmatrix } .
$$

Sin embargo, por razones prácticas relacionadas con la corrección de errores de Quantum puede ser más conveniente considerar un conjunto de puertas mayor, es decir, uno que se puede generar mediante $H $ y $T $ .
Podemos clasificar las puertas de Quantum en dos categorías: Clifford Gates y $T $ -Gate.
Esta subdivisión es útil porque, en muchos esquemas de corrección de errores de Quantum, las puertas de Clifford, denominadas también, son fáciles de implementar, es decir, requieren muy pocos recursos en cuanto a operaciones y Qubits para implementar la tolerancia a errores, mientras que las puertas de Clifford no son muy costosas cuando se requiere tolerancia a errores. El conjunto estándar de puertas de Clifford de un solo qubit, [incluido de forma predeterminada en Q #](xref:microsoft.quantum.libraries.standard.prelude), incluye

$ $ H = \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 & 1 \\ \\ 1 &-1 \end{ bmatrix } , \qquad S = \begin{ bmatrix } 1 & 0 \\ \\ 0 & i \end{ bmatrix } = T ^ 2, \qquad X = \begin{ bmatrix } 0 &1 \\ \\ 1 & 0 \end{ bmatrix } = HT ^ 4H, $ $

$ $ Y = \begin{ bmatrix } 0 &-i \\ \\ & 0 \END{ bmatrix } = T ^ 2HT ^ 4 HT ^ 6, \qquad Z = \begin{ bmatrix } 1&0 \\\\ 0 & -1 \end{ bmatrix } = T ^ 4.
$$

Aquí las operaciones $X $ , $Y $ y $Z $ se usan especialmente con frecuencia y se denominan [*operadores Pauli*](https://en.wikipedia.org/wiki/Pauli_matrices) después de Creator Wolfgang Pauli.
Junto con la puerta que no es de Clifford (la $ puerta $T), estas operaciones pueden componerse para aproximar cualquier transformación de unitarios en un solo qubit.

Para obtener más información sobre estas operaciones, sus representaciones de esfera Bloch y las implementaciones de Q #, consulte [funciones y funciones intrínsecas](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions).

Como ejemplo de cómo se pueden crear transformaciones de unitarios a partir de estas primitivas, las tres transformaciones que se ilustran en las esferas Bloch anteriores corresponden a la secuencia de la puerta \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \mapsto HZH \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $.

Mientras que la anterior constituye las puertas de primitivos más populares para describir las operaciones en el nivel lógico de la pila (piense en el nivel lógico como el nivel del algoritmo Quantum), a menudo resulta conveniente tener en cuenta las operaciones menos básicas en el nivel algorítmico, por ejemplo las operaciones más próximas a un nivel de descripción de función. Afortunadamente, Q # también tiene métodos disponibles para implementar unitaries de nivel superior que, a su vez, permiten la implementación de algoritmos de alto nivel sin descomponer explícitamente todo en Clifford y $T $ -puertas.

La más sencilla, tal primitiva, es el único qubit. Normalmente se consideran tres rotaciones de un solo qubit: $R _x $ , $R _y $ y $R _z $ . Para visualizar la acción de la rotación $R _x (\theta) $, por ejemplo, Imagine que señala el control de posición correcto a lo largo de la dirección del $ eje $x de la esfera Bloch y gira el vector con la mano a través de un ángulo de $ \ Theta/2 $ radianes. Este factor confuso de $2 $ surge del hecho de que los vectores ortogonales tienen una separación de $180 ^ \circ $ cuando se representan en la esfera Bloch, pero en realidad son $90 ^ \circ $ grados separados geométricamente. Las matrices unitarios correspondientes son:

\begin{align *} &R_z (\theta) = e ^ {-i\theta z/2 } = \begin{ bmatrix } e ^ {-i \ Theta/2 } & 0 \\\\ 0 & e ^ {i \ Theta/2 } \end{ bmatrix } , \\ \\ &R_x (\theta) = e ^ {-i\theta x/2 } = HR_z (\theta) H = \begin{ bmatrix } \cos (\ Theta/2) &-i\sin (\ Theta/2) \\ \\ -i\sin (\ Theta/2) & \cos (\ Theta/2) \end{ bmatrix } , \\ \\ &R_y (\theta) = e ^ {-i\theta y/2 } = SHR_z (\theta) HS ^ \dagger = \begin{ bmatrix } \cos (\ Theta/2) &-\sin (\ Theta/2) \\ \\ \sin (\ Theta/2) & \cos (\ Theta/2) \end{ bmatrix } . \end{align*}

Del mismo modo que se pueden combinar tres rotaciones de forma conjunta para realizar una rotación arbitraria en tres dimensiones, se puede observar en la representación de la esfera Bloch que cualquier matriz de unitarios puede escribirse como una secuencia de tres giros también. En concreto, para cada matriz de unitario $U $ existe $ \alpha, \beta, \gamma, \delta, de $ modo que $U = e ^ {i \alpha } R_x (\beta) R_z (\gamma) R_x (\delta) $. Por lo tanto $R _z (\theta) $ y $H $ también forman un conjunto de puertas universales, aunque no es un conjunto discreto porque $ \theta $ puede tomar cualquier valor. Por esta razón, y debido a las aplicaciones en la simulación Quantum, estas puertas continuas son cruciales para el cálculo de Quantum, especialmente en el nivel de diseño del algoritmo Quantum. Para lograr una implementación de hardware tolerante a errores, se compilarán en última instancia en secuencias de puerta discretas que se aproximan a estos giros.
