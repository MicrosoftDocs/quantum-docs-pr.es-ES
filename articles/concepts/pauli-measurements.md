---
title: Medidas de Pauli | Microsoft Docs
description: Medidas Pauli
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7bea821be7e26e72f2860278486d35be676ca63d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183716"
---
# <a name="pauli-measurements"></a>Medidas Pauli

En las conversaciones anteriores, nos hemos centrado en las mediciones de base de cálculo.  De hecho, hay otras medidas comunes que se producen en la informática Quantum que, desde una perspectiva de notación, son convenientes para expresar en términos de mediciones de base de cálculo.  El conjunto más común de estas medidas son las *medidas Pauli*.  En tales casos, es habitual analizar un operador Pauli, en general un operador como $X, Y, Z $ o $Z \otimes Z, X\otimes X, X\otimes Y $, etc.  La explicación de la medida en términos de operadores Pauli es especialmente común en el subcampo de la corrección de errores Quantum. En Q # se sigue una Convención similar. ahora se explica esta vista alternativa de las medidas.

Antes de profundizar en los detalles de cómo pensar en una medición Pauli, es útil pensar en qué medida un qubit único dentro de un equipo Quantum se realiza en el estado de Quantum.  Imagine que tenemos un estado de Quantum $n $-qubit; después, al medir una qubit inmediatamente, se desprotege la mitad de las posibilidades de $2 ^ n $ que podrían estar en el estado.  En otras palabras, la medida proyecta el estado de cuanto en uno de los dos espacios a medio.  Podemos generalizar el modo en que pensamos en medida para reflejarlo.

Para identificar de manera concisa estos subespacios, necesitamos un lenguaje para describirlos.  Una manera de hacer esto es describir los dos subespacios mediante la especificación de una matriz que solo tiene dos vectores propios únicos, tomadas por Convención para que sea $ \pm $1.  El ejemplo más sencillo es:

$ $ Z = \begin{bmatrix} 1 & 0 \\\\ 0 &-1 \end{bmatrix}.
$$

La matriz Pauli-$Z $ tiene claramente dos vectores propios $ \ket{0}$ y $ \ket{1}$ con vectores propios $ \pm $1.  Por lo tanto, si se mide el qubit y se obtiene $ \ket{0}$ se encuentran en la eigenspace $ + $1 (el conjunto de todos los vectores que están formados por sumas de vectores propios con solo los vectores propios positivos o negativos) del operador y si se mide $ \ket{1}$, en el eigenspace de $ $1 de $Z $.  Este proceso se conoce en el idioma de las medidas de Pauli como "medición de Pauli $Z $" y es totalmente equivalente a realizar una medición de base de cálculo.

Por supuesto, cualquier matriz de $2 \ Times $2 que sea una transformación de $Z $ también cumple este criterio.  Esto es decir que también podríamos considerar Matrix $A = U ^ \dagger Z U $, para cualquier matriz de unidades unitarios $U $, para proporcionar una matriz que defina los dos resultados de una medida en su vectores propios $ \pm $1.  La notación de las medidas de Pauli hace referencia a esto identificando $X, Y, Z $ Measurements como medidas equivalentes que puede hacer para obtener información de un qubit.  Estas medidas se proporcionan a continuación para mayor comodidad.

$ $ \begin{array}{| c | c |} \text{Pauli Measurement} & U\\\\ Z & \boldone\\\\ X & H\\\\ Y & HS ^ \dagger\\\\ \end{array} $ $

Es decir, con este lenguaje, "Measure $Y $" es equivalente a aplicar $HS ^ \dagger $ y, a continuación, medir en función de la base de cálculo, donde $S $ es la puerta de fase que se llama

$ $ \begin{bmatrix}1 & 0\\\\ 0 & i\end {bmatrix}.
$$

También es equivalente a aplicar $HS ^ \dagger $ al vector de estado de Quantum y después medir $Z $.  A continuación, se encontraría el estado correcto transformando de nuevo a la base de cálculo, lo que equivale a aplicar $SH $ al vector de estado de Quantum.

## <a name="q-outcome-classical-information-obtained-from-quantum-state"></a>P # resultado de la información clásica obtenida del estado de Quantum
En preguntas y respuestas, es decir, la información clásica extraída de la interacción con el estado es $j $ que se encuentra en el conjunto $\{0, 1\}$ si el resultado se encuentra en $ (-1) ^ j $ eigenspace del operador Pauli medido.

Las medidas de los operadores qubit de Pauli se definen de forma similar, como se aprecia en:

$ $ Z\otimes Z = \begin{bmatrix}1 & 0 & 0 & 0\\\\ 0 &-1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 & 1 \ end {bmatrix}.
$$

Por lo tanto, los productos de tensores de dos operadores Pauli-$Z $ forman una matriz formada por dos espacios compuestos de $ + $1 y $-$1 vectores propios.  Al igual que en el caso de un solo qubit, ambos constituyen un medio de espacio, lo que significa que la mitad del espacio de vector accesible pertenece a la eigenspace de $ + $1 y la mitad restante al eigenspace de $-$1.  En general, es fácil ver a partir de la definición del producto tensores que cualquier producto tensores de los operadores Pauli-$Z $ y la identidad también obedece esto.  Por ejemplo,

