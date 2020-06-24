---
title: Notación Dirac
description: Obtenga información sobre el uso de la notación Dirac para representar los Estados Quantum y para simular las operaciones Quantum.
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
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
ms.openlocfilehash: f9dddfa25e9fd1e3d8aaf92b2e3b17c96ed8b72a
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269513"
---
# <a name="dirac-notation"></a>Notación Dirac

Aunque la notación de vectores de columna es omnipresente en álgebra lineal, a menudo resulta incómodo en la informática Quantum, especialmente cuando se trabaja con varios qubits.  Por ejemplo, cuando se define $ \psi $ para que sea un vector, no se desactiva explícitamente si $ \psi $ es una fila o un vector de columna.  Por lo tanto, si $ \phi $ y $ \psi $ son vectores, es igualmente inclaro si $ \phi \psi $ se define incluso porque las formas de $ \phi $ y $ \psi $ pueden no estar claras en el contexto.  Además de la ambigüedad sobre las formas de vectores, la expresión de vectores simples con la notación algebraico lineal introducida anteriormente puede ser muy engorroso. Por ejemplo, si deseamos describir un estado $n $ -qubit en el que cada qubit toma el valor $0 $ , se expresaría formalmente el estado como 

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cdots \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } . $$  

Por supuesto, la evaluación de este producto tensores es poco práctica porque el vector se encuentra en un espacio exponencialmente grande y, por lo tanto, esta notación es, de hecho, la mejor descripción del estado que se puede proporcionar mediante la notación anterior.  

La [*notación Dirac*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) resuelve estos problemas presentando un nuevo lenguaje para ajustarse a las necesidades precisas de la mecánica de Quantum.  Por esta razón, se recomienda que el lector no vea los ejemplos de esta sección como una receta rígida de cómo describir los Estados de Quantum, sino que anime al lector a verlos como sugerencias que se pueden usar para expresar ideas de Quantum de manera concisa.

Hay dos tipos de vectores en notación Dirac: el vector *Bra* y el vector *les* , por lo que el nombre se debe a que, cuando se unen, forman un *freno* o producto interno.  Si $ \psi $ es un vector de columna, podemos escribirlo en la notación Dirac como $ \ket { \psi } $, donde $ \ket { \cdot } $ denota que es un vector de columna unitaria, es decir, un vector *les* .  Del mismo modo, el vector de fila $ \psi ^ \dagger $ se expresa como $ \bra { \psi } $. En otras palabras, $ \psi ^ \dagger $ se obtiene aplicando la conjugación compleja de modo de entrada a los elementos de la transposición de $ \psi $ . La notación bra-les implica directamente que $ \braket { \psi | \psi } $ es el producto interno de vector $ \psi $ con sí mismo, que es la definición $1 $ .  

En general, si $ \psi $ y $ \phi $ son vectores de estado Quantum, su producto interno es $ \braket { \phi | \psi } $, lo que implica que la probabilidad de medir el estado $ \ket { \psi } $ sea $ \ket { \phi } $ es $ | \braket { \phi | \psi } | ^ 2 $ .  

La Convención siguiente se usa para describir los Estados de Quantum que codifican los valores de cero y uno (los Estados de base de cálculo de qubit único):

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } , \qquad \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } = \ket{1 } .
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>Ejemplo: representar la operación Hadamard con la notación Dirac

La siguiente notación se usa a menudo para describir los Estados que son el resultado de aplicar la puerta Hadamard a $ \ket{0 } $ y $ \ket{1 } $ (que corresponden a los vectores de unidad de las direcciones $ + x $ y $-x $ en la esfera Bloch):

$ $ \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ 1 \end{ bmatrix } = H \ket {0 } = \ket { +}, \qquad \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ -1 \end{ bmatrix } = H \ket {1 } = \ket { -}.
$$

Estos Estados también se pueden expandir mediante la notación Dirac como sumas de $ \ket{0 } $ y $ \ket{1 } $:

$ $ \ket { +} = \frac{1 } {\sqrt{2 } } (\ket{0 } + \ket{1 } ), \qquad \ket { -} = \frac{1 } {\sqrt{2 } } (\ket{0 } -\ket{1 } ).
$$

### <a name="computational-basis-vectors"></a>Vectores de base de cálculo
Esto demuestra por qué estos Estados se suelen denominar *base de cálculo*: cada estado de cuanto se puede expresar siempre como suma de los vectores de base de cálculo y estas sumas se expresan fácilmente mediante la notación Dirac.  Lo contrario también es cierto en que los Estados $ \ket { +} $ y $ \ket { -} $ también forman una base para los Estados de Quantum.  Puede ver esto en el hecho de que

