---
title: Varios qubits | Microsoft Docs
description: Varios qubits
author: QuantumWriter
uid: microsoft.quantum.concepts.multiple-qubits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: e9c043f4ee41a878b9544a27d5ea052fce29f06e
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863223"
---
# <a name="multiple-qubits"></a>Varios qubits

Mientras que las puertas de qubit único poseen algunas características que son intuitivas, como la capacidad de tener más de un estado en un momento dado, si todo lo que teníamos en un equipo Quantum era de un solo qubit, entonces tendremos un dispositivo con la potencia de cálculo que sería dwarfed por incluso una calculadora permite un superequipo clásico.
La verdadera potencia de la informática Quantum solo es evidente a medida que aumentamos el número de qubits.
Esta potencia surge, en parte, porque la dimensión del espacio de vectores de los vectores de estado Quantum aumenta exponencialmente con el número de qubits.
Esto significa que, mientras que un único qubit puede modelarse de forma trivial, la simulación de un cálculo de Quantum 50-qubit impedirá los límites de los superequipos existentes.
Si se aumenta el tamaño del cálculo solo en un qubit adicional, se *duplica* la memoria necesaria para almacenar el estado y, aproximadamente, se *duplica* el tiempo de cálculo.
Esta rápida duplicación de la potencia de cálculo es el motivo por el que un equipo Quantum con un número relativamente pequeño de qubits puede superar los superequipos más eficaces de hoy, mañana y más allá de algunas tareas de cálculo.

¿Por qué tenemos un crecimiento exponencial de los vectores de estado de Quantum?  Nuestro objetivo en esta sección es revisar las reglas que se usan para compilar Estados de varios qubit fuera de los Estados de un solo qubit, además de describir las operaciones de la puerta que necesitamos incluir en nuestro conjunto de la puerta para formar un equipo Quantum universal de varios qubit.
Estas herramientas son absolutamente necesarias para comprender los conjuntos de puertas que se suelen usar en el código de Q # y también para obtener Intuition sobre por qué los efectos de Quantum como el inenredo o la interferencia representan la informática Quantum más eficaz que la informática clásica.

## <a name="representing-two-qubits"></a>Representar dos qubits
La principal diferencia entre los Estados uno y dos qubit es que los Estados dos qubit son cuatro dimensionales en lugar de dos dimensiones.
Esto se debe a que la base de cálculo de los Estados de dos qubit está formada por los productos de tensores de un estado de qubit.  Por ejemplo, tenemos \begin{align} 00 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}1 \\\\ 0\\\\ 0\\\\ 0 \end{bmatrix}, \qquad 01 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 1\\\\ 0\\\\ 0 \end{bmatrix},\\\\ 10 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}0 \\\\ 0\\\\ 1\\\\ 0 \end{bmatrix}, \qquad 11 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 0\\\\ 0 @no__ t_40_ \\ 1 \end{bmatrix}.
\end{align}

Es fácil ver que, en general, el estado del Quantum de $n $ qubits se representa mediante un vector de unidad de la dimensión $2 ^ n $ mediante esta construcción.  Vector

$ $ \begin{bmatrix} \ alpha_{00} \\\\ \ alpha_{01} \\\\ \ alpha_{10} \\\\ \ alpha_{11} \end{bmatrix} $ $

representa un estado de Quantum en dos qubits si $ | \ alpha_{00}| ^ 2 + | \ alpha_{01}| ^ 2 + | \ alpha_{10}| ^ 2 + | \ alpha_{11}| ^ 2 = 1 $. Del mismo modo que con un solo qubits, el vector de estado Quantum de varios qubits contiene toda la información necesaria para describir el comportamiento del sistema.

Si se proporcionan dos qubits independientes, uno en el estado $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ y un segundo qubit en el estado $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $, el estado de dos qubit correspondiente es

$ $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} = \begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\ \delta \end{bmatrix} \end{bmatrix} = \begin{bmatrix} \alpha\gamma \\\\ \alpha\delta \\\\ \beta\gamma \\\\ \beta\delta \end{bmatrix} , $$

donde la operación $ \otimes $ se denomina producto tensores (o producto Kronecker) de vectores. Tenga en cuenta que aunque siempre podemos tomar el producto tensores de dos Estados de qubit único para formar un estado de dos qubit, no todos los Estados de Quantum de dos qubit pueden escribirse como el producto tensores de dos Estados de qubit único.
Por ejemplo, no hay ningún estado $ \psi = \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ y $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ de modo que su producto tensores sea el estado 

$ $ \psi\otimes \phi = \begin{bmatrix} 1/\ sqrt{2} \\\\ 0 \\\\ 0 \\\\ 1/\ sqrt{2} \end{bmatrix}. $ $ 

