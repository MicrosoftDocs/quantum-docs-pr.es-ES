---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: d8c2f52290ce89d0a8ff138ba25f6b2e5e0516d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728343"
---
# <a name="transformedoperation-function"></a>TransformedOperation función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Dada una función y una operación, devuelve una nueva operación cuya entrada se transforma mediante la función especificada.

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a>Entrada

### <a name="fn--u---t"></a>FN: ' U-> ' t

Función que transforma la entrada especificada en un formato esperado por la operación.


### <a name="op--t--unit"></a>OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de> 

Operación que se va a transformar.



## <a name="output--u--unit"></a>Salida: ' U = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Una nueva operación tbat llama a `fn` con su entrada y, a continuación, pasa el resultado a `op` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada


### <a name="u"></a>' U



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Microsoft. Quantum. Canon. TransformedOperationC](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [Microsoft. Quantum. Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. Quantum. Canon. compuestas](xref:Microsoft.Quantum.Canon.Composed)