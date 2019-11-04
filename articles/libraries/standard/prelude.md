---
title: Bibliotecas estándar de preguntas y respuestas Microsoft Docs
description: 'Bibliotecas estándar de preguntas y respuestas: preparadas'
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: dddb3d4a5ebcdca16da41a5ae5520d98ea900a7f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73183240"
---
# <a name="the-prelude"></a>El preparador #

El compilador de Q # y las máquinas de destino incluidas con el kit de desarrollo de Quantum proporcionan un conjunto de funciones y operaciones intrínsecas que se pueden usar al escribir programas Quantum en Q #.

## <a name="intrinsic-operations-and-functions"></a>Operaciones y funciones intrínsecas ##

Las operaciones intrínsecas definidas en la biblioteca estándar se encuentran aproximadamente en una de varias categorías:

- Funciones clásicas esenciales, recopiladas en el espacio de nombres <xref:microsoft.quantum.core>.
- Operaciones que representan unitaries formada por [Clifford y $T $ Gates](xref:microsoft.quantum.concepts.qubit).
- Operaciones que representan rotaciones sobre varios operadores.
- Operaciones que implementan medidas.

Dado que el conjunto de Clifford + $T $ Gate es [universal](xref:microsoft.quantum.concepts.multiple-qubits) para la informática Quantum, estas operaciones bastan para implementar de forma aproximada cualquier algoritmo Quantum en un error poco significativo.
Al proporcionar también rotaciones, Q # permite al programador trabajar en la biblioteca única de qubit unitario y CNOT Gate Library. Es mucho más fácil pensar en esta biblioteca, ya que no requiere que el programador exprese directamente la descomposición Clifford + $T $ y porque existen métodos muy eficaces para compilar una unitaries de qubit única en Clifford y $T $ Gates (vea [aquí](xref:microsoft.quantum.more-information) para obtener más información).

Siempre que sea posible, las operaciones definidas en el ejemplo que actúan en qubits permiten aplicar el `Controlled` variante, de modo que el equipo de destino realice la descomposición adecuada.

Muchas de las funciones y operaciones definidas en esta parte del preparado se encuentran en el espacio de nombres @"microsoft.quantum.intrinsic", de modo que la mayoría de los archivos de código fuente Q # tendrán una directiva `open Microsoft.Quantum.Intrinsic;` inmediatamente después de la declaración inicial del espacio de nombres.
El espacio de nombres <xref:microsoft.quantum.core> se abre automáticamente, por lo que las funciones como <xref:microsoft.quantum.core.length> se pueden usar sin una instrucción `open` en absoluto.

### <a name="common-single-qubit-unitary-operations"></a>Operaciones de unitarios de un solo qubit comunes ###

El predefinido también define muchas [operaciones de qubit único](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)comunes.
Todas estas operaciones permiten los funcdores `Controlled` y `Adjoint`.

#### <a name="pauli-operators"></a>Operadores Pauli ####

La operación <xref:microsoft.quantum.intrinsic.x> implementa el operador Pauli $X $.
A veces, esto también se conoce como la puerta de `NOT`.
Tiene `(Qubit => Unit is Adj + Ctl)`de firma.
Corresponde a la unitario de un solo qubit:

\begin{Equation} \begin{bmatrix} 0 & 1 \\\\% FIXME: actualmente utiliza la quadwhack hack.
1 & 0 \end{bmatrix} \end{Equation}

La operación <xref:microsoft.quantum.intrinsic.y> implementa el operador Pauli $Y $.
Tiene `(Qubit => Unit is Adj + Ctl)`de firma.
Corresponde a la unitario de un solo qubit:

\begin{Equation} \begin{bmatrix} 0 &-i \\\\% FIXME: actualmente utiliza la quadwhack hack.
i & 0 \end{bmatrix} \end{Equation}

La operación <xref:microsoft.quantum.intrinsic.z> implementa el operador Pauli $Z $.
Tiene `(Qubit => Unit is Adj + Ctl)`de firma.
Corresponde a la unitario de un solo qubit:

