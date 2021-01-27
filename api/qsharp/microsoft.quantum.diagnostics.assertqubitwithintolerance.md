---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: Operación AssertQubitWithinTolerance
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 7f57fc7a29d3eb86dc94cb24230d52b37eb6971d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853429"
---
# <a name="assertqubitwithintolerance-operation"></a>Operación AssertQubitWithinTolerance

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Valida que qubit `q` está en el eigenstate esperado del operador Pauli Z hasta una tolerancia determinada.

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>Entrada

### <a name="expected--__invalidresult__"></a>esperado: __no <Result> válido__

El estado en el que se espera que esté el qubit: `Zero` o `One` .


### <a name="q--qubit"></a>p: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit cuyo estado se declara.


### <a name="tolerance--double"></a>tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerancia en la probabilidad de que una medida de qubit devuelva el resultado esperado.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> permite la aserción de Estados de qubit arbitrarios en lugar de solo $Z $ eigenstates.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)