---
uid: Microsoft.Quantum.Arrays.Zipped
title: Función Zip
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729909"
---
# <a name="zipped-function"></a>Función Zip

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


Dadas dos matrices, devuelve una nueva matriz de pares de modo que cada par contiene un elemento de cada matriz original.

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a>Entrada

### <a name="left--t"></a>Left: ' t []

Una matriz que contiene valores para el primer elemento de cada tupla.


### <a name="right--u"></a>Right: ' U []

Una matriz que contiene valores para el segundo elemento de cada tupla.



## <a name="output--tu"></a>Salida: (' t, ' U) []

Una matriz que contiene pares del formulario `(left[idx], right[idx])` para cada `idx` . Si las dos matrices no tienen la misma longitud, la salida será tan larga como las entradas más cortas.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de los elementos de la matriz izquierda.
### <a name="u"></a>' U

Tipo de los elementos de la matriz de la derecha.

## <a name="see-also"></a>Consulte también

- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)
- [Microsoft. Quantum. matrices. descomprimido](xref:Microsoft.Quantum.Arrays.Unzipped)