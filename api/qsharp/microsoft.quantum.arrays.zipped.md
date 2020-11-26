---
uid: Microsoft.Quantum.Arrays.Zipped
title: Función Zip
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 56ed97d573bf29dddb7cdb1c3f360218bf97889a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219760"
---
# <a name="zipped-function"></a>Función Zip

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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