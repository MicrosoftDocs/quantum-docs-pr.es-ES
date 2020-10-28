---
uid: Microsoft.Quantum.Canon.Angle
title: Función Angle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: da3ecdaf1b2c88180bd2a660fac0b6e87b2cafa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729764"
---
# <a name="angle-function"></a>Función Angle

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


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

