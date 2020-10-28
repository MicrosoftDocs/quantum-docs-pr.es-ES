---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Operación EstimateTermExpectation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727653"
---
# <a name="estimatetermexpectation-operation"></a>Operación EstimateTermExpectation

Espacio de nombres: [Microsoft. Quantum. química. JordanWigner. vqe](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Configura [](https://nuget.org/packages/)


Calcula la energía asociada a un determinado término de Jordan-Wigner Hamiltonian

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>Descripción

Esta operación calcula el valor de expectativa asociado a cada operador de medida y lo multiplica por el coeficiente correspondiente, mediante el muestreo.
Los resultados se agregan a una variable que contiene la energía del término Jordan-Wigner.

## <a name="input"></a>Entrada

### <a name="inputstateunitary--qubit--unit-adj"></a>inputStateUnitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit)

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