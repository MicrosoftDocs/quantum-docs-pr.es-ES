---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Sequencei (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220304"
---
# <a name="sequencei-function"></a>Sequencei (función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Obtiene una matriz de enteros en un intervalo determinado.

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a>Entrada

### <a name="from--int"></a>de: [int](xref:microsoft.quantum.lang-ref.int)

Índice inicial inclusivo del intervalo.


### <a name="to--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Índice final inclusivo del intervalo que no es menor que `from` .



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)[]

Una matriz que contiene la secuencia de números `from` , `from + 1` ,... `to` .