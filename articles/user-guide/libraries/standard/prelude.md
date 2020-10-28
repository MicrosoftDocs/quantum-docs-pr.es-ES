---
title: Operaciones intrínsecas y funciones en QDK
description: Obtenga información sobre las operaciones intrínsecas y las funciones de QDK, incluidas las funciones clásicas y las operaciones de unitario, rotación y medición.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.prelude
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4d15226fe46be79b7d3e6f414f33f1debd691f40
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692126"
---
# <a name="the-prelude"></a>El preparador #

El Q# compilador y las máquinas de destino incluidas en el kit de desarrollo de Quantum proporcionan un conjunto de funciones y operaciones intrínsecas que se pueden usar al escribir programas Quantum en Q# .

## <a name="intrinsic-operations-and-functions"></a>Operaciones y funciones intrínsecas ##

Las operaciones intrínsecas definidas en la biblioteca estándar se encuentran aproximadamente en una de varias categorías:

- Funciones clásicas esenciales, recopiladas en el <xref:Microsoft.Quantum.Core> espacio de nombres.
- Operaciones que representan unitaries formada por [Clifford y $T $ Gates](xref:microsoft.quantum.concepts.qubit).
- Operaciones que representan rotaciones sobre varios operadores.
- Operaciones que implementan medidas.

Dado que el conjunto de Clifford + $T $ Gate es [universal](xref:microsoft.quantum.concepts.multiple-qubits) para la informática Quantum, estas operaciones bastan para implementar de forma aproximada cualquier algoritmo Quantum en un error poco significativo.
Al proporcionar también giros, permite al Q# programador trabajar en una sola biblioteca de qubit y CNOT. Es mucho más fácil pensar en esta biblioteca porque no requiere que el programador exprese directamente la descomposición Clifford + $T $ y porque existen métodos muy eficaces para compilar una unitaries de qubit única en Clifford y $T $ Gates (vea [aquí](xref:microsoft.quantum.more-information) para obtener más información).

Siempre que sea posible, las operaciones definidas en el ejemplo que actúan en qubits permiten aplicar la `Controlled` variante, de modo que el equipo de destino realizará la descomposición adecuada.

Muchas de las funciones y operaciones definidas en esta parte del preparado se encuentran en el @"microsoft.quantum.intrinsic" espacio de nombres, de modo que la mayoría de Q# los archivos de código fuente tendrán una `open Microsoft.Quantum.Intrinsic;` Directiva inmediatamente después de la declaración de espacio de nombres inicial.
El <xref:Microsoft.Quantum.Core> espacio de nombres se abre automáticamente, por lo que las funciones como <xref:Microsoft.Quantum.Core.Length> se pueden usar sin una `open` instrucción.

### <a name="common-single-qubit-unitary-operations"></a>Operaciones de unitarios Single-Qubit comunes ###

El predefinido también define muchas [operaciones de qubit único](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)comunes.
Todas estas operaciones permiten tanto los `Controlled` como los `Adjoint` funcdores.

#### <a name="pauli-operators"></a>Operadores Pauli ####

La <xref:Microsoft.Quantum.Intrinsic.X> operación implementa el operador Pauli $X $.
A veces, esto también se conoce como la `NOT` puerta.
Tiene la firma `(Qubit => Unit is Adj + Ctl)` .
Corresponde a la unitario de un solo qubit:

\begin{Equation} \begin{bmatrix} 0 & 1 \\ \\ % FIXME: actualmente utiliza la quadwhack hack.
1 & 0 \end{bmatrix} \end{Equation}

La <xref:Microsoft.Quantum.Intrinsic.Y> operación implementa el operador Pauli $Y $.
Tiene la firma `(Qubit => Unit is Adj + Ctl)` .
Corresponde a la unitario de un solo qubit:

\begin{Equation} \begin{bmatrix} 0 &-i \\ \\ % FIXME: actualmente usa la quadwhack hack.
i & 0 \end{bmatrix} \end{Equation}

La <xref:Microsoft.Quantum.Intrinsic.Z> operación implementa el operador Pauli $Z $.
Tiene la firma `(Qubit => Unit is Adj + Ctl)` .
Corresponde a la unitario de un solo qubit:

