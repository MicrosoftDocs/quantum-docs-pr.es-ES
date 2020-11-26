---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 6077110cc07c8626b22eb404c1de096ed43efcc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224248"
---
# <a name="pauliarrayasint-function"></a>PauliArrayAsInt función)

Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Codifica un operador qubit de Pauli que se representa como una matriz de operadores de un solo qubit Pauli en un entero.

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a>Entrada

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Una matriz de, como máximo, 31 operadores de Pauli de un solo qubit.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Un entero `paulis` que identifica de forma única, tal y como se describe a continuación.

## <a name="remarks"></a>Observaciones

Cada operador Pauli se puede codificar con dos bits: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.
\end{align} $ $

Dada una matriz de operadores Pauli `[P0, ..., Pn]` , esta función devuelve un entero con expansión binaria formada mediante la concatenación de las asignaciones de cada operador Pauli en orden Big Endian `bits(Pn) ... bits(P0)` .