\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: actualmente utiliza la quadwhack hack.
0 &-1 \end{bmatrix} \end{Equation}

A continuación se muestran estas transformaciones asignadas a la [esfera Bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (el eje de giro de cada caso se resalta en rojo):

![Pauli operaciones asignadas a la esfera Bloch](~/media/prelude_pauliBloch.png)

Es importante tener en cuenta que la aplicación de la misma puerta Pauli dos veces al mismo qubit cancela la operación (porque ya ha realizado una rotación completa de 2π (360 °) sobre la superficie en la esfera Bloch, lo que llega al punto inicial). Esto nos lleva a la siguiente identidad:

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $

Esto se puede visualizar en la esfera Bloch:

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>Otro Cliffords de qubit único ####

La operación <xref:microsoft.quantum.intrinsic.h> implementa la puerta Hadamard.
Esto intercambia los ejes Pauli $X $ y $Z $ del qubit de destino, de modo que $H \ket{0} = \ket{+} \mathrel{: =} (\ket{0} + \ket{1})/\sqrt{2}$ y $H \ket{+} = \ket{0}$.
Tiene `(Qubit => Unit is Adj + Ctl)`de firma y corresponde a la unitario de un solo qubit:

\begin{Equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\% FIXME: actualmente usa el quadwhack hack.
1 &-1 \end{bmatrix} \end{Equation}

La puerta Hadamard es especialmente importante, ya que se puede usar para crear una superposición de $ \ket{0}$ y $ \ket{1}$ States. En la representación de la esfera Bloch, es más fácil pensar en esto como un giro de $ \ket{\psi} $ alrededor del eje x por $ \pi $ radianes ($ 180 ^ \circ $) seguido de un giro (en el sentido de las agujas del reloj) alrededor del eje y por $ \ pi/2 $ radianes ($ 90 ^ \circ $):

![Operación Hadamard asignada en la esfera Bloch](~/media/prelude_hadamardBloch.png)

La operación <xref:microsoft.quantum.intrinsic.s> implementa la puerta de fase $S $.
Esta es la raíz cuadrada de la matriz de la operación Pauli $Z $.
Es decir, $S ^ 2 = Z $.
Tiene `(Qubit => Unit is Adj + Ctl)`de firma y corresponde a la unitario de un solo qubit:

\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: actualmente utiliza la quadwhack hack.
0 & \end{bmatrix} \end{Equation}

#### <a name="rotations"></a>Rotaciones ####

Además de las operaciones Pauli y Clifford anteriores, el prepárrafo de preguntas y respuestas proporciona diversas formas de expresar los giros.
Tal y como se describe en [operaciones de un solo qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), la capacidad de rotar es fundamental para los algoritmos Quantum.

Empezamos por volver a llamar a que podemos expresar cualquier operación de un solo qubit con las $H $ y $T $ Gates, donde $H $ es la operación Hadamard y donde \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\\\% FIXME: actualmente utiliza la versión cuádruple Whack hack.
0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} es la raíz cuadrada de la operación de <xref:microsoft.quantum.intrinsic.s>, de modo que $T ^ 2 = S $.
A su vez, el $T $ Gate lo implementa la operación de <xref:microsoft.quantum.intrinsic.t> y tiene `(Qubit => Unit is Adj + Ctl)`de firma, lo que indica que se trata de una operación unitario en un solo qubit.

Aunque esto es lo más adecuado para describir cualquier operación de un solo qubit arbitrario, diferentes equipos de destino pueden tener representaciones más eficaces para los giros sobre los operadores de Pauli, de modo que el predicho incluye diversas formas de convienently exprese estos giros.
La más básica es la operación <xref:microsoft.quantum.intrinsic.r>, que implementa una rotación alrededor de un eje Pauli especificado, \begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation} donde $ \sigma $ es un operador Pauli, $ \phi $ es un ángulo y donde $ \exp $ representa la matriz exponencial.
Tiene `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`de firma, donde las dos primeras partes de la entrada representan los argumentos clásicos $ \sigma $ y $ \phi $ necesarios para especificar el operador unitario $R (\sigma, \phi) $.
Podemos aplicar parcialmente $ \sigma $ y $ \phi $ para obtener una operación cuyo tipo sea el de una sola qubit unitario.
Por ejemplo, `R(PauliZ, PI() / 4, _)` tiene el tipo `(Qubit => Unit is Adj + Ctl)`.