\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % FIXME: actualmente usa la quadwhack hack.
0 &-1 \end{bmatrix} \end{Equation}

A continuación se muestran estas transformaciones asignadas a la [esfera Bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (el eje de giro de cada caso se resalta en rojo):

![Pauli operaciones asignadas a la esfera Bloch](~/media/prelude_pauliBloch.png)

Es importante tener en cuenta que la aplicación de la misma puerta Pauli dos veces al mismo qubit cancela la operación (porque ya ha realizado una rotación completa de 2π (360 °) sobre la superficie en la esfera Bloch, lo que llega al punto inicial). Esto nos lleva a la siguiente identidad:

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $

Esto se puede visualizar en la esfera Bloch:

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>Otros Single-Qubit Cliffords ####

La <xref:Microsoft.Quantum.Intrinsic.H> operación implementa la puerta Hadamard.
Esto intercambia los ejes Pauli $X $ y $Z $ del qubit de destino, de modo que $H \ket {0} = \ket{+} \mathrel{: =} (\ket {0} + \ket {1} )/\sqrt {2} $ y $H \ket{+} = \ket {0} $.
Tiene la firma `(Qubit => Unit is Adj + Ctl)` y corresponde a la unitario de un solo qubit:

\begin{Equation} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ % FIXME: actualmente usa el quadwhack hack.
1 &-1 \end{bmatrix} \end{Equation}

La puerta Hadamard es especialmente importante, ya que se puede usar para crear una superposición de los Estados $ \ket {0} $ y $ \ket {1} $. En la representación de la esfera Bloch, es más fácil pensar en esto como un giro de $ \ket{\psi} $ alrededor del eje x por $ \pi $ radianes ($ 180 ^ \circ $) seguido de un giro (en el sentido de las agujas del reloj) alrededor del eje y por $ \ pi/2 $ radianes ($ 90 ^ \circ $):

![Operación Hadamard asignada en la esfera Bloch](~/media/prelude_hadamardBloch.png)

La <xref:Microsoft.Quantum.Intrinsic.S> operación implementa la puerta de fase $S $.
Esta es la raíz cuadrada de la matriz de la operación Pauli $Z $.
Es decir, $S ^ 2 = Z $.
Tiene la firma `(Qubit => Unit is Adj + Ctl)` y corresponde a la unitario de un solo qubit:

\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % FIXME: actualmente usa la quadwhack hack.
0 & \end{bmatrix} \end{Equation}

#### <a name="rotations"></a>Rotaciones ####

Además de las operaciones Pauli y Clifford anteriores, el prepárrafo Q# proporciona diversas formas de expresar los giros.
Tal y como se describe en [operaciones de un solo qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), la capacidad de rotar es fundamental para los algoritmos Quantum.

Empezamos por volver a llamar a que podemos expresar cualquier operación de un solo qubit con las $H $ y $T $ Gates, donde $H $ es la operación Hadamard y donde \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ % FIXME: actualmente utiliza la versión más actualizada de la cuádruple Whack hack.
0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} es la raíz cuadrada de la <xref:Microsoft.Quantum.Intrinsic.S> operación, de modo que $T ^ 2 = S $.
A su vez, el $T $ Gate lo implementa la <xref:Microsoft.Quantum.Intrinsic.T> operación y tiene la firma `(Qubit => Unit is Adj + Ctl)` , lo que indica que se trata de una operación unitario en un solo qubit.

Aunque esto es lo más adecuado para describir cualquier operación de un solo qubit arbitrario, las diferentes máquinas de destino pueden tener representaciones más eficaces para las rotaciones sobre los operadores de Pauli, de modo que el predicho incluye diversas maneras de convienently expresar tales giros.
La más básica de esto es la <xref:Microsoft.Quantum.Intrinsic.r> operación, que implementa una rotación alrededor de un eje Pauli especificado, \Begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation} donde $ \sigma $ es un operador Pauli, $ \phi $ es un ángulo y donde $ \exp $ representa la matriz exponencial.
Tiene una firma `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` , donde las dos primeras partes de la entrada representan los argumentos clásicos $ \sigma $ y $ \phi $ necesarios para especificar el operador unitario $R (\sigma, \phi) $.
Podemos aplicar parcialmente $ \sigma $ y $ \phi $ para obtener una operación cuyo tipo sea el de una sola qubit unitario.
Por ejemplo, `R(PauliZ, PI() / 4, _)` tiene el tipo `(Qubit => Unit is Adj + Ctl)` .

