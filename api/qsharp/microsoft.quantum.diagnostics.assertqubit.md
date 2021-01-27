---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: Operación AssertQubit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 8fcdd8de9250348e1dd1173052b53be978f2a0c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853451"
---
# <a name="assertqubit-operation"></a>Operación AssertQubit

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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