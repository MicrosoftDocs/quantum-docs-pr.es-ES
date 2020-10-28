---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: Operación EstimateRealOverlapBetweenStates
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 01631bcbff2bff26ddc1db4e42d90ac4f8380bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728187"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a>Operación EstimateRealOverlapBetweenStates

Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)

Configura [](https://nuget.org/packages/)


Dadas dos operaciones que preparan copias de un estado, calcula la parte real de la superposición entre los Estados preparados por cada operación.

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Entrada

### <a name="commonpreparation--qubit--unit-adj"></a>commonPreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit)

Operación que prepara un estado de entrada fijo.


### <a name="preparation1--qubit--unit-adj--ctl"></a>preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL

Primera de las dos operaciones de preparación de estado que se van a comparar.


### <a name="preparation2--qubit--unit-adj--ctl"></a>preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL

Segundo de las dos operaciones de preparación de estado que se van a comparar.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

El número de qubits en el `commonPreparation` que `preparation1` `preparation2` todos los actos, y.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Número de medidas que se van a usar para calcular la superposición.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Observaciones

Esta operación usa la prueba Hadamard para encontrar la parte real de $ $ \begin{align} \braket{\psi | V ^ {\dagger} U | \psi} \end{align} $ $, donde $ \ket{\psi} $ es el estado preparado por `commonPreparation` , $U $ es la representación unitario de la acción de `preparation1` y donde $V $ corresponde a `preparation2` .

## <a name="references"></a>Referencias

- Aharonov *et al.* [Quant-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Caracterización. EstimateImagOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [Microsoft. Quantum. Caracterización. EstimateOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)