---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Función sequencel
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730021"
---
# <a name="sequencel-function"></a>Función sequencel

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


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