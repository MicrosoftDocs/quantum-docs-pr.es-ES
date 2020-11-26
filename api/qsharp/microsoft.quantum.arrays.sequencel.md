---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Función sequencel
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220270"
---
# <a name="sequencel-function"></a>Función sequencel

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Obtiene una matriz de enteros en un intervalo determinado.

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a>Entrada

### <a name="from--bigint"></a>From: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Índice inicial inclusivo del intervalo.


### <a name="to--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Índice final inclusivo del intervalo que no es menor que `from` .



## <a name="output--bigint"></a>Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]

Una matriz que contiene la secuencia de números `from` , `from + 1` ,... `to` .

## <a name="remarks"></a>Observaciones

La diferencia entre `from` y `to` debe ajustarse a un `Int` valor.