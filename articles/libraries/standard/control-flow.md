---
title: Controles de flujo en el libararies de preguntas y respuestas
description: Obtenga información sobre las operaciones y las funciones de control de flujo en la biblioteca estándar de preguntas y respuestas de Microsoft.
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b41b3edd7a3e3ac13dbda106a869f4cba8183600
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907178"
---
# <a name="higher-order-control-flow"></a>Flujo de control de orden superior #

Uno de los roles principales de la biblioteca estándar es facilitar la rápida creación de ideas algorítmicas de alto nivel como [programas Quantum](https://en.wikipedia.org/wiki/Quantum_programming).
Por lo tanto, Q # Canon proporciona una variedad de diferentes construcciones de control de flujo, cada una de las cuales se implementa mediante la aplicación parcial de funciones y operaciones.
Saltar inmediatamente a un ejemplo, considere el caso en el que uno desea construir una "CNOT escalera" en un registro:

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

Podemos expresar este patrón mediante bucles de iteración y `for`:

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

Sin embargo, expresado en términos de <xref:microsoft.quantum.canon.applytoeachca> y funciones de manipulación de matrices como <xref:microsoft.quantum.arrays.zip>, esto es mucho más corto y más fácil de leer:

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

En el resto de esta sección, proporcionaremos una serie de ejemplos de cómo usar las distintas operaciones y funciones de control de flujo que proporciona Canon para compactar los programas Quantum.

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>Aplicar operaciones y funciones sobre matrices e intervalos ##

Una de las abstracciones principales que proporciona la Canon es la de la iteración.
Por ejemplo, considere una unidad con el formato $U \otimes U \otimes \cdots \otimes U $ para una unidad de qubit única $U $.
En Q #, podríamos usar <xref:microsoft.quantum.arrays.indexrange> para representarlo como un bucle `for` sobre un registro:

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

A continuación, podemos usar esta nueva operación como `HAll(register)` para aplicar $H \otimes H \otimes \cdots \otimes H $.

Sin embargo, esto resulta complicado, especialmente en un algoritmo mayor.
Además, este enfoque se especializa en la operación concreta que se desea aplicar a cada qubit.
Podemos usar el hecho de que las operaciones sean de primera clase para expresar este concepto algorítmico más explícitamente:

```qsharp
ApplyToEachCA(H, register);
```

Aquí, el sufijo `CA` indica que la llamada a `ApplyToEach` es adjointable y controlable.
Por lo tanto, si `U` admite `Adjoint` y `Controlled`, las líneas siguientes son equivalentes:

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

En concreto, esto significa que las llamadas a `ApplyToEachCA` pueden aparecer en las operaciones para las que se genera automáticamente una especialización de unjoin.
Del mismo modo, <xref:microsoft.quantum.canon.applytoeachindex> resulta útil para representar patrones de la forma `U(0, targets[0]); U(1, targets[1]); ...`y ofrece versiones para cada combinación de funciones de tipo que admite su entrada.

> [!TIP]
> `ApplyToEach` es con parámetros de tipo, de modo que se puede utilizar con operaciones que toman entradas distintas de `Qubit`.
> Por ejemplo, supongamos que `codeBlocks` es una matriz de valores <xref:microsoft.quantum.errorcorrection.logicalregister> que deben recuperarse.
> A continuación, `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` aplicará el código de corrección de errores `code` y la función de recuperación `recoveryFn` en cada bloque de forma independiente.
> Esto se mantiene incluso para las entradas clásicas: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` aplicará un giro de $ \pi/$2 sobre $X $ seguido de un giro de $pi/$3 sobre $Y $.

Q # Canon también proporciona compatibilidad con patrones de enumeración clásicas conocidos para la programación funcional.
Por ejemplo, <xref:microsoft.quantum.arrays.fold> implementa el patrón $f (f (f (s\_{\text{Initial}}, x\_0), x\_1), \dots) $ para reducir una función en una lista.
Este patrón se puede usar para implementar sumas, productos, mínimos, máximos y otras funciones de este tipo:

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

Del mismo modo, se pueden usar funciones como <xref:microsoft.quantum.arrays.mapped> y <xref:microsoft.quantum.arrays.mappedbyindex> para expresar conceptos de programación funcional en Q #.

## <a name="composing-operations-and-functions"></a>Componer operaciones y funciones ##

Las construcciones de flujo de control que ofrece Canon toman las operaciones y las funciones como sus entradas, de modo que resulta útil poder componer varias operaciones o funciones en un único que se pueda llamar.
Por ejemplo, el patrón $UVU ^ {\dagger} $ es muy común en la programación de Quantum, de modo que Canon proporciona la operación <xref:microsoft.quantum.canon.applywith> como una abstracción para este patrón.
Esta abstracción también permite una mayor eficacia en los circuitos, como `Controlled` actúa en la secuencia `U(qubit); V(qubit); Adjoint U(qubit);` no necesita actuar en cada `U`.
Para ver esto, deje que $c (U) $ sea la unidad que representa `Controlled U([control], target)` y deje que $c (V) $ se defina de la misma manera.
A continuación, para un estado arbitrario $ \ket{\psi} $, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU ^ {\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes U ^ \dagger) \ket{1} \otimes \ket{\psi}.
\end{align} por la definición de `Controlled`.
Por otro lado, \begin{align} c (U) c (V) c (U) ^ \dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU ^ \dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c (V)) (\boldone \otimes U ^ \dagger) \ket{0} \otimes \ket{\psi}.
\end{align} por linealidad, podemos concluir que podemos factorizar $U $ de esta manera para todos los Estados de entrada.
Es decir, $c (UVU ^ \dagger) = U c (V) U ^ \dagger $.
Puesto que el control de las operaciones puede ser costoso en general, el uso de variantes controladas como `WithC` y `WithCA` puede ayudar a reducir el número de activadores de control que se deben aplicar.

> [!NOTE]
> Otra consecuencia de la división de $U $ es que no es necesario saber incluso cómo aplicar el `Controlled` functor a `U`.
> por lo tanto, `ApplyWithCA` tiene una firma más débil de lo que cabría esperar:
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

Del mismo modo, <xref:microsoft.quantum.canon.bound> produce operaciones que aplican una secuencia de otras operaciones a su vez.
Por ejemplo, los siguientes elementos son equivalentes:

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

La combinación con patrones de iteración puede hacer esto especialmente útil:

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>Composición ordenada por hora ###

Todavía podemos seguir pensando en el control de flujo en términos de aplicación parcial y en funciones clásicas, y puede modelar incluso conceptos de Quantum bastante sofisticados en términos de control de flujo clásico.
Esta analogía se hace precisa al reconocer que los operadores unitarios corresponden exactamente a los efectos secundarios de las operaciones de llamada, de modo que cualquier descomposición de operadores unitarios en términos de otros operadores unitarios corresponde a construir un determinado secuencia de llamada para subrutinas clásicas que emiten instrucciones para actuar como operadores unitarios determinados.
En esta vista, `Bound` es precisamente la representación del producto de matriz, ya que `Bound([A, B])(target)` es equivalente a `A(target); B(target);`, que a su vez es la secuencia de llamada correspondiente a $BA $.

Un ejemplo más sofisticado es la [expansión Trotter – Suzuki](https://arxiv.org/abs/math-ph/0506007v1).
Como se describe en la sección representación dinámica del generador de [estructuras de datos](xref:microsoft.quantum.libraries.data-structures), la expansión Trotter – Suzuki proporciona una manera especialmente útil de expresar la exponencial de la matriz.
Por ejemplo, si se aplica la expansión en el orden más bajo, se produce que para los operadores $A $ y $B $, $A = A ^ \dagger $ y $B = B ^ \dagger $, \begin{align} \tag{★} \label{EQ: Trotter-Suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left (\exp (p/n) \exp (i B t/n) \right) ^ n.
\end{align} suele, esto indica que podemos desarrollar aproximadamente un estado en $A + B $ cambiando de forma alternativa en $A $ y $B $ solo.
Si se representa la evolución en $A $ por una operación `A : (Double, Qubit[]) => Unit` que se aplica $e ^ {i t A} $, la representación de la expansión Trotter – Suzuki en lo que respecta a la reorganización de las secuencias de llamada queda clara.
Concretamente, dada una operación `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` tal que `A = U(0, _, _)` y `B = U(1, _, _)`, podemos definir una nueva operación que represente la parte entera de `U` en el tiempo $t $ generando secuencias del formulario

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

Llegados a este punto, ahora podemos pensar en la expansión Trotter – Suzuki *sin hacer referencia a la mecánica de Quantum*.
La expansión es en realidad un patrón de iteración muy concreto motivado por $ \eqref{EQ: Trotter-Suzuki-0} $.
Este patrón de iteración se implementa mediante <xref:microsoft.quantum.canon.decomposeintotimestepsca>:

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

La firma de `DecomposeIntoTimeStepsCA` sigue un patrón común en Q #, donde las colecciones que pueden estar respaldadas por matrices o por algo que los elementos de cálculo sobre la marcha se representan mediante tuplas cuyos primeros elementos son `Int` valores que indican sus longitudes.

## <a name="putting-it-together-controlling-operations"></a>Reunir juntos: controlar las operaciones ##

Por último, la Canon se basa en el `Controlled` functor, ya que proporciona métodos adicionales para la condición de las operaciones Quantum.
Es habitual, especialmente en la aritmética de Quantum, realizar operaciones de condición en Estados de base de cálculo distintos de $ \ket{0\cdots 0} $.
Con las operaciones de control y las funciones que se introdujeron anteriormente, podemos obtener condiciones de cuanto más generales en una única instrucción.
Vamos a entrar en el modo en que <xref:microsoft.quantum.canon.controlledonbitstring> (parámetros de tipo de San), vamos a desglosar las partes una a una.
Lo primero que debemos hacer es definir una operación que realmente realiza el pesado trabajo de implementar el control en Estados de base de cálculo arbitrarios.
Sin embargo, no llamaremos a esta operación directamente, así que agregaremos `_` al principio del nombre para indicar que es una implementación de otra construcción en otro lugar.

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

Tenga en cuenta que tomamos una cadena de bits, representada como una matriz de `Bool`, que usamos para especificar el acondicionamiento que queremos aplicar a la operación `oracle` que se les proporciona.
Puesto que esta operación realmente realiza la aplicación directamente, también es necesario tomar los registros de control y de destino, que se representan aquí como `Qubit[]`.

A continuación, observamos que el control del estado de base de cálculo $ \ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n-1}} $ para una cadena de bits $ \vec{s} $ se puede realizar transformando $ \ket{\vec{s}} $ en $ \ket{0\cdots 0} $.
En concreto, $ \ket{\vec{s}} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{0\cdots 0} $.
Desde $X ^ {\dagger} = X $, esto implica que $ \ket{0\dots 0} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{\vec{s}} $.
Por lo tanto, podemos aplicar $P = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} $, aplicar `Controlled oracle`y transformar de nuevo a $ \vec{s} $.
Esta construcción es precisamente `ApplyWith`, por lo que escribimos el cuerpo de la nueva operación en consecuencia:

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

Aquí hemos usado <xref:microsoft.quantum.canon.applypaulifrombitstring> para aplicar $P $, aplicar parcialmente a través de su destino para su uso con `ApplyWith`.
Sin embargo, tenga en cuenta que es necesario transformar el registro de *control* en el formulario deseado, por lo que aplicamos parcialmente la operación interna `(Controlled oracle)` en el *destino*.
Esto deja `ApplyWith` que actúen entre corchetes el registro de control con $P $, exactamente como se desea.

En este punto, podríamos hacer esto, pero de algún modo es que la nueva operación no "se siente" como aplicar el `Controlled` functor.
Por lo tanto, terminamos de definir el nuevo concepto de flujo de control escribiendo una función que toma el control de Oracle y que devuelve una nueva operación.
De esta manera, la nueva función tiene un aspecto muy similar al de `Controlled`, lo que ilustra que podemos definir fácilmente nuevas construcciones eficaces de flujo de control con Q # y la Canon conjuntamente:

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
