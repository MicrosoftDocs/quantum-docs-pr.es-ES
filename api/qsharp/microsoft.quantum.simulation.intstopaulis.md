---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 2333dcbd2988480e2b2b9b217b26705f3578de00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230538"
---
# <a name="intstopaulis-function"></a>IntsToPaulis función)

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Convierte una matriz de enteros en una matriz de operadores Pauli de un solo qubit.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Entrada

### <a name="ints--int"></a>ints: [int](xref:microsoft.quantum.lang-ref.int)[]

Matriz de enteros en el intervalo `0..3`  que se va a convertir en operadores de Pauli.



## <a name="output--pauli"></a>Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Una matriz `paulis` de operadores Pauli `Pauli[]` la misma longitud `ints` que `paulis[idxPauli]` es igual al elemento de `[PauliI, PauliX, PauliY, PauliZ]` proporcionado por `ints[idxPauli]` .