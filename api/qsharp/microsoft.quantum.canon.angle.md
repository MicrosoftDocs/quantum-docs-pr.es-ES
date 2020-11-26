---
uid: Microsoft.Quantum.Canon.Angle
title: Función Angle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 1d8a9c2c19469e4949f043edd1ba91021fa42e78
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219420"
---
# <a name="angle-function"></a>Función Angle

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve 1, si `index` tiene un número impar de 1s y-1, si `index` tiene un número par de 1s.

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a>Descripción

El valor corresponde al signo del coeficiente del Rademacher-Walsh espectro de la variable n y la función para una asignación determinada que decide el ángulo de rotación.

## <a name="input"></a>Entrada

### <a name="index--int"></a>Índice: [int](xref:microsoft.quantum.lang-ref.int)

Asignación de entrada como entero (de 0 a 2 ^ n-1)



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

