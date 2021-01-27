---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Función sequencel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 7e3c5c31428f9be152e28afbe478a3d15eb0a56c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850987"
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

## <a name="example"></a>Ejemplo

```qsharp
let arr1 = SequenceL(0L, 3L); // [0L, 1L, 2L, 3L]
let arr2 = SequenceL(23L, 29L); // [23L, 24L, 25L, 26L, 27L, 28L, 29L]
let arr3 = SequenceL(-5L, -2L); // [-5L, -4L, -3L, -2L]
```

## <a name="remarks"></a>Observaciones

La diferencia entre `from` y `to` debe ajustarse a un `Int` valor.