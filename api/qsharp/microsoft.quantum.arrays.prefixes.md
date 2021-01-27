---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Prefixes (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845507"
---
# <a name="prefixes-function"></a>Prefixes (función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una matriz, devuelve todos sus prefijos.

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a>Descripción

Devuelve una matriz de todos los prefijos, empezando por una matriz que solo tiene el primer elemento hasta la matriz completa.

## <a name="input"></a>Entrada

### <a name="array--t"></a>matriz: ' t []

Matriz de elementos.



## <a name="output--t"></a>Salida: ' t [] []



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de `array` elementos.

## <a name="example"></a>Ejemplo

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```