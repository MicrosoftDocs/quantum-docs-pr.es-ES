---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: Operación AssertQubitIsInStateWithinTolerance
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: b40c5c4f731190c8c0d00d33718680e5448bf767
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829784"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a>Operación AssertQubitIsInStateWithinTolerance

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Valida que qubit en el estado esperado.

`expected` representa un vector complejo, $ \ket{\psi} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $.
El primer elemento de las tuplas que representa cada una de $a $, $b $ es la parte real del número complejo, mientras que la segunda es la parte imaginaria.
El último argumento define la tolerancia con la que se realiza la aserción.

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>Entrada

### <a name="expected--complexcomplex"></a>esperado: ([complejo](xref:Microsoft.Quantum.Math.Complex),[complejo](xref:Microsoft.Quantum.Math.Complex))

Se esperaban las amplitudes complejas de $ \ket {0} $ y $ \ket {1} $, respectivamente.


### <a name="register--qubit"></a>registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit cuyo estado se va a declarar. Tenga en cuenta que se supone que este qubit se puede separar de otros qubits asignados y no está insuficiente.


### <a name="tolerance--double"></a>tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerancia aditiva mediante la cual se permite que las amplitudes reales se desvíen de lo esperado.
Vea la sección Comentarios a continuación para obtener más información.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Ejemplo

```qsharp
using (qubits = Qubit[2]) {
    // Both qubits are initialized as |0〉: a=(1 + 0*i), b=(0 + 0*i)
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[0], 1e-5);
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[1], 1e-5);
    Y(qubits[1]);
    // Y |0〉 = i |1〉: a=(0 + 0*i), b=(0 + 1*i)
    AssertQubitIsInStateWithinTolerance((Complex(0., 0.), Complex(0., 1.)), qubits[1], 1e-5);
}
```

## <a name="remarks"></a>Observaciones

El siguiente código de Mathematica se puede usar para comprobar las expresiones de mi, mx, My, MZ:

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

La tolerancia es la $L \_ {\infty} $ distance entre 3 vectores reales (x ₂, x ₃, x ₄) definido por $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 y + x \_ 4 Z $ y Vector real (y ₂, y ₃, y ₄) definidos por p = y ₁ I + y ₂ x + y ₃ y + y ₄ Z, donde p es la matriz de densidad que corresponde al estado del registro.
Esto solo se aplica en la suposición de que TR (p) y TR (| ψ ⟩ ⟨ ψ |) son 1 (por ejemplo, x ₁ = 1/2, y ₁ = 1/2).
Si no es así, la función garantiza que la distancia l ∞ entre (x ₂-x ₁, x ₃-x ₁, x ₄-x ₁, x ₄ + x ₁) y (y ₂-y ₁, y ₃-y ₁, y ₄-y ₁, y ₄ + y ₁) es menor que el parámetro Tolerance.