Este estado de dos qubit, que no se puede escribir como el producto tensores de los Estados de qubit único, se denomina "estado de inscrito". [*se dice*](https://en.wikipedia.org/wiki/Quantum_entanglement)que los dos qubits están inscritos.  Hablando de forma flexible, dado que el estado del Quantum no se puede considerar como un producto tensores de Estados de qubit únicos, la información que el estado contiene no se limita a ninguno de los qubits individualmente.  En su lugar, la información se almacena de forma no local en las correlaciones entre los dos Estados.  Este no emplazamiento de la información es una de las principales características distintivas de la informática Quantum en la informática clásica y es esencial para varios protocolos Quantum, como la [teleportabilidad de Quantum](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/teleportation) y la [corrección de errores de Quantum](xref:microsoft.quantum.libraries.error-correction).

## <a name="measuring-two-qubit-states"></a>Medición de Estados de dos qubit ##
Medir los Estados de dos qubit es muy similar a las mediciones de un solo qubit. Medir el estado

$ $ \begin{bmatrix} \ alpha_{00} \\\\ \ alpha_{01} \\\\ \ alpha_{10} \\\\ \ alpha_{11} \end{bmatrix} $ $

produce $0 $ con probabilidad $ | \ alpha_{00}| ^ $2, $1 $ con probabilidad $ | \ alpha_{01}| ^ $2, $10 $ con probabilidad $ | \ alpha_{10}| ^ $2 y $11 $ con probabilidad $ | \ alpha_{11}| ^ $2. Las variables $ \ alpha_{00}, \ alpha_{01}, \ alpha_{10}, $ y $ \ alpha_{11}$ se denominaron deliberadamente para que esta conexión sea clara. Después de la medición, si el resultado es $0 $, el estado de cuanto del sistema de dos qubit se ha contraído y ahora es

$ $0 \equiv \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix}.
$$

También es posible medir solo un qubit de un estado de Quantum de dos qubit. En los casos en los que solo se mide uno de los qubits, el impacto de la medida es ligeramente diferente porque el estado completo no se contrae en un estado de base de cálculo, sino que se contrae solo en un subsistema.  En otras palabras, en estos casos, la medición de solo un qubit solo contrae uno de los subsistemas, pero no todos.  

Para ver esto, considere la posibilidad de medir la primera qubit del estado siguiente, que se forma aplicando la transformación Hadamard $H $ en dos qubits inicialmente establecidas en el estado "0": $ $ H ^ {\otimes 2} \left (\begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} \right) = \frac{1}{2}\begin{bmatrix}1 & 1 & 1 & 1 \\\\ 1 &-1 & 1 &-1 \\\\ 1 & 1 &-1 &-1 \\\\ 1 &- 1 &-1 & 1 \end{bmatrix}\begin{bmatrix}1\\\\ 0\\\\ 0\\\\ 0 \ end {bmatrix} = \frac{1}{2}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \mapsto \begin{Cases}\text{Outcome} = 0 & \frac{1}{\sqrt{2}} \begin{bmatrix}1\\\\ 1\\\\ 0\\\\ 0 \end{bmatrix}\\\\ \text{Outcome} = 1 & \frac{1}{\sqrt{2}} \begin{bmatrix}0\\\\ 0\\\\ 1\\\\ 1 \end{bmatrix}\\\\ \end{cases}.
$ $ Ambos resultados tienen una probabilidad del 50% de su aparición.  El resultado es una probabilidad del 50% para ambos se puede intuir desde el hecho de que el vector de estado de Quantum inicial es invariable en el intercambio de $0 $ con $1 $ en el primer qubit.

La regla matemática para medir el primer o el segundo qubit es sencilla.  Si se permite que $e _k $ sea el vector de base $k ^ {\rm TH} $ y deje que $S $ sea el conjunto de todos los $e _k $, de modo que el qubit en cuestión toma el valor $1 $ para ese valor de $k $.  Por ejemplo, si nos interesa medir el primer qubit, $S $ consistiría en $e _2 \ equiv $10 y $e _3 \ equiv $11.  Del mismo modo, si estamos interesados en el segundo qubit $S $ constaría de $e _ $1 1 y $e _3 \equiv $11.  Después, la probabilidad de medir el qubit elegido es $1 $ para el vector de estado $ \psi $

$ $ P (\text{Outcome} = 1) = \ sum_ {e_k \text{en el conjunto} S} \psi ^ \dagger e_k e_k ^ \dagger \psi.
$$

Dado que cada medida de qubit solo puede producir $0 $ o $1 $, la probabilidad de medir $0 $ es simplemente $1-P (\text{Outcome} = 1) $.  Este es el motivo por el que solo proporcionamos explícitamente una fórmula para la probabilidad de medir $1 $.

La acción que tiene esta medida en el estado se puede expresar de forma matemática como

