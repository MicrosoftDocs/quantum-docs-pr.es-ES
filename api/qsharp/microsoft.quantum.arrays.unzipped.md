---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Descomprimir función
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219964"
---
# <a name="unzipped-function"></a>Descomprimir función

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una matriz de 2-tuplas, devuelve una tupla de dos matrices, cada una con los elementos de las tuplas de la matriz de entrada.

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a>Entrada

### <a name="arr--tu"></a>ARR: (' t, ' U) []

Una matriz que contiene dos tuplas



## <a name="output--tu"></a>Salida: (' t [], ' U [])

Dos matrices, la primera que contiene todos los primeros elementos de las tuplas de entrada, la segunda que contiene todos los segundos elementos de las tuplas de entrada.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo del primer elemento de cada tupla.
### <a name="u"></a>' U

Tipo del segundo elemento de cada tupla.

## <a name="see-also"></a>Consulte también

- [Microsoft.Quantum.Arrays.ZipPED](xref:Microsoft.Quantum.Arrays.Zipped)