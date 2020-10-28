---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: Operación AssertQubit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: fa1f52da5a011cd914a0fda69b78cf5a4fd71e16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727317"
---
# <a name="assertqubit-operation"></a>Operación AssertQubit

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Configura [](https://nuget.org/packages/)


Valida que qubit `q` está en el eigenstate esperado del operador Pauli Z.

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="expected--__invalidresult__"></a>esperado: __no <Result> válido__

El estado en el que se espera que esté el qubit: `Zero` o `One` .


### <a name="q--qubit"></a>p: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit cuyo estado se declara.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> permite la aserción de Estados de qubit arbitrarios en lugar de solo $Z $ eigenstates.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)