$ $ \ket{0 } = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}), \qquad \ket{1 } = \frac{1 } {\sqrt{2 } } (\ket { +}-\ket { -}).
$$

Como ejemplo de notación Dirac, considere el freno $ \braket{0 | 1 } $, que es el producto interno entre $0 $ y $1 $ .  Se puede escribir como 

$ $ \braket{0 | 1 } = \begin{ bmatrix } 1 & 0 \end{ bmatrix } \begin{ bmatrix } 0 \\\\ 1 \end{bmatrix} = 0. $ $

Esto indica que $ \ket{0 } $ y $ \ket{1 } $ son vectores ortogonales, lo que significa que $ \braket{0 | 1 } = \braket{1 | 0 } = 0 $ .  También por definición $ \braket{0 | 0 } = \braket{1 | 1 } = 1 $ , lo que significa que los dos vectores de base de cálculo también se pueden denominar *Orthonormal*.
Estas propiedades de Orthonormal serán útiles en el ejemplo siguiente. Si tenemos un estado $ \ket { \psi } = {\frac{3 } {5 } } \ket{1 } + {\frac{4 } {5 } } \ket{0 } $, dado que $ \braket{1 | 0 } = 0, $ la probabilidad de medir $1 $ es  

$ $ \big | \braket{1 | \psi } \big | ^ 2 = \left | \frac{3 } {5 } \braket{1 | 1 } + \frac{4 } {5 } \braket{1 | 0 } \right | ^ 2 = \frac{9 } {25 } . $ $ 

### <a name="tensor-product-notation"></a>Notación del producto tensores
La notación Dirac también incluye una estructura de producto tensores implícita dentro de ella.  Esto es importante porque en la informática Quantum, el vector de estado descrito por dos registros de Quantum no correlacionados es el tensores de los dos vectores de estado.  La descripción concisa de la estructura del producto tensores, o la ausencia de ella, es fundamental si desea explicar un cálculo de Quantum.  La estructura del producto tensores implica que se puede escribir $ \psi \otimes \phi $ para dos vectores de estado Quantum $ \phi $ y $ \psi $ como $ \ket { \psi } \ket { \phi } $, que a veces se escriben explícitamente como $ \ket { \psi } \otimes \ket { \phi } $, sin embargo, no es necesario escribir en la Convención $ \otimes $ entre los vectores.  Por ejemplo, el estado con dos qubits inicializado en el estado cero lo proporciona

$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \\ \\ 0 \end{ bmatrix } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } \otimes \ket{0 } = \ket{0 } \ket{0 } .
$$

Del mismo modo, el estado $ \ket{p } $ para Integer $p $ representa un estado de Quantum que codifica en representación binaria el entero $p $ .  Por ejemplo, si desea expresar el número $5 $ con una codificación binaria sin firmar, podríamos expresarlo igual que

$ $ \ket{1 } \ket{0 } \ket{1 } = \ket{101 } = \ket{5 } .
$$

Dentro de esta notación, $ \ket{0 } $ no necesita hacer referencia a un estado de qubit único, sino un *registro qubit* que almacena una codificación binaria de $0 $ .  Las diferencias entre estas dos notaciones suelen estar claras del contexto.  Esta Convención es útil para simplificar el primer ejemplo que se puede escribir de cualquiera de las siguientes maneras:

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cdots \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } \otimes \cdots \otimes \ket{0 } = | 0 \cdots 0 \rangle = \ket{0 } ^ {\otimes n } = \ket{0 } .
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>Ejemplo: describir la superposición con notación Dirac
Como otro ejemplo de cómo puede usar la notación Dirac para describir un estado de Quantum, tenga en cuenta las siguientes formas equivalentes de escribir un estado de Quantum que sea una superposición igual a cada cadena de bits posible de longitud $n$

$ $ H ^ {\otimes n } \ket{0 } = \frac{1 } {2 ^ {n/2 } } \ sum_ {j = 0 } ^ {2 ^ n-1 } \ket{j } = \ket { +} ^ {\otimes n } .
$$

Aquí puede que se pregunte por qué la suma va de $0 $ a $2 ^ {n } -1 $ para $n $ bits.  En primer lugar, tenga en cuenta que hay $2 ^ {n } $ configuraciones diferentes que $ pueden tardar $n bits.  Puede verlo observando que un bit puede tomar $2 $ valores, pero dos bits pueden tomar $4 $ valores, etc. En general, esto significa que hay $2 ^ n $ cadenas de bits posibles diferentes, pero el valor más grande codificado en cualquiera de ellos $1 \cdots 1 = 2 ^ n-1 $ y, por lo tanto, es el límite superior de la suma.
Como nota lateral, en este ejemplo no usamos $ \ket { +} ^ {\otimes n } = \ket { +} $ en analogía con $ \ket{0 } ^ {\otimes n } = \ket{0 } $ porque esta Convención de notación se reserva normalmente para el estado de base de cálculo con cada qubit inicializado en cero.  Aunque esta Convención sería razonable en este caso, no se emplea en la literatura de Quantum Computing.

