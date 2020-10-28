---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: c78406aa4557834ac2bb40cf1847696d075e5135
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728714"
---
# <a name="embedpauli-function"></a>EmbedPauli función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Dado un operador Pauli de un solo qubit y el índice de un qubit, devuelve un operador Pauli de varios qubit con el operador Single-qubit dado en dicho índice y `PauliI` en todos los demás índices.

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a>Entrada

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Un operador Pauli de un solo qubit que se va a colocar en la ubicación especificada.


### <a name="location--int"></a>Ubicación: [int](xref:microsoft.quantum.lang-ref.int)

Índice tal que `output[location] == pauli` , donde `output` es la salida de esta función.


### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

Longitud de la matriz que se va a devolver.



## <a name="output--pauli"></a>Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

