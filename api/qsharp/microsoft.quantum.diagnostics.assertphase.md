---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Operación AssertPhase
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: e042c03d2a72d9ce4816a8cdb56603e175b22807
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727322"
---
# <a name="assertphase-operation"></a>Operación AssertPhase

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Configura [](https://nuget.org/packages/)


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

