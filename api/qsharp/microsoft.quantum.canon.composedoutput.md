---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728835"
---
# <a name="composedoutput-function"></a>ComposedOutput función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Devuelve el resultado de la composición de `inner` y `outer` para una entrada determinada.

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a>Entrada

### <a name="outer--u---v"></a>Outer: ' U-> ' V




### <a name="inner--t---u"></a>interno: ' U ' > ' U




### <a name="target--t"></a>destino: ' t





## <a name="output--v"></a>Salida: ' V



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada


### <a name="u"></a>' U


### <a name="v"></a>' V

