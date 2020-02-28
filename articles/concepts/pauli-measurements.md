---
title: Medidas Pauli
description: Obtenga información sobre cómo trabajar con operaciones de medición de Pauli de un solo y varios qubit.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: fcd30c171859f96c3f9cc74664ecba8df0a02855
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907518"
---
# <a name="pauli-measurements"></a>Medidas Pauli

En las conversaciones anteriores, nos hemos centrado en las mediciones de base de cálculo.
De hecho, hay otras medidas comunes que se producen en la informática Quantum que, desde una perspectiva de notación, son convenientes para expresar en términos de mediciones de base de cálculo.
A medida que trabaje con Q #, el tipo más común de medidas en las que se ejecutará probablemente serán *mediciones de Pauli*, que generalizan las mediciones de base de cálculo para incluir medidas en otras bases y de paridad entre diferentes qubits.
En tales casos, es habitual analizar un operador Pauli, en general un operador como $X, Y, Z $ o $Z \otimes Z, X\otimes X, X\otimes Y $, etc.

> [!TIP]
> En Q #, los operadores multiqubit Pauli se representan generalmente mediante matrices de tipo `Pauli[]`.
> Por ejemplo, para representar $X \otimes Z \otimes Y $, puede usar el `[PauliX, PauliZ, PauliY]`de matriz.

La explicación de la medida en términos de operadores Pauli es especialmente común en el subcampo de la corrección de errores Quantum.
En Q #, seguimos una Convención similar; ahora se explica esta vista alternativa de las medidas.

Antes de profundizar en los detalles de cómo pensar en una medición Pauli, es útil pensar en qué medida un qubit único dentro de un equipo Quantum se realiza en el estado de Quantum.
Imagine que tenemos un estado de Quantum $n $-qubit; después, al medir una qubit inmediatamente, se desprotege la mitad de las posibilidades de $2 ^ n $ que podrían estar en el estado.
En otras palabras, la medida proyecta el estado de cuanto en uno de los dos espacios a medio.
Podemos generalizar el modo en que pensamos en medida para reflejar este Intuition.

Para identificar de manera concisa estos subespacios, necesitamos un lenguaje para describirlos.
Una manera de describir los dos subespacios es mediante la especificación de una matriz que solo tiene dos vectores propios únicos, tomadas por Convención para que sea $ \pm $1.
Para obtener un ejemplo sencillo de la descripción de los subespacios de esta manera, considere la posibilidad de $Z $:

$ $ \begin{align} Z & = \begin{bmatrix} 1 & 0 \\\\ 0 &-1 \end{bmatrix}.
\end{align} $ $

Al leer los elementos diagonales de la matriz Pauli-$Z $, podemos ver que $Z $ tiene dos vectores propios, $ \ket{0}$ y $ \ket{1}$, con la vectores propios $ \pm $1 correspondiente.
Por lo tanto, si se mide el qubit y se obtiene `Zero` (que corresponde al estado $ \ket{0}$), sabemos que el estado de nuestro qubit es un $1 $ + eigenstate del operador $Z $.
Del mismo modo, si obtenemos `One`, sabemos que el estado de nuestro qubit es un eigenstate $-$1 de $Z $.
Este proceso se conoce en el idioma de las medidas de Pauli como "medición de Pauli $Z $" y es totalmente equivalente a realizar una medición de base de cálculo.

Cualquier matriz de $2 \ Times $2 que sea una transformación de $Z $ también cumple este criterio.
Es decir, también podríamos usar una matriz $A = U ^ \dagger Z U $, donde $U $ es cualquier otra matriz de unidades unitarios, para proporcionar una matriz que defina los dos resultados de una medida en su vectores propios $ \pm $1.
La notación de las medidas Pauli hace referencia a esta equivalencia de unitarios mediante la identificación de $X, Y, Z $ Measurement como medidas equivalentes que podría hacer para obtener información de un qubit.
Estas medidas se proporcionan a continuación para mayor comodidad.


|Medida Pauli  |Transformación unitario  |
|-------------------|------------------------|
| $Z $               | $ \boldone $             |
| $X $               | $H $                    |
| $Y $               | $HS ^ {\dagger} $         |