> [!NOTE]
> La <xref:Microsoft.Quantum.Intrinsic.r> operación divide el ángulo de entrada en 2 y lo multiplica por-1.
> En el caso de los giros de $Z $, esto significa que $ \ket {0} $ eigenstate está girado por $-\phi/$2 y $ \ket {1} $ eigenstate se gira en $ \phi/$2, de modo que $ \ket $ {1} eigenstate gira en relación con $ \phi $ {0} \ket.
>
> En concreto, esto significa que `T` y `R(PauliZ, PI() / 8, _)` solo difieren en una [fase global](xref:microsoft.quantum.glossary#global-phase)irrelevante.
> Por esta razón, a veces $T $ se conoce como $ \frac{\pi} {8} $-Gate.
>
> Tenga en cuenta también que `PauliI` la rotación solo aplica una fase global de $ \phi/$2. Aunque estas fases son irrelevantes, como se argumenta en [los documentos conceptuales](xref:microsoft.quantum.concepts.qubit), son relevantes para las `PauliI` rotaciones controladas.

Dentro de los algoritmos Quantum, a menudo resulta útil expresar giros como fracciones de Dyadic, como $ \phi = \pi k/2 ^ n $ para algunos $k \en \mathbb{Z} $ y $n \en \mathbb{N} $.
La <xref:Microsoft.Quantum.Intrinsic.RFrac> operación implementa una rotación alrededor de un eje Pauli especificado mediante esta Convención.
Se diferencia de <xref:Microsoft.Quantum.Intrinsic.R> en que el ángulo de rotación se especifica como dos entradas de tipo `Int` , que se interpretan como una fracción Dyadic.
Por lo tanto, `RFrac` tiene Signature `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` .
Implementa el qubit unitario $ \exp (i \pi k \sigma/2 ^ n) $, donde $ \sigma $ es la matriz de Pauli correspondiente al primer argumento, $k $ es el segundo argumento y $n $ es el tercer argumento.
`RFrac(_,k,n,_)` es igual que `R(_,-πk/2^n,_)` ; tenga en cuenta que el ángulo es el *negativo* de la fracción.

La <xref:Microsoft.Quantum.Intrinsic.Rx> operación implementa un giro alrededor del Pauli $X $ Axis.
Tiene la firma `((Double, Qubit) => Unit is Adj + Ctl)` .
`Rx(_, _)` es igual que `R(PauliX, _, _)`.

La <xref:Microsoft.Quantum.Intrinsic.Ry> operación implementa un giro alrededor del Pauli $Y $ Axis.
Tiene la firma `((Double, Qubit) => Unit is Adj + Ctl)` .
`Ry(_, _)` es igual que `R(PauliY,_ , _)`.

La <xref:Microsoft.Quantum.Intrinsic.Rz> operación implementa un giro alrededor del Pauli $Z $ axis.
Tiene la firma `((Double, Qubit) => Unit is Adj + Ctl)` .
`Rz(_, _)` es igual que `R(PauliZ, _, _)`.

La <xref:Microsoft.Quantum.Intrinsic.R1> operación implementa una rotación en la cantidad determinada alrededor de $ \ket {1} $, el eigenstate de $-$1 de $Z $.
Tiene la firma `((Double, Qubit) => Unit is Adj + Ctl)` .
`R1(phi,_)` es igual que `R(PauliZ,phi,_)` seguido de `R(PauliI,-phi,_)` .

La <xref:Microsoft.Quantum.Intrinsic.R1Frac> operación implementa una rotación fraccionaria en la cantidad determinada alrededor de la Z = 1 eigenstate.
Tiene la firma `((Int,Int, Qubit) => Unit is Adj + Ctl)` .
`R1Frac(k,n,_)` es igual que `RFrac(PauliZ,-k.n+1,_)` seguido de `RFrac(PauliI,k,n+1,_)` .

A continuación se muestra un ejemplo de una operación de giro (alrededor del Pauli $Z $ axis, en esta instancia) asignada en la esfera Bloch:

![Operación de rotación asignada en la esfera Bloch](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>Operaciones de qubit múltiple ####

Además de las operaciones de un solo qubit, el predicho también define varias operaciones de varios qubit.

En primer lugar, la <xref:Microsoft.Quantum.Intrinsic.CNOT> operación realiza una puerta controlada estándar `NOT` , \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}.
\end{Equation} tiene una firma `((Qubit, Qubit) => Unit is Adj + Ctl)` que representa que $ \operatorname{CNOT} $ actúa unitarily en dos qubits individuales.
`CNOT(q1, q2)` es igual que `(Controlled X)([q1], q2)`.
Dado que el `Controlled` functor permite controlar en un registro, usamos el literal de matriz `[q1]` para indicar que queremos solo el control.

La <xref:Microsoft.Quantum.Intrinsic.CCNOT> operación realiza un control no controlado de doble control, a veces también conocido como la puerta Toffoli.
Tiene la firma `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` .
`CCNOT(q1, q2, q3)` es igual que `(Controlled X)([q1, q2], q3)`.

La <xref:Microsoft.Quantum.Intrinsic.SWAP> operación intercambia los Estados de Quantum de dos qubits.
Es decir, implementa la matriz unitario \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}.
\end{Equation} tiene una firma `((Qubit, Qubit) => Unit is Adj + Ctl)` .
`SWAP(q1,q2)` es equivalente a `CNOT(q1, q2)` seguido de `CNOT(q2, q1)` y después de `CNOT(q1, q2)` .