> [!NOTE]
> La operación <xref:microsoft.quantum.intrinsic.r> divide el ángulo de entrada en 2 y lo multiplica por-1.
> En el caso de $Z $ rotations, esto significa que $ \ket{0}$ eigenstate está girado por $-\phi/$2 y el $ \ket{1}$ eigenstate está girado por $ \phi/$2, por lo que $ \ket $ eigenstate{1}$ \phi se rota en $ \ket $ en relación con $ eigenstate{0}$.
>
> En concreto, esto significa que `T` y `R(PauliZ, PI() / 8, _)` solo se diferencian en una [fase global](xref:microsoft.quantum.glossary#global-phase)irrelevante.
> Por esta razón, a veces $T $ se conoce como $ \frac{\pi}{8}$-Gate.
>
> Tenga en cuenta también que la rotación alrededor de `PauliI` aplica simplemente una fase global de $ \phi/$2. Aunque estas fases son irrelevantes, como se argumenta en [los documentos conceptuales](xref:microsoft.quantum.concepts.qubit), son relevantes para las rotaciones de `PauliI` controladas.

Dentro de los algoritmos Quantum, a menudo resulta útil expresar giros como fracciones de Dyadic, como $ \phi = \pi k/2 ^ n $ para algunos $k \en \mathbb{Z} $ y $n \en \mathbb{N} $.
La operación <xref:microsoft.quantum.intrinsic.rfrac> implementa una rotación alrededor de un eje Pauli especificado mediante esta Convención.
Difiere de <xref:microsoft.quantum.intrinsic.r> en que el ángulo de rotación se especifica como dos entradas de tipo `Int`, se interpreta como una fracción Dyadic.
Por lo tanto, `RFrac` tiene `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`de firma.
Implementa el qubit unitario $ \exp (i \pi k \sigma/2 ^ n) $, donde $ \sigma $ es la matriz de Pauli correspondiente al primer argumento, $k $ es el segundo argumento y $n $ es el tercer argumento.
`RFrac(_,k,n,_)` es igual que `R(_,-πk/2^n,_)`; Observe que el ángulo es el *negativo* de la fracción.

La operación <xref:microsoft.quantum.intrinsic.rx> implementa un giro alrededor del eje $ Pauli $X $.
Tiene `((Double, Qubit) => Unit is Adj + Ctl)`de firma.
`Rx(_, _)` es igual que `R(PauliX, _, _)`.

La operación <xref:microsoft.quantum.intrinsic.ry> implementa un giro alrededor del eje $ Pauli $Y $.
Tiene `((Double, Qubit) => Unit is Adj + Ctl)`de firma.
`Ry(_, _)` es igual que `R(PauliY,_ , _)`.

La operación <xref:microsoft.quantum.intrinsic.rz> implementa un giro alrededor del eje $ Pauli $Z $.
Tiene `((Double, Qubit) => Unit is Adj + Ctl)`de firma.
`Rz(_, _)` es igual que `R(PauliZ, _, _)`.

La operación <xref:microsoft.quantum.intrinsic.r1> implementa una rotación en la cantidad determinada alrededor de $ \ket{1}$, el eigenstate de $-$1 de $Z $.
Tiene `((Double, Qubit) => Unit is Adj + Ctl)`de firma.
`R1(phi,_)` es igual que `R(PauliZ,phi,_)` seguido de `R(PauliI,-phi,_)`.

La operación <xref:microsoft.quantum.intrinsic.r1frac> implementa una rotación fraccionaria en la cantidad determinada alrededor de la Z = 1 eigenstate.
Tiene `((Int,Int, Qubit) => Unit is Adj + Ctl)`de firma.
`R1Frac(k,n,_)` es igual que `RFrac(PauliZ,-k.n+1,_)` seguido de `RFrac(PauliI,k,n+1,_)`.

A continuación se muestra un ejemplo de una operación de giro (alrededor del Pauli $Z $ axis, en esta instancia) asignada en la esfera Bloch:

![Operación de rotación asignada en la esfera Bloch](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>Operaciones de qubit múltiple ####

Además de las operaciones de un solo qubit, el predicho también define varias operaciones de varios qubit.

En primer lugar, la operación de <xref:microsoft.quantum.intrinsic.cnot> realiza una puerta de`NOT` controlada estándar, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.
\end{Equation} tiene `((Qubit, Qubit) => Unit is Adj + Ctl)`de firma, que representa que $ \operatorname{CNOT} $ actúa unitarily en dos qubits individuales.
`CNOT(q1, q2)` es igual que `(Controlled X)([q1], q2)`.
Dado que el `Controlled` functor permite controlar en un registro, usamos el literal de matriz `[q1]` para indicar que queremos solo el control.

La operación <xref:microsoft.quantum.intrinsic.ccnot> realiza una puerta que no tiene un control doble y, a veces, también se conoce como la puerta Toffoli.
Tiene `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`de firma.
`CCNOT(q1, q2, q3)` es igual que `(Controlled X)([q1, q2], q3)`.

La operación <xref:microsoft.quantum.intrinsic.swap> intercambia los Estados de Quantum de dos qubits.
Es decir, implementa la matriz unitario \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.
\end{Equation} tiene `((Qubit, Qubit) => Unit is Adj + Ctl)`de firma.
`SWAP(q1,q2)` es equivalente a `CNOT(q1, q2)` seguido de `CNOT(q2, q1)` y, a continuación, `CNOT(q1, q2)`.

> [!NOTE]
> La puerta de intercambio *no* es lo mismo que reorganizar los elementos de una variable con el tipo `Qubit[]`.
> La aplicación de `SWAP(q1, q2)` produce un cambio en el estado del qubits al que hace referencia `q1` y `q2`, mientras que `let swappedRegister = [q2, q1];` solo afecta a la forma en que hacemos referencia a esos qubits.
> Además, `(Controlled SWAP)([q0], (q1, q2))` permite que `SWAP` se ordene en el estado de un tercer qubit, que no se puede representar mediante la reorganización de los elementos.
> La puerta de intercambio controlado, también conocida como la puerta Fredkin, es lo suficientemente eficaz como para incluir todo el cálculo clásico.

Por último, el predicho proporciona dos operaciones para representar los exponenciales de los operadores de Pauli de varios qubit.
La operación de <xref:microsoft.quantum.intrinsic.exp> realiza una rotación basada en un producto tensores de matrices Pauli, tal como se representa en la qubit unitario \begin{Equation} \operatorname{Exp} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \sigma_0 \otimes \sigma_1 \otimes \ cdots \otimes \sigma_n \right), \end{Equation} donde $ \vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n) $ es una secuencia de operadores de qubit únicos y donde $ Pauli $ es un ángulo.
La rotación de `Exp` representa $ \vec{\sigma} $ como una matriz de elementos `Pauli`, de modo que tiene `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`de firma.

