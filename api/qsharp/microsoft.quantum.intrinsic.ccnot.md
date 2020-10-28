---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: Operación CCNOT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: bf20ff1e9d25d72e7e8e0207ab947a57dc394cf4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726716"
---
# <a name="ccnot-operation"></a>Operación CCNOT

Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Configura [](https://nuget.org/packages/)


Aplica la puerta de control doble, no (CCNOT) a tres qubits.

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="control1--qubit"></a>Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Primer control qubit para la puerta CCNOT.


### <a name="control2--qubit"></a>control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Segundo control qubit para la puerta CCNOT.


### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit de destino para la puerta CCNOT.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Equivalente a:

```qsharp
Controlled X([control1, control2], target);
```