---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Descomprimir función
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845380"
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

## <a name="example"></a>Ejemplo

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a>Consulte también

- [Microsoft.Quantum.Arrays.ZipPED](xref:Microsoft.Quantum.Arrays.Zipped)