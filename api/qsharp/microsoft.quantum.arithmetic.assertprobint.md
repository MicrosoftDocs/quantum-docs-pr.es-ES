---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Operación AssertProbInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843405"
---
# <a name="assertprobint-operation"></a>Operación AssertProbInt

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Valida que la probabilidad de un estado específico de un registro de Quantum tiene el valor esperado.

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a>Descripción

Dado un $n $-qubit Quantum State $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, garantiza que la probabilidad $ | \ alpha_j | ^ 2 $ del estado $ \ket{j} $ indexada por $j $ tiene el valor esperado.

## <a name="input"></a>Entrada

### <a name="stateindex--int"></a>stateIndex: [int](xref:microsoft.quantum.lang-ref.int)

Índice $j $ del estado $ \ket{j} $ representado por un `LittleEndian` registro.


### <a name="expected--double"></a>se esperaba: [Double](xref:microsoft.quantum.lang-ref.double)

El valor esperado de $ | \ alpha_j | ^ 2 $.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

El registro qubit que almacena $ \ket{\psi} $ en formato Little-Endian.


### <a name="tolerance--double"></a>tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerancia absoluta en la diferencia entre real y expected.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Ejemplo

Supongamos que el `qubits` registro codifica un estado de Quantum 3-qubit $ \ket{\psi} = \ sqrt {1/8} \ les {0} + \ sqrt {7/8} \ les {6} $ en formato Little-Endian.
Esto significa que el número indica $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ y $ \ket {6} \equiv\ket {0} \ket {1} {1} $. A continuación, se realizan correctamente las siguientes aserciones:

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```