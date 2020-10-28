---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Sequencei (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730036"
---
# <a name="sequencei-function"></a>Sequencei (función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


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