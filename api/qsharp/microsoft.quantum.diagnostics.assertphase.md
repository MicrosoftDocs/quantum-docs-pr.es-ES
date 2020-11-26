---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Operación AssertPhase
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 9130d6c735d90abbc51989ef4a68a8eff8b41371
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202267"
---
# <a name="assertphase-operation"></a>Operación AssertPhase

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Declara que la fase de un estado de superposición igual tiene el valor esperado.

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a>Descripción

Esta operación garantiza que la fase $ \phi $ de un estado de Quantum que se puede expresar como $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ les {0} + e ^ {-i\phi} \ les {1} ) $ para algunos $t reales arbitrarios $ tiene el valor esperado.

## <a name="input"></a>Entrada

### <a name="expected--double"></a>se esperaba: [Double](xref:microsoft.quantum.lang-ref.double)

El valor esperado de $ \phi \en (-\pi, \pi] $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit que almacena el estado esperado.


### <a name="tolerance--double"></a>tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerancia absoluta en la diferencia entre real y expected.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

