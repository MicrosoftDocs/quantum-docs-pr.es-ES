---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: TransformedOperationCA función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: bb39530ae28e17d07a6a5c2bb2d35f81be312d15
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840119"
---
# <a name="transformedoperationca-function"></a>TransformedOperationCA función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una función y una operación, devuelve una nueva operación cuya entrada se transforma mediante la función especificada.

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="fn--u---t"></a>FN: ' U-> ' t

Función que transforma la entrada especificada en un formato esperado por la operación.


### <a name="op--t--unit--is-adj--ctl"></a>OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL

Operación que se va a transformar.



## <a name="output--u--unit--is-adj--ctl"></a>Salida: ' U = [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL

Una nueva operación tbat llama a `fn` con su entrada y, a continuación, pasa el resultado a `op` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada


### <a name="u"></a>' U



## <a name="example"></a>Ejemplo

La siguiente llamada utiliza @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" para transformar una operación diseñada para @"Microsoft.Quantum.Arithmetic.BigEndian" entradas en una operación que acepta entradas de tipo @"Microsoft.Quantum.Arithmetic.LittleEndian" :

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Microsoft. Quantum. Canon. TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Microsoft. Quantum. Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. Quantum. Canon. compuestas](xref:Microsoft.Quantum.Canon.Composed)