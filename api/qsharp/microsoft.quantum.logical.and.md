---
uid: Microsoft.Quantum.Logical.And
title: And (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 279221ed785dd76e28146e4c22e70290936bf529
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198578"
---
# <a name="and-function"></a>And (función)

Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve la conjunción booleana de dos valores.

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--bool"></a>r: [bool](xref:microsoft.quantum.lang-ref.bool)

Primer valor que se va a considerar.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Segundo valor que se va a considerar.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` es si y solo si `a` y `b` son ambos `true` .

## <a name="remarks"></a>Observaciones

A diferencia del `and` operador, esta función no cortocircuita, de modo que ambas entradas se evalúen por completo.

Hasta un comportamiento de cortocircuito, los siguientes son equivalentes:

```Q#
let x = a and b;
let x = And(a, b);
```