Es decir, con este lenguaje, "Measure $Y $" es equivalente a aplicar $HS ^ \dagger $ y después medir en función de la base de cálculo, donde [`S`](xref:microsoft.quantum.intrinsic.s) es una operación Quantum intrínseca que a veces se denomina "puerta de fase", y se puede simular mediante la matriz de la unidad.

$ $ \begin{align} S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.
\end{align} $ $

También es equivalente a aplicar $HS ^ \dagger $ al vector de estado de Quantum y, a continuación, medir $Z $, de tal forma que la operación siguiente sea equivalente a `Measure([PauliY], [q]])`:

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

A continuación, se encontraría el estado correcto transformando de nuevo a la base de cálculo, lo que equivale a aplicar $SH $ al vector de estado de Quantum; en el fragmento de código anterior, el uso del bloque `within … apply` controla automáticamente la transformación de vuelta a la base computacional.

En Q #, se indica el resultado---es decir, la información clásica extraída de la interacción con el estado---se proporciona mediante un valor `Result` $j \en \\{\texttt{Zero}, \texttt{One}\\} $ que indica si el resultado está en $ (-1) ^ j $ eigenspace del operador Pauli medido.


## <a name="multiple-qubit-measurements"></a>Mediciones de varios qubit

Las medidas de los operadores qubit de Pauli se definen de forma similar, como se aprecia en:

$ $ Z\otimes Z = \begin{bmatrix}1 & 0 & 0 & 0\\\\ 0 &-1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 & 1 \ end {bmatrix}.
$$

Por lo tanto, los productos de tensores de dos operadores Pauli-$Z $ forman una matriz formada por dos espacios compuestos de $ + $1 y $-$1 vectores propios.
Al igual que en el caso de un solo qubit, ambos constituyen un medio de espacio, lo que significa que la mitad del espacio de vector accesible pertenece a la eigenspace de $ + $1 y la mitad restante al eigenspace de $-$1.
En general, es fácil ver a partir de la definición del producto tensores que cualquier producto tensores de los operadores Pauli-$Z $ y la identidad también obedece esto.
Por ejemplo,

$ $ \begin{align} Z \otimes \boldone = \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 &-1 & 0 \\\\ 0 & 0 & 0 &-1 \end{bmatrix}.
\end{align} $ $

Como antes, cualquier transformación unitario de estas matrices también describe dos espacios a la mitad etiquetados por $ \pm $1 vectores propios.
Por ejemplo, $X \otimes X = H\otimes H (Z\otimes Z) H\otimes H $ de la identidad que $Z = HXH $.
Al igual que en el caso de una qubit, todas las mediciones de dos qubit Pauli se pueden escribir como $U ^ \dagger (Z\otimes \id) U $ para $4 \ Times $4 unidad unitario $U $. En la tabla siguiente se enumeran las transformaciones.

> [!NOTE]
> En la tabla siguiente, usamos $ \operatorname{SWAP} $ para indicar la matriz $ $ \begin{align} \operatorname{SWAP} & = \left (\begin{Matrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{Matrix}\right) \end{align} $ $ que se usa para simular la operación intrínseca [`SWAP`](xref:microsoft.quantum.intrinsic).

|Medida Pauli     |Transformación unitario  |
|----------------------|------------------------|
| $Z \otimes \boldone $ | $ \boldone \otimes \boldone $ |
| $Z \otimes \boldone $ | $ \boldone\otimes \boldone $ |
| $X \otimes \boldone $ | $H \otimes \boldone $ |
| $Y \otimes \boldone $ | $HS ^ \dagger\otimes \boldone $ |
| $ \boldone \otimes Z $ | $ \operatorname{SWAP} $ |
| $ \boldone \otimes X $ | $ (H\otimes \boldone) \operatorname{SWAP} $ |
| $ \boldone \otimes Y $ | $ (HS ^ \dagger\otimes \boldone) \operatorname{SWAP} $ |
| $Z \otimes Z $ | $ \operatorname{CNOT}\_{10}$ |
| $X \otimes Z $ | $ \operatorname{CNOT}\_{10}(H\otimes \boldone) $ |
| $Y \otimes Z $ | $ \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes \boldone) $ |
| $Z \otimes X $ | $ \operatorname{CNOT}\_{10}(\boldone\otimes H) $ |
| $X \otimes X $ | $ \operatorname{CNOT}\_{10}(H\otimes H) $ |
| $Y \otimes X $ | $ \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes H) $ |
| $Z \otimes Y $ | $ \operatorname{CNOT}\_{10}(\boldone \otimes HS ^ \dagger) $ |
| $X \otimes Y $ | $ \operatorname{CNOT}\_{10}(H\otimes HS ^ \dagger) $ |
| $Y \otimes Y $ | $ \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes HS ^ \dagger) $ |