### <a name="expressing-linearity-with-dirac-notation"></a>Expresar la linealidad con la notación Dirac
Otra característica agradable de la notación Dirac es el hecho de que es lineal.  Si deseamos escribir para cualquier otro vector de estado de Quantum, 

$ $ (\alpha \ket { \psi } + \beta \ket { \phi } ) \otimes (\gamma \ket { \chi } + \delta \ket { \omega } ) = \alpha \gamma \ket { \psi } \ket { \chi } + \alpha \delta \ket { \psi } \ket { \omega } + \beta \gamma \ket { \phi } \ket { \chi } + \beta \delta \ket { \phi } \ket { \omega } . $ $

Es decir, puede distribuir la notación del producto tensores en la notación Dirac para que la toma de los productos tensores entre vectores de estado acabe observando la multiplicación normal.

Los vectores Bra siguen una Convención similar a los vectores les.  Por ejemplo, el vector $ \bra { \psi } \bra { \phi } $ es equivalente al vector de estado $ \psi ^ \dagger \otimes \phi ^ \dagger = (\psi \otimes \phi) ^ \dagger $ . Si el vector les $ \ket { \psi } $ es $ \alpha \ket{0 } + \beta \ket{1 } $, la versión del vector Bra del vector es $ \bra { \psi } = \ket { \psi } ^ \dagger = (\bra{0 } \alpha ^ * + \bra{1 } \beta ^ *) $.

Por ejemplo, Imagine que desea calcular la probabilidad de medir el estado $ \ket { \psi } = \frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } $ usando un programa Quantum para medir los Estados para que sea $ \ket { +} $ o $ \ket { -} $. Después, la probabilidad de que el dispositivo genere el resultado de que el estado es $ \ket { -} $ es 

$ $ | \braket { -| \psi } | ^ 2 = \left | \frac{1 } {\sqrt{2 } } (\bra{0 } -\bra{1 } ) (\frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } ) \right | ^ 2 = \left | -\frac{3 } {5 \sqrt {2 } } + \frac{4 } {5 \sqrt {2 } } \right | ^ 2 = \frac{1 } {50 } . $ $

El hecho de que el signo negativo aparezca en el cálculo de la probabilidad es una manifestación de interferencia Quantum, que es uno de los mecanismos por los que la informática Quantum gana ventajas en la informática clásica.

## <a name="ketbra-or-outer-product"></a>ketbra o producto externo
El último elemento que merece la pena analizar en la notación Dirac es el producto *ketbra* o externo.  El producto exterior se representa dentro de las notaciones de Dirac como $ \ket { \psi } \bra { \phi } $ y, a veces, se denomina ketbras porque los Bras y kets se producen en el orden opuesto como frenos.  El producto externo se define a través de la multiplicación de matrices como $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger $ para los vectores de estado de Quantum $ \psi $ y $ \phi $ .  El ejemplo más sencillo y posiblemente más común de esta notación es

$ $ \ket{0 } \bra{0 } = \begin{ bmatrix } 1 \\\\ 0 \end{ bmatrix } \begin{ bmatrix } 1&0 \end{ bmatrix } = \begin{ bmatrix } 1 &0 \\\\ 0 &0 \end{bmatrix} \qquad \ket{1 } \bra{1 } = \begin{ bmatrix } 0 \\\\ 1 \end{ bmatrix } \begin{ bmatrix } 0&1 \end{ bmatrix } = \begin{ bmatrix } 0 &0 \\\\ 0 &1 \end{bmatrix} .
$$

Ketbras a menudo se denominan proyectores porque proyectan un estado de Quantum en un valor fijo.  Puesto que estas operaciones no son unitarios (y no conservan siquiera la norma de un vector), no debería sorprender que un equipo Quantum no pueda aplicar de forma determinista un proyector.  Sin embargo, los proyectores realizan un trabajo bonito de describir la acción que tiene la medida en un estado Quantum.  Por ejemplo, si se mide un estado $ \ket { \psi } $ para que sea $0 $ , la transformación resultante que experimenta el estado como resultado de la medida es

  $ $ \ket { \psi } \rightarrow \frac { (\ket{0 } \bra{0 } ) \ket { \psi } } {| \braket{0 | \psi } |} = \ket{0 } , $ $