> [!NOTE]
> La puerta de intercambio *no* es lo mismo que reorganizar los elementos de una variable con el tipo `Qubit[]` .
> La aplicación `SWAP(q1, q2)` de produce un cambio en el estado de qubits al que hace referencia `q1` y `q2` , mientras que `let swappedRegister = [q2, q1];` solo afecta a cómo hacemos referencia a esos qubits.
> Además, `(Controlled SWAP)([q0], (q1, q2))` permite `SWAP` que se ordene en el estado de un tercer qubit, que no se puede representar mediante la reorganización de los elementos.
> La puerta de intercambio controlado, también conocida como la puerta Fredkin, es lo suficientemente eficaz como para incluir todo el cálculo clásico.

Por último, el predicho proporciona dos operaciones para representar los exponenciales de los operadores de Pauli de varios qubit.
La <xref:Microsoft.Quantum.Intrinsic.Exp> operación realiza una rotación basada en un producto tensores de matrices Pauli, tal como se representa en la qubit unitario \Begin{Equation} \operatorname{exp} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right), \end{Equation} donde $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \dots, \ sigma_n) $ es una secuencia de operadores qubit de Pauli y donde $ \phi $ es un ángulo.
La `Exp` rotación representa $ \vec{\sigma} $ como una matriz de `Pauli` elementos, de modo que tiene la firma `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` .

La <xref:Microsoft.Quantum.Intrinsic.ExpFrac> operación realiza la misma rotación mediante la notación de fracción Dyadic descrita anteriormente.
Tiene la firma `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` .

> [!WARNING]
> Los exponenciales del producto tensores de los operadores Pauli no son los mismos que los de tensores los de los operadores exponencial de Pauli.
> Es decir, $e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.

### <a name="measurements"></a>Medidas ###

Al medir, el eigenvalue + 1 del operador que se está midiendo corresponde a un `Zero` resultado y el-1 eigenvalue a un `One` resultado.

> [!NOTE]
> Aunque esta Convención podría parecer extraña, tiene dos ventajas muy ventajosas.
> En primer lugar, la observación del resultado $ \ket {0} $ se representa mediante el `Result` valor `Zero` , mientras que la observación de $ \ket {1} $ corresponde a `One` .
> En segundo lugar, podemos escribir que el eigenvalue $ \lambda $ correspondiente a un resultado $r $ es $ \lambda = (-1) ^ r $.

