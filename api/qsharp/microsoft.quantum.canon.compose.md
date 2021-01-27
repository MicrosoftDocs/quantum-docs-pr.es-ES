---
uid: Microsoft.Quantum.Canon.Compose
title: Función Compose
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840905"
---
# <a name="compose-function"></a>Función Compose

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve la composición de dos funciones.

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a>Descripción

Dadas dos funciones $f $ y $g $, devuelve una nueva función que representa $f \circ g $.

## <a name="input"></a>Entrada

### <a name="outer--u---v"></a>Outer: ' U-> ' V

Segunda función que se va a aplicar.


### <a name="inner--t---u"></a>interno: ' U ' > ' U

La primera función que se va a aplicar.



## <a name="output--t---v"></a>Salida: ' t-> ' V

Una nueva función $h $ tal que para todas las entradas $x $, $f (g (x)) = h (x) $.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la primera función que se va a aplicar.
### <a name="u"></a>' U

El tipo de salida de la primera función que se va a aplicar y el tipo de entrada de la segunda función que se va a aplicar.
### <a name="v"></a>' V

Tipo de salida de la segunda función que se va a aplicar.