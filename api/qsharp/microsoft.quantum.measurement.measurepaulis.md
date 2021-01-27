---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: Operación MeasurePaulis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 1bc14ec8e7c608d1195a03a354c71e870594f86d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853765"
---
# <a name="measurepaulis-operation"></a>Operación MeasurePaulis

Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una matriz de operadores Pauli de varios qubit, mide cada uno de ellos con un gadget de medida especificado y, a continuación, devuelve la matriz de resultados.

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a>Entrada

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Matriz de operadores de Pauli de varios qubits que se van a medir.


### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro en el que se van a medir los operadores especificados.


### <a name="gadget--pauliqubit--__invalidresult__"></a>gadget: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __no <Result> válido__ 

Operación que realiza la medición de un operador multiqubit determinado.



## <a name="output--__invalidresult__"></a>Salida: __no <Result> válido__[]

Matriz de resultados obtenida de la medición de cada elemento de `paulis` en `target` .