como se espera si se mediera el estado y se considera que es $ \ket{0 } $.  Para reiterarse, no se pueden aplicar tales proyectores en un estado en un equipo Quantum de manera determinista.  En su lugar, se pueden aplicar de manera aleatoria con el resultado $ \ket{0 } $ que aparece con una probabilidad fija.  La probabilidad de que se produzca una medición correcta puede escribirse como el valor esperado del proyector Quantum en el estado

$ $ \bra { \psi } (\ket{0 } \bra{0 } ) \ket { \psi } = | \braket { \psi | 0 } | ^ 2, $ $

lo que muestra que los proyectores simplemente proporcionan una nueva forma de expresar el proceso de medición.

Si, por el contrario, se considera que la primera qubit de un estado de varios qubit es $1 $ , también se puede describir este proceso de forma cómoda mediante proyectores y notación Dirac:

$ $ P (\text{First qubit = 1 } ) = \bra { \psi } \left (\ket{1 } \bra{1 \otimes } \boldone ^ {\otimes n-1 } \right) \ket { \psi } .
$$

Aquí, la matriz de identidad se puede escribir de forma cómoda en la notación Dirac como

$ $ \boldone = \ket{0 } \bra{0 } + \ket{1 } \bra{1 } = \begin{ bmatrix } 1&0 \\\\ 0&1 \end{ bmatrix } .
$$

En el caso de que haya dos qubits, el proyector puede expandirse como 

$ $ \ket{1 } \bra{1 } \otimes \id = \ket{1 } \bra{1 \otimes } (\ket{0 } \bra{0 } + \ket{1 } \bra{1 } ) = \ket{10 } \bra{10 } + \ket{11 } \bra{11 } .
$$

A continuación, podemos ver que esto es coherente con la explicación de las probabilidades de medición para los Estados de multiqubit mediante la notación de vector de columna:

$ $ P (\text{First qubit = 1 } ) = \psi ^ \dagger (e \_ {10} e \_ {10 } ^ \dagger + e \_ {11} e \_ {11 } ^ \dagger) \psi = | e \_ {10 } ^ \dagger \psi | ^ 2 + | e \_ {11 } ^ \dagger \psi | ^ 2, $ $

que coincide con la descripción de la medida qubit.  Sin embargo, la generalización de este resultado en el caso de qubit múltiple es ligeramente más sencilla de expresar con la notación de Dirac que la notación de vector de columna y es totalmente equivalente al tratamiento anterior.

## <a name="density-operators"></a>Operadores de densidad

Otro operador útil para expresar con notación Dirac es un *operador de densidad*, a veces también conocido como *operador de estado*.
Un operador de densidad para un vector de estado de Quantum toma el formato $ \rho = \ket { \psi } \bra { \psi } $.
Este concepto de representar el estado como una matriz, en lugar de un vector, suele ser práctico porque proporciona una manera cómoda de representar los cálculos de probabilidad y también permite que se describa tanto la incertidumbre estadística como la incertidumbre de Quantum en el mismo formalismo.
Los operadores de estado de Quantum generales, en lugar de los vectores, están omnipresentes en algunas áreas de la informática Quantum, pero no son necesarios para comprender los aspectos básicos del campo.
En el caso del lector interesado, se recomienda leer uno de los libros de referencia que se proporcionan en [para obtener más información](xref:microsoft.quantum.more-information).

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a>Secuencias de Q # Gate equivalentes a los Estados de Quantum
Un punto final merece la pena aumentar sobre la notación de Quantum y el lenguaje de programación de Q #: al principio de este documento, mencionamos que el estado de Quantum es el objeto fundamental de la información en el cálculo de Quantum Computing.  Entonces, puede suponer que, en Q #, no hay noción de estado de Quantum.  En su lugar, todos los Estados solo se describen mediante las operaciones que se usan para prepararlos.  El ejemplo anterior es una ilustración excelente de esto.  En lugar de expresar una superposición uniforme sobre cada cadena de bits de Quantum de un registro, podemos representar el resultado como $H ^ {\otimes n } \ket{0 } $.  Esta descripción exponencialmente más corta del estado no solo tiene la ventaja de que se puede tener en cuenta, pero también define de forma concisa las operaciones necesarias para propagarse a través de la pila de software para implementar el algoritmo.  Por esta razón, Q # está diseñado para emitir secuencias de puerta en lugar de Estados Quantum; sin embargo, en un nivel teórico, las dos perspectivas son equivalentes.
