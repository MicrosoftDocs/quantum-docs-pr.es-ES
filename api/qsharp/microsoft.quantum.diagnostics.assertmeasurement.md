---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Operación AssertMeasurement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727358"
---
# <a name="assertmeasurement-operation"></a>Operación AssertMeasurement

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Configura [](https://nuget.org/packages/)


Las aserciones que midan el qubits determinado en la base de Pauli determinada siempre tendrán el resultado especificado.

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="bases--pauli"></a>bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Un efecto de medición para imponer la probabilidad de, expresado como un operador Pauli de varios qubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro en el que se va a realizar la aserción.


### <a name="result--__invalidresult__"></a>resultado: __no <Result> válido__

Resultado esperado de `Measure(bases, qubits)` .


### <a name="msg--string"></a>msg: [cadena](xref:microsoft.quantum.lang-ref.string)

Mensaje que se va a mostrar si se produce un error en la aserción.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Tenga en cuenta que las versiones contiguas y controladas de esta operación no comprobarán la condición.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Diagnostics. AssertMeasurementProbability](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)