La operación de <xref:microsoft.quantum.intrinsic.expfrac> realiza la misma rotación mediante la notación de fracción Dyadic descrita anteriormente.
Tiene `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`de firma.

> [!WARNING]
> Los exponenciales del producto tensores de los operadores Pauli no son los mismos que los de tensores los de los operadores exponencial de Pauli.
> Es decir, $e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.

### <a name="measurements"></a>Medidas ###

Al medir, el eigenvalue + 1 del operador que se está midiendo corresponde a un resultado `Zero` y el-1 eigenvalue a un resultado `One`.

> [!NOTE]
> Aunque esta Convención podría parecer extraña, tiene dos ventajas muy ventajosas.
> En primer lugar, observando el resultado $ \ket{0}$ se representa mediante el valor de `Result` `Zero`, mientras que la observación de $ \ket{1}$ corresponde a `One`.
> En segundo lugar, podemos escribir que el eigenvalue $ \lambda $ correspondiente a un resultado $r $ es $ \lambda = (-1) ^ r $.

Las operaciones de medición no admiten ni el `Adjoint` ni el functor de `Controlled`.

La operación <xref:microsoft.quantum.intrinsic.measure> realiza una medición conjunta de uno o más qubits en el producto especificado de los operadores Pauli.
Si la matriz Pauli y la matriz qubit tienen longitudes diferentes, se produce un error en la operación.
`Measure` tiene `((Pauli[], Qubit[]) => Result)`de firma.

