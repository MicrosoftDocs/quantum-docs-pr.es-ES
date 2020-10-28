---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725822"
---
# <a name="intstopaulis-function"></a>IntsToPaulis función)

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Configura [](https://nuget.org/packages/)


Convierte una matriz de enteros en una matriz de operadores Pauli de un solo qubit.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Entrada

### <a name="ints--int"></a>ints: [int](xref:microsoft.quantum.lang-ref.int)[]

Matriz de enteros en el intervalo `0..3`  que se va a convertir en operadores de Pauli.



## <a name="output--pauli"></a>Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Una matriz `paulis` de operadores Pauli `Pauli[]` la misma longitud `ints` que `paulis[idxPauli]` es igual al elemento de `[PauliI, PauliX, PauliY, PauliZ]` proporcionado por `ints[idxPauli]` .