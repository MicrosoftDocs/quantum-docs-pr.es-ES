---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: Operación PrepareEntangledState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 5f6e3ea1e7638d3bc446f21ace2968cf8284353a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210478"
---
# <a name="prepareentangledstate-operation"></a>Operación PrepareEntangledState

Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


En pares de dos registros qubit.

Es decir, dados dos registros, prepara el estado de in\frac {1} {\sqrt {2} } \left (\ket {00} + \ket {11} \right) $ entre cada par de qubits en los respectivos registros, suponiendo que cada registro comienza en el estado $ \ket{0\cdots 0} $.

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="left--qubit"></a>izquierda: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Una matriz qubit en el estado $ \ket{0\cdots 0} $


### <a name="right--qubit"></a>Right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Una matriz qubit en el estado $ \ket{0\cdots 0} $



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