Tenga en cuenta que una medida conjunta no es lo mismo que medir cada qubit individualmente.
Por ejemplo, considere el estado $ \ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.
Al medir $Z _0 $ y $Z _ 1 _ cada uno individualmente, obtenemos los resultados $r _0 = $1 y $r _ 1 = $1.
Al medir $Z _0 Z_1 $, se obtiene el resultado único $r _ {\textrm{Joint}} = $0, que representa que la pareja de $ \ket{11}$ es positiva.
Se colocan de forma diferente, $ (-1) ^ {r_0 + r_1} = (-1) ^ R_ {\textrm{Joint}}) $.
De forma crítica, dado que *solo* se aprende la paridad de esta medida, cualquier información de Quantum representada en la superposición entre los Estados 2 2-qubit de paridad positiva, $ \ket{00}$ y $ \ket{11}$, se conserva.
Esta propiedad será esencial más adelante, ya que se describe la corrección de errores.

Para mayor comodidad, el predicho también proporciona otras dos operaciones para medir qubits.
En primer lugar, dado que la realización de medidas de un solo qubit es bastante común, el pre define una abreviatura para este caso.
La operación <xref:microsoft.quantum.intrinsic.m> mide el operador Pauli $Z $ en un solo qubit y tiene `(Qubit => Result)`de firma.
`M(q)` equivale a `Measure([PauliZ], [q])`.

El <xref:microsoft.quantum.measurement.multim> mide el operador Pauli $Z $ *por separado* en cada una de las matrices de qubits, devolviendo la *matriz* de valores de `Result` obtenidos para cada qubit.
En algunos casos, esto se puede optimizar. Tiene la firma (`Qubit[] => Result[])`.
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

Además, el pretexto define un amplio conjunto de funciones matemáticas y de conversión de tipos en el nivel de .NET para su uso en el código de preguntas y respuestas.
Por ejemplo, el espacio de nombres <xref:microsoft.quantum.extensions.math> define operaciones útiles como <xref:microsoft.quantum.extensions.math.sin> y <xref:microsoft.quantum.extensions.math.log>.
La implementación proporcionada por el kit de desarrollo de Quantum usa la biblioteca de clases base de .NET clásica y, por lo tanto, puede implicar un viaje de ida y vuelta de comunicaciones adicional entre programas Quantum y sus controladores clásico.
Aunque esto no presenta un problema para un simulador local, puede tratarse de un problema de rendimiento al usar un simulador remoto o un hardware real como equipo de destino.
Dicho esto, una máquina de destino individual puede mitigar este impacto en el rendimiento invalidando estas operaciones con versiones más eficaces para ese sistema en particular.

### <a name="math"></a>3\.0 ###

El espacio de nombres <xref:microsoft.quantum.extensions.math> proporciona muchas funciones útiles de la [clase`System.Math`](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)de la biblioteca de clases base de .net.
Estas funciones se pueden usar de la misma manera que cualquier otra función de Q #:

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

Cuando un método estático de .NET se ha sobrecargado según el tipo de sus argumentos, la función Q # correspondiente se anota con un sufijo que indica el tipo de su entrada:

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>Operaciones bit a bit ###

Por último, el espacio de nombres <xref:microsoft.quantum.extensions.bitwise> proporciona varias funciones útiles para manipular enteros a través de operadores bit a bit.
Por ejemplo, <xref:microsoft.quantum.extensions.bitwise.parity> devuelve la paridad bit a bit de un entero como otro entero.