$ $ Z\otimes\boldone = \begin{bmatrix} 1 & 0 & 0 & 0\\\\ 0 & 1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 &-1 \ end {bmatrix}.
$$

Como antes, cualquier transformación unitario de estas matrices también describe dos espacios a la mitad etiquetados por $ \pm $1 vectores propios.  Por ejemplo, $X \otimes X = H\otimes H (Z\otimes Z) H\otimes H $ de la identidad que $Z = HXH $.  Al igual que en el caso de una qubit, todas las mediciones de dos qubit Pauli se pueden escribir como $U ^ \dagger (Z\otimes \id) U $ para $4 \ Times $4 unidad unitario $U $.  En la tabla siguiente se enumeran las transformaciones en las que se introduce para mayor comodidad la puerta de intercambio que intercambia qubits $0 $ y $1 $: $ \operatorname{SWAP} = \operatorname{CNOT}\_{01}\operatorname{CNOT}\_{10}\operatorname{CNOT}\_{01}$:

$ $ \begin{array}{| c | c |} \text{Pauli Measurement} & U\\\\ \hline Z\otimes \boldone & \boldone\otimes \boldone\\\\ X\otimes \boldone & H\otimes \boldone\\\\ Y\otimes \boldone & HS ^ \dagger\otimes \boldone\\\\ \boldone \otimes Z & \operatorname{SWAP}\\\\ \boldone \otimes X & (H\otimes \boldone) \operatorname{SWAP}\\\\ \boldone \otimes Y & (HS ^ \dagger\otimes \boldone) \ operatorname {SWAP}\\\\ Z\otimes Z & \operatorname{CNOT}\_{10}\\\\ X\otimes Z & \operatorname{CNOT}\_{10}(H\otimes \boldone)\\\\ Y\otimes Z & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes \boldone)\\\\ Z\otimes X & \operatorname{CNOT}\_{10}(\boldone\otimes H)\\\\ X\otimes X & \operatorname{CNOT}\_{10}(H \ otimes H)\\\\ Y\otimes X & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes H)\\\\ Z\otimes Y & \operatorname{CNOT}\_{10}(\boldone \otimes HS ^ \dagger)\\\\ X\otimes Y & \operatorname{CNOT}\_{10}(H\otimes HS ^ \dagger)\\\\ Y\otimes Y & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes HS ^ \dagger)\\\\ \end{array} $ $

Aquí se muestra la puerta $ \operatorname{CNOT}\_{10}$ por el siguiente motivo.  Cada medida de Pauli que no incluye la matriz $ \boldone $ equivale a una unitario a $Z \otimes Z $ por la razón anterior.  Los vectores propios de $Z \otimes Z $ solo dependen de la paridad de qubits que conforman cada vector de base de cálculo y las operaciones controladas que aparecen en esta lista sirven para calcular esta paridad y almacenarla en el primer bit.  Después, una vez que se mida el primer bit, podemos recuperar la identidad del espacio medio resultante, que es equivalente a medir el operador Pauli.

Una nota adicional, aunque puede ser tentador asumir que la medición de $Z \otimes Z $ es la misma que la medición de $Z \otimes \id $ y, a continuación, $ \id \otimes Z $, esta suposición sería falsa.  La razón es que medir $Z \otimes Z $ proyecta el estado de cuanto en el eigenstate $ + $1 o $-$1 de estos operadores.  La medición de $Z \otimes \id $ y después $ \id \otimes Z $ proyecta el vector de estado Quantum primero en un espacio medio de $Z \otimes \id $ y después en un espacio medio de $ \id \otimes Z $.  Como hay cuatro vectores de base de cálculo, al realizar ambas mediciones se reduce el estado a un cuarto de espacio y, por tanto, se reduce a un vector de base de cálculo único.


## <a name="correlations-between-qubits"></a>Correlaciones entre qubits
Otra forma de ver los productos de tensores de Paulis, como $X \otimes X $ o $Z \otimes Z $, es que estas medidas permiten examinar la información almacenada en las correlaciones entre los dos qubits.  La medición de $X \otimes \id $ le permite consultar la información que se almacena localmente en la primera qubit.  Aunque ambos tipos de medidas son igualmente valiosos en la informática Quantum, el primero ilumina la potencia de la informática Quantum. Revela que, en la informática Quantum, a menudo la información que desea aprender no se almacena en ningún qubit único, sino que se almacena de forma no local en todas las qubits a la vez, y solo al examinarla mediante una medida conjunta con $Z \otimes Z $ hace que esta información se convierta en manifiesto.

También se pueden medir los operadores arbitrarios de Pauli, como $X \otimes Y \otimes Z \otimes \boldone $.  Todos estos productos tensores de los operadores Pauli tienen solo dos vectores propios $ \pm $1 y ambos eigenspaces constituyen los semiespacios del espacio vectorial completo.  Por lo tanto, coinciden con los requisitos indicados anteriormente.