Las operaciones de medición no admiten `Adjoint` ni el `Controlled` functor.

La <xref:Microsoft.Quantum.Intrinsic.Measure> operación realiza una medición conjunta de uno o más qubits en el producto especificado de los operadores Pauli.
Si la matriz Pauli y la matriz qubit tienen longitudes diferentes, se produce un error en la operación.
`Measure` tiene una firma `((Pauli[], Qubit[]) => Result)` .

Tenga en cuenta que una medida conjunta no es lo mismo que medir cada qubit individualmente.
Por ejemplo, considere el estado $ \ket {11} = \ket {1} \otimes \Ket {1} = X\otimes X \ket {00} $.
Al medir $Z _0 $ y $Z _ 1 _ cada uno individualmente, obtenemos los resultados $r _0 = $1 y $r _ 1 = $1.
Al medir $Z _0 Z_1 $, se obtiene el resultado único $r _ {\textrm{Joint}} = $0, que representa que la pareja de $ \ket {11} $ es positiva.
Se colocan de forma diferente, $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{Joint}}) $.
De forma crítica, dado que *solo* se aprende la paridad a partir de esta medida, se conserva toda la información de Quantum representada en la superposición entre los Estados 2 2-qubit de paridad positiva, $ \ket {00} $ y $ \ket {11} $.
Esta propiedad será esencial más adelante, ya que se describe la corrección de errores.

Para mayor comodidad, el predicho también proporciona otras dos operaciones para medir qubits.
En primer lugar, dado que la realización de medidas de un solo qubit es bastante común, el pre define una abreviatura para este caso.
La <xref:Microsoft.Quantum.Intrinsic.M> operación mide el operador Pauli $Z $ en un solo qubit y tiene Signature `(Qubit => Result)` .
`M(q)` equivale a `Measure([PauliZ], [q])`.

<xref:microsoft.quantum.measurement.MultiM>Mide el operador Pauli $Z $ *por separado* en cada una de las matrices de qubits, devolviendo la *matriz* de `Result` valores obtenidos para cada qubit.
En algunos casos, esto se puede optimizar. Tiene Signature ( `Qubit[] => Result[])` .
`MultiM(qs)` es equivalente a:

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a>Funciones y operaciones de extensión ##

Además, el pretexto define un amplio conjunto de funciones matemáticas y de conversión de tipos en el nivel de .NET para su uso en el Q# código.
Por ejemplo, el <xref:Microsoft.Quantum.Math> espacio de nombres define operaciones útiles como <xref:Microsoft.Quantum.Math.Sin> y <xref:Microsoft.Quantum.Math.Log> .
La implementación proporcionada por el kit de desarrollo de Quantum usa la biblioteca de clases base de .NET clásica y, por lo tanto, puede implicar un viaje de ida y vuelta de comunicaciones adicional entre programas Quantum y sus controladores clásico.
Aunque esto no presenta un problema para un simulador local, puede tratarse de un problema de rendimiento al usar un simulador remoto o un hardware real como equipo de destino.
Dicho esto, una máquina de destino individual puede mitigar este impacto en el rendimiento invalidando estas operaciones con versiones más eficaces para ese sistema en particular.

### <a name="math"></a>Matemáticas ###

El <xref:Microsoft.Quantum.Math> espacio de nombres proporciona muchas funciones útiles de la [ `System.Math` clase](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1&preserve-view=true)de la biblioteca de clases base de .net.
Estas funciones se pueden usar de la misma manera que cualquier otra Q# función:

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

Cuando un método estático de .NET se ha sobrecargado según el tipo de sus argumentos, la Q# función correspondiente se anota con un sufijo que indica el tipo de su entrada:

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>Operaciones bit a bit ###

Por último, el <xref:Microsoft.Quantum.Bitwise> espacio de nombres proporciona varias funciones útiles para manipular enteros a través de operadores bit a bit.
Por ejemplo, <xref:Microsoft.Quantum.Bitwise.Parity> devuelve la paridad bit a bit de un entero como otro entero.
