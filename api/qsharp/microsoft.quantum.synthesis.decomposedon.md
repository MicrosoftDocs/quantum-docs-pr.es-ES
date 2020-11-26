---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: Descomponer función
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: 79f952e7bc7ba9f5337cf5e7a625e0d270a2e17a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203236"
---
# <a name="decomposedon-function"></a>Descomponer función

Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Descompone una permutación en una variable

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>Descripción

Dada una permutación $ \pi $ ( `perm` ) y un índice $i $ ( `index` ), este método devuelve tres permutaciones $ ((\ pi_l, \ PI_R), \pi ') $ de modo que las imágenes de $ \ pi_l $ y $ \ PI_R $ no cambian bits en sus elementos en índices distintos de $i $ e imágenes de $ \pi ' $ no cambie el bit $i $ en sus elementos.

## <a name="input"></a>Entrada

### <a name="perm--int"></a>Perm: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>Índice: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Output: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])