$ $ \psi \mapsto \frac{\ sum_ {e_k \text{en el conjunto} S} e_k e_k ^ \dagger \psi}{\sqrt{P (\text{Outcome} = 1)}}.
$$

El lector prudente puede preocuparse de lo que sucede cuando la probabilidad de la medida es cero.  Aunque el estado resultante es técnicamente indefinido en este caso, nunca es necesario preocuparse por estas eventualidades porque la probabilidad es cero.


Si tomamos $ \psi $ para ser el vector de estado uniforme indicado anteriormente y están interesados en medir el primer qubit, entonces 

$ $ P (\text{Measurement de primer qubit} = 1) = (\psi ^ \dagger e_2) (e_2 ^ \dagger \psi) + (\psi ^ \dagger e_3) (e_3 ^ \dagger \psi) = | e_2 ^ \dagger \psi | ^ 2 + | e_3 ^ \dagger \psi | ^ 2.
$$

Tenga en cuenta que esto es solo la suma de las dos probabilidades que se esperarían para medir los resultados $10 $ y $11 $ que se medieron todos los qubits.
En nuestro ejemplo, se evalúa como

$ $ \frac{1}{4}\left | \begin{bmatrix}0 & 0 & 1 & 0 \ end {bmatrix} \ Begin {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \right | ^ 2 + \frac{1}{4}\left | \begin{bmatrix}0 & 0 & 0 & 1 \ end {bmatrix} \ Begin {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \right | ^ 2 = \frac{1}{2}.
$$

que coincide perfectamente con el Intuition que nos indica que la probabilidad debe ser.  Del mismo modo, el estado se puede escribir como

$ $ \frac{\frac{e_2}{2}+ \frac{e_3}{2}} {\sqrt{\frac{1}{2}}} = \frac{1}{\sqrt{2}} \begin{bmatrix} 0\\\\ 0\\\\ 1\\\\ 1 \ end {bmatrix} $ $

de nuevo de acuerdo con nuestro Intuition.

## <a name="two-qubit-operations"></a>Dos operaciones de qubit
Como en el caso de una sola qubit, cualquier transformación unitario es una operación válida en qubits. En general, una transformación unitario en $n $ qubits es una matriz $U $ de tamaño $2 ^ n \times 2 ^ n $ (para que actúe en vectores de tamaño $2 ^ n $), de modo que $U ^{-1} = U ^ \dagger $. Por ejemplo, la puerta CNOT (controlada-NOT) es una puerta de dos qubits de uso frecuente y se representa mediante la siguiente matriz de unitario:

$ $ \operatorname{CNOT} = \begin{bmatrix} 1 \ 0 \ 0 \ 0 \\\\ 0 \ 1 \ 0 \ 0 \\\\ 0 \ 0 \ 0 \ 1 \\\\ 0 \ 0 \ 1 \ 0 \end{bmatrix} $ $

También podemos formar dos puertas qubit mediante la aplicación de puertas de qubit único en ambos qubits. Por ejemplo, si se aplican las contrataciones 

$ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} $ $

y

$ $ \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} $ $

en el primer y segundo qubits, respectivamente, esto es equivalente a aplicar la unitario de dos qubit proporcionada por su producto tensores: $ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} = \begin{bmatrix} AE \ AF \ es \ BF \\\\ AG \ ah \ BG \ BH \\\\ CE \ CF \ de \ DF \\\\ CG \ CH \ DG \ DH \end{bmatrix}. $ $, por lo que podemos formar dos puertas qubit tomando el producto tensores de algunas puertas de qubit único conocidas. Algunos ejemplos de puertas de dos qubit incluyen $H \otimes H $, $X \otimes \boldone $ y $X \otimes Z $.

Tenga en cuenta que, mientras que las dos puertas de un solo qubit definen una puerta de dos qubit mediante la toma de su producto tensores, lo contrario no es cierto. No todas las puertas de dos qubit se pueden escribir como el producto tensores de las puertas de qubit único.  Este tipo de puerta se denomina puerta de *inenredo* . Un ejemplo de una puerta de inenredo es la puerta CNOT.

El Intuition detrás de una puerta controlada y no se puede generalizar a las puertas arbitrarias.  Una puerta controlada en general es una puerta que actúa como identidad (es decir, no tiene ninguna acción) a menos que un qubit específico sea $1 $.  Denotamos una unidad de qubit controlada, que se controla en este caso en el con la etiqueta $x $, con un $ \Lambda\_x (U) $.  Por ejemplo, $ \ Lambda_0 (U) e\_{1}\otimes {\psi} = e\_{1}\otimes U {\psi} $ y $ \Lambda\_0 (U) e\_{0}\otimes {\psi} = e\_{0}\otimes{\psi} $, donde $e\_$0 y $e\_$1 son los vectores de base de cálculo para una única qubit correspondiente a los valores $0 $ y $1 $.  Por ejemplo, considere el siguiente control controlado $Z $ Gate que podemos expresar como $ $ \Lambda\_0 (Z) = \begin{bmatrix}1 & 0 & 0 & 0\\\\0 & 1 & 0 & 0\\\\0 & 0 & 1 & 0\\\\0 & 0 & 0 &-1 \end{bmatrix} = (\boldone\otimes H) \operatorname{CNOT} (\boldone\otimes H).
$$

