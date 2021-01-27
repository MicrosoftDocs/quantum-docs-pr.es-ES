---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: Operación AssertMeasurementProbability
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 2fd89121516ef6994dedb75b214589b4e360ff8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830817"
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



## <a name="example"></a>Ejemplo

```qsharp
using (register = Qubit()) {
    H(register);
    AssertProb([PauliZ], [register], One, 0.5,
        "Measuring in conjugate basis did not give 50/50 results.", 1e-5);
}
```

## <a name="remarks"></a>Observaciones

Tenga en cuenta que las versiones contiguas y controladas de esta operación no comprobarán la condición.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Diagnostics. AssertMeasurement](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)