En este caso, la operación de [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) aparece por el siguiente motivo.
Cada medida de Pauli que no incluye la matriz $ \boldone $ equivale a una unitario a $Z \otimes Z $ por la razón anterior.
Los vectores propios de $Z \otimes Z $ solo dependen de la paridad de qubits que conforman cada vector de base de cálculo, y las operaciones controladas y no sirven para calcular esta paridad y almacenarla en el primer bit.
Después, una vez que se mide el primer bit, podemos recuperar la identidad del espacio medio resultante, que es equivalente a medir el operador Pauli.

Una nota adicional: aunque puede ser tentador asumir que la medición de $Z \otimes Z $ es la misma que la medición secuencial de $Z \otimes \mathbb{1}$ y después $ \mathbb{1} \otimes Z $, esta suposición sería falsa.
La razón es que medir $Z \otimes Z $ proyecta el estado de cuanto en el eigenstate $ + $1 o $-$1 de estos operadores.
La medición de $Z \otimes \mathbb{1}$ y después $ \mathbb{1} \otimes Z $ proyecta el vector de estado Quantum primero en un espacio medio de $Z \otimes \mathbb{1}$ y, a continuación, en un espacio medio de $ \mathbb{1} \otimes Z $.
Como hay cuatro vectores de base de cálculo, al realizar ambas mediciones se reduce el estado a un cuarto de espacio y, por tanto, se reduce a un vector de base de cálculo único.

## <a name="correlations-between-qubits"></a>Correlaciones entre qubits
Otra forma de ver los productos de tensores de matrices de Pauli, como $X \otimes X $ o $Z \otimes Z $, es que estas medidas permiten examinar la información almacenada en las correlaciones entre los dos qubits.
La medición de $X \otimes \id $ le permite consultar la información que se almacena localmente en la primera qubit.
Aunque ambos tipos de medidas son igualmente valiosos en la informática Quantum, el primero ilumina la potencia de la informática Quantum.
Revela que, con frecuencia, la información que desea aprender no se almacena en ningún qubit único, sino que se almacena de forma no local en todas las qubits a la vez y, por lo tanto, solo si se examina mediante una medida conjunta (por ejemplo, $Z \otimes Z $) lo hace la información se convierte en manifiesto.

Por ejemplo, en la corrección de errores, a menudo queremos obtener información sobre el error que se produjo al no aprender nada sobre el estado que estamos intentando proteger.
[En el ejemplo de código bit-Flip](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) se muestra un ejemplo de cómo puede hacerlo con medidas como $Z \otimes z \otimes \id $ y $ \Id \otimes Z \otimes z $.
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

También se pueden medir los operadores arbitrarios de Pauli, como $X \otimes Y \otimes Z \otimes \boldone $.
Todos estos productos tensores de los operadores Pauli tienen solo dos vectores propios $ \pm $1 y ambos eigenspaces constituyen los semiespacios del espacio vectorial completo.
Por lo tanto, coinciden con los requisitos indicados anteriormente.

En Q #, estas medidas devuelven $j $ si la medida produce un resultado en el eigenspace del signo $ (-1) ^ j $.
Tener las medidas de Pauli como una característica integrada en Q # es útil porque la medición de estos operadores requiere largas cadenas de puertas y transformaciones controladas (no) para describir la diagonalización $U $ Gate necesaria para expresar la operación como un producto tensores de $Z $ y $ \id $.
Al poder especificar que desea realizar una de estas medidas predefinidas, no es necesario preocuparse por cómo transformar la base de forma que una medición de base de cálculo proporcione la información necesaria.
Q # controla todas las transformaciones de base necesarias automáticamente.
Para obtener más información, vea las operaciones [`Measure`](xref:microsoft.quantum.intrinsic.measure) y [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) .

