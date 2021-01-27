---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: Operación EstimateOverlapBetweenStates
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: e083d6da13b0780905bf365c7a428ebc9666ce9e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839714"
---
# <a name="estimateoverlapbetweenstates-operation"></a>Operación EstimateOverlapBetweenStates

Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dadas dos operaciones que preparan copias de un estado, calcula la superposición cuadrada entre los Estados preparados por cada operación.

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Entrada

### <a name="preparation1--qubit--unit--is-adj"></a>preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ

Primera de las dos operaciones de preparación de estado que se van a comparar.


### <a name="preparation2--qubit--unit--is-adj"></a>preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ

Segundo de las dos operaciones de preparación de estado que se van a comparar.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

El número de qubits en el `commonPreparation` que `preparation1` `preparation2` todos los actos, y.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Número de medidas que se van a usar para calcular la superposición.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Observaciones

Esta operación usa la prueba de intercambio para encontrar $ $ \begin{align} \left | \braket{00\cdots 0 | V ^ {\dagger} U | 00 \ cdots 0} \right | ^ 2 \end{align} $ $, donde $U $ es la representación unitario de la acción de `preparation1` y donde $V $ corresponde a `preparation2` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Caracterización. EstimateRealOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [Microsoft. Quantum. Caracterización. EstimateImagOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)