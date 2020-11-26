---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: Operación EstimateImagOverlapBetweenStates
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: b192abc4ba37d126bf46f94c66cb87fe3bbec4c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216207"
---
# <a name="estimateimagoverlapbetweenstates-operation"></a>Operación EstimateImagOverlapBetweenStates

Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dadas dos operaciones que preparan copias de un estado, calcula la parte imaginaria de la superposición entre los Estados preparados por cada operación.

```qsharp
operation EstimateImagOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Entrada

### <a name="commonpreparation--qubit--unit--is-adj"></a>commonPreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ

Operación que prepara un estado de entrada fijo.


### <a name="preparation1--qubit--unit--is-adj--ctl"></a>preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL

Primera de las dos operaciones de preparación de estado que se van a comparar.


### <a name="preparation2--qubit--unit--is-adj--ctl"></a>preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL

Segundo de las dos operaciones de preparación de estado que se van a comparar.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

El número de qubits en el `commonPreparation` que `preparation1` `preparation2` todos los actos, y.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Número de medidas que se van a usar para calcular la superposición.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Observaciones

Esta operación usa la prueba Hadamard para encontrar la parte imaginaria de $ $ \begin{align} \braket{\psi | V ^ {\dagger} U | \psi} \end{align} $ $, donde $ \ket{\psi} $ es el estado preparado por `commonPreparation` , $U $ es la representación unitario de la acción de `preparation1` y donde $V $ corresponde a `preparation2` .

## <a name="references"></a>Referencias

- Aharonov *et al.* [Quant-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Caracterización. EstimateRealOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [Microsoft. Quantum. Caracterización. EstimateOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)