La creación de unitaries controlados de forma eficaz es un desafío importante.  La manera más sencilla de implementar esto requiere formar una base de datos de versiones controladas de las puertas fundamentales y reemplazar cada puerta fundamental en la operación unitario original con su homólogo controlado.  A menudo, esto es bastante excesivo y, a menudo, se puede usar para reemplazar algunas puertas con versiones controladas para lograr el mismo impacto.  Por esta razón, proporcionamos en nuestro marco la capacidad de realizar el método Naive para controlar o permitir al usuario definir una versión controlada de la unitario si se conoce una versión optimizada de forma manual.

Las puertas también se pueden controlar mediante información clásica.  Por ejemplo, una puerta sin control controlada por clases, por ejemplo, es simplemente una no puerta normal, pero solo se aplica si un bit clásico es $1 $ en lugar de un bit de Quantum.  En este sentido, una puerta controlada por clases puede considerarse como una instrucción if en el código Quantum, donde la puerta se aplica solo en una bifurcación del código.


Al igual que en el caso de un solo qubit, un conjunto de puertas de dos qubit es universal si cualquier matriz de la unitario $4 \ Times $4 puede ser aproximada por un producto de las puertas de este conjunto a una precisión arbitraria.
Un ejemplo de un conjunto de puerta universal es la puerta Hadamard, la puerta T y la puerta CNOT. Mediante la toma de los productos de estas puertas, podemos aproximar cualquier matriz de unitarios en dos qubits.

## <a name="many-qubit-systems"></a>Muchos sistemas qubit
Seguimos exactamente los mismos patrones explorados en el caso de dos qubit para compilar los Estados de Quantum de varios qubit desde sistemas más pequeños.  Estos Estados se crean formando productos tensores de Estados más pequeños.  Por ejemplo, considere la posibilidad de codificar la cadena de bits $1011001 $ en un equipo Quantum.  Podemos codificarlo como

$ $1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}.
$$

Las puertas de Quantum funcionan exactamente de la misma manera.  Por ejemplo, si deseamos aplicar el $X $ Gate al primer qubit y, a continuación, realizar una CNOT entre el segundo y el tercer qubits, podremos expresar esta transformación como

\begin{align} & (X \otimes \operatorname{CNOT}_{12}\otimes \boldone\otimes \boldone \otimes \boldone \otimes \boldone) \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\\\\ & \qquad\qquad\equiv 0011001.
\end{align}

En muchos sistemas qubit, a menudo es necesario asignar y anular la asignación de qubits que sirvan como memoria temporal para el equipo Quantum.  Este tipo de qubit se denomina ancilla.  De forma predeterminada, suponemos que el estado de qubit se inicializa en $e _0 $ tras la asignación.  También se da por hecho que se devuelve de nuevo a $e _0 $ antes de la anulación de la asignación.  Esta suposición es importante porque si un qubit de ancilla se pone inhabilitado con otro registro qubit cuando se anula su asignación, el proceso de anulación de asignación dañará el ancilla.  Por esta razón, siempre suponemos que estas qubits se revierten a su estado inicial antes de que se lancen.

Por último, aunque es necesario agregar nuevas puertas a nuestro conjunto de pruebas para lograr la informática universal de Quantum para dos equipos Quantum de qubit, no es necesario introducir nuevas puertas en el caso de varios qubit.  Las puertas $H $, $T $ y CNOT forman una puerta universal establecida en muchos qubits porque cualquier transformación de unitario general se puede dividir en una serie de dos rotaciones qubit.  A continuación, podemos aprovechar la teoría desarrollada para el caso de dos qubit y volver a usarla aquí cuando tengamos muchos qubits.

Aunque la notación algebraico lineal que hemos usado hasta ahora se puede usar para describir los Estados de varios qubit, se vuelve cada vez más complicada a medida que aumentamos el tamaño de los Estados.  El vector de columna resultante para una cadena de longitud de 7 bits, por ejemplo, es $128 $ dimensional, lo que permite expresarlo mediante la notación descrita anteriormente como muy engorroso.  Por esta razón, a continuación presentamos una notación común en la informática Quantum que nos permite describir de forma concisa estos vectores de gran dimensionalidad.