En Q #, estas medidas devuelven $j $ si la medida produce un resultado en el eigenspace del signo $ (-1) ^ j $.  Tener esto como una característica integrada en Q # es útil porque la medición de estos operadores requiere largas cadenas de puertas y transformaciones basadas en no controladas para describir la diagonalización $U $ Gate necesaria para expresar la operación como un producto tensores de $Z $ y $ \id $.  Si simplemente se puede especificar que se desea realizar una de estas medidas predefinidas, no es necesario preocuparse por cómo transformar la base de forma que una medición de base de cálculo proporcione la información necesaria.  Q # controla todas las transformaciones de base necesarias automáticamente. Consulte la [referencia de la biblioteca de Q # para las medidas Pauli](/qsharp/api/canon/microsoft.quantum.canon.measurepaulis)

## <a name="the-no-cloning-theorem"></a>Teorema sin clonación
La información de Quantum es eficaz.  Nos permite hacer cosas sorprendentes, como números de factor exponencialmente más rápidos que los mejores algoritmos clásicos conocidos, o simular eficazmente sistemas de electrones correlacionados que requieran el costo exponencial para simular con precisión.  Sin embargo, existen limitaciones en cuanto a la eficacia de la informática Quantum.  Una de estas limitaciones viene determinada por el *teorema sin clonación*.

La teorema sin clonación tiene un nombre acertado.
No permite la clonación de Estados de Quantum genéricos por un equipo Quantum.
La prueba de Teorema es bastante sencilla.
Aunque una prueba completa del teorema sin clonación es un poco muy técnico para nuestro debate aquí, la prueba de teorema en caso de que el equipo Quantum en cuestión no tenga ningún qubits de ancilla adicional en nuestro ámbito (ancilla qubits se usan para el espacio de desecho durante un cálculo y se pueden usar y administrar fácilmente en Q #, vea <xref:microsoft.quantum.techniques.qubits>).
Para este tipo de equipo Quantum, la operación de clonación debe ser una matriz unitario. No permitimos la medición, ya que dañaría el estado de Quantum que estamos intentando clonar. La matriz de unitarios que queremos debe tener la propiedad $ $ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}, $ $ para cualquier estado $ \ket{\psi} $.
La propiedad linearity de la multiplicación de matrices implica que para cualquier segundo estado de Quantum $ \ket{\phi} $,

\begin{align} & U\left [\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right] \ket{0}= \frac{1}{\sqrt{2}} U\ket {\ Phi} \ les{0}+ \frac{1}{\sqrt{2}} U\ket {\ PSI} \ les{0}\\\\ & \qquad\qquad = \frac{1}{\sqrt{2}} \left (\ket{\phi}\ket{\phi} + \ket{\psi}\ket{\psi}\right)\\\\ & \qquad\qquad\ne \left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \ Right) \right) \otimes\left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right).
\end{align}

Esto proporciona el Intuition fundamental detrás del teorema sin clonación: cualquier dispositivo que copie un estado de Quantum desconocido debe inducir errores en al menos algunos de los Estados que copia.  Aunque la principal suposición de que el Cloner actúa de forma lineal en el estado de la entrada se puede infringir mediante la adición de ancilla y la medición de la ancilla qubits, estas interacciones también pierden información sobre el sistema a través de las estadísticas de medida y evitan también clonación exacta en estos casos.  Para obtener una prueba más completa de la teorema sin clonación, vea [para obtener más información](xref:microsoft.quantum.more-information).

La teorema sin clonación es importante para el conocimiento cualitativo de la informática Quantum, ya que si pudiera clonar los Estados de Quantum de forma económica, se le concederá una capacidad casi mágica para aprender de los Estados de Quantum.  En realidad, puede infringir el principio de incertidumbre de vaunted de Heisenberg.  Como alternativa, puede usar una Cloner óptima para tomar una muestra única de una distribución de Quantum compleja y obtener información sobre todo lo que podría obtener más información sobre esa distribución desde un solo ejemplo.  Esto sería similar a la forma de voltear una moneda y observar los cabezales y, a continuación, al decir a un amigo sobre el resultado de responder "Ah la distribución de esa moneda debe ser Bernoulli con $p = 0.512643 \ ldots $!"  Este tipo de instrucción sería no SENS, porque un bit de información (el resultado de los cabezales) simplemente no puede proporcionar los numerosos bits de información necesaria para codificar la distribución sin información importante de gran tamaño.  Del mismo modo, sin información previa, no se puede clonar absolutamente un estado de Quantum, al igual que no se puede preparar un conjunto de esas monedas sin conocer $p $.

La información no es gratuita en la informática Quantum.  Cada qubit medido proporciona un único bit de información y el teorema sin clonación muestra que no hay ninguna puerta trasera que pueda aprovecharse para evitar el equilibrio fundamental entre la información obtenida sobre el sistema y la perturbación invocada.

