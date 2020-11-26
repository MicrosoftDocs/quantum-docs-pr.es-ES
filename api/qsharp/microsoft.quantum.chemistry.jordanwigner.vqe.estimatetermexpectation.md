---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Operación EstimateTermExpectation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 3f0ff5037b1424abb6fb318bd49ffd89f545822d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224656"
---
# <a name="estimatetermexpectation-operation"></a>Operación EstimateTermExpectation

Espacio de nombres: [Microsoft. Quantum. química. JordanWigner. vqe](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Calcula la energía asociada a un determinado término de Jordan-Wigner Hamiltonian

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>Descripción

Esta operación calcula el valor de expectativa asociado a cada operador de medida y lo multiplica por el coeficiente correspondiente, mediante el muestreo.
Los resultados se agregan a una variable que contiene la energía del término Jordan-Wigner.

## <a name="input"></a>Entrada

### <a name="inputstateunitary--qubit--unit--is-adj"></a>inputStateUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ

La unitario usada para la preparación del estado.


### <a name="ops--pauli"></a>OPS: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Los operadores de medida del término Jordan-Wigner.


### <a name="coeffs--double"></a>coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]

Coeficientes del término Jordan-Wigner.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

El número de qubits necesario para simular el sistema molecular.


### <a name="nsamples--int"></a>nSamples: [int](xref:microsoft.quantum.lang-ref.int)

Número de muestras que se van a usar para la estimación de la expectativa de términos.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)

La energía asociada al término Jordan-Wigner.