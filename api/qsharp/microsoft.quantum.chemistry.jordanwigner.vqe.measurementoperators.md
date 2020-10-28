---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727634"
---
# <a name="measurementoperators-function"></a>MeasurementOperators función)

Espacio de nombres: [Microsoft. Quantum. química. JordanWigner. vqe](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Configura [](https://nuget.org/packages/)


Calcula todos los operadores de medida necesarios para calcular la expectativa de un término Jordan-Wigner.

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

El número de qubits necesario para simular el sistema molecular.


### <a name="indices--int"></a>índices: [int](xref:microsoft.quantum.lang-ref.int)[]

Una matriz que contiene los índices de qubit a los que se aplica cada operador Pauli.


### <a name="termtype--int"></a>Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)

Tipo del término Jordan-Wigner.



## <a name="output--pauli"></a>Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Matriz de operadores de medida (cada uno de ellos es una matriz de Pauli).