## <a name="the-no-cloning-theorem"></a>Teorema sin clonación

La información de Quantum es eficaz.
Nos permite hacer cosas sorprendentes, como números de factor exponencialmente más rápidos que los mejores algoritmos clásicos conocidos, o simular eficazmente sistemas de electrones correlacionados que requieran el costo exponencial para simular con precisión.
Sin embargo, existen limitaciones en cuanto a la eficacia de la informática Quantum.
Una de estas limitaciones viene determinada por el *teorema sin clonación*.

La teorema sin clonación tiene un nombre acertado.
No permite la clonación de Estados de Quantum genéricos por un equipo Quantum.
La prueba de Teorema es bastante sencilla.
Aunque una prueba completa del teorema sin clonación es un poco muy técnico para nuestro debate aquí, la prueba, en el caso de que no haya ningún qubits auxiliar adicional, se encuentra dentro de nuestro ámbito (los qubits auxiliares se qubits usan para el espacio de desecho durante un cálculo y se usan y administran fácilmente en Q #, vea <xref:microsoft.quantum.techniques.qubits>).

Para este tipo de equipo Quantum, la operación de clonación debe describirse mediante una matriz de unitario.
No permitimos la medición, ya que dañaría el estado de Quantum que estamos intentando clonar.
Para simular la operación de clonación, queremos que la matriz de unitarios se use para tener la propiedad que $ $ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi} $ $ para cualquier estado $ \ket{\psi} $.
La propiedad linearity de la multiplicación de matrices implica que para cualquier segundo estado de Quantum $ \ket{\phi} $,

$ $ \begin{align} U \left [\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right] \ket{0} & = \frac{1}{\sqrt{2}} U\ket {\ Phi} \ les{0} + \frac{1}{\sqrt{2}} U\ket {\ PSI} \ les{0} \\\\ & = \frac{1}{\sqrt{2}} \left (\ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi} \right) \\\\ & \ne \left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right) \otimes \ Left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right).
\end{align} $ $

Esto proporciona el Intuition fundamental detrás del teorema sin clonación: cualquier dispositivo que copie un estado de Quantum desconocido debe inducir errores en al menos algunos de los Estados que copia.
Aunque la principal suposición de que el Cloner actúa de forma lineal en el estado de la entrada se puede infringir mediante la adición y medición de qubits auxiliares, estas interacciones también pierden información sobre el sistema a través de las estadísticas de medida y evitan exactamente también se clona en estos casos.
Para obtener una prueba más completa de la teorema sin clonación, vea [para obtener más información](xref:microsoft.quantum.more-information).

La teorema sin clonación es importante para el conocimiento cualitativo de la informática Quantum, ya que si pudiera clonar los Estados de Quantum de forma económica, se le concederá una capacidad casi mágica para aprender de los Estados de Quantum.
En realidad, puede infringir el principio de incertidumbre de vaunted de Heisenberg.
Como alternativa, puede usar una Cloner óptima para tomar una muestra única de una distribución de Quantum compleja y obtener información sobre todo lo que podría obtener más información sobre esa distribución desde un solo ejemplo.
Esto sería similar a la forma de voltear una moneda y observar los cabezales y, a continuación, al decir a un amigo sobre el resultado de responder "Ah la distribución de esa moneda debe ser Bernoulli con $p = 0.512643 \ ldots $!"  Este tipo de instrucción sería no SENS, porque un bit de información (el resultado de los cabezales) simplemente no puede proporcionar los numerosos bits de información necesaria para codificar la distribución sin información importante de gran tamaño.
Del mismo modo, sin información previa, no se puede clonar absolutamente un estado de Quantum, al igual que no se puede preparar un conjunto de esas monedas sin conocer $p $.

La información no es gratuita en la informática Quantum.
Cada qubit medido proporciona un único bit de información y el teorema sin clonación muestra que no hay ninguna puerta trasera que pueda aprovecharse para evitar el equilibrio fundamental entre la información obtenida sobre el sistema y la perturbación invocada.
