---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: Operación AssertMeasurementProbability
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 032b9224ad728f0637596668c2928a889deeba55
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202369"
---
# <a name="assertmeasurementprobability-operation"></a>Operación AssertMeasurementProbability

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Las aserciones que midan el qubits determinado en la base de Pauli determinada tendrán el resultado dado con la probabilidad especificada, dentro de cierta tolerancia.

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="bases--pauli"></a>bases: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Un efecto de medición para imponer la probabilidad de, expresado como un operador Pauli de varios qubit.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro en el que se va a realizar la aserción.


### <a name="result--__invalidresult__"></a>resultado: __no <Result> válido__

Resultado esperado de `Measure(bases, qubits)` .


### <a name="prob--double"></a>probabilidad: [doble](xref:microsoft.quantum.lang-ref.double)

La probabilidad con la que se espera el resultado especificado.


### <a name="msg--string"></a>msg: [cadena](xref:microsoft.quantum.lang-ref.string)

Mensaje que se va a mostrar si se produce un error en la aserción.


### <a name="tol--double"></a>Tol: [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Tenga en cuenta que las versiones contiguas y controladas de esta operación no comprobarán la condición.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Diagnostics. AssertMeasurement](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)