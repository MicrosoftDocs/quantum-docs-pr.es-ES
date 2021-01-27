---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: TransformedOperationA función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: fac0fb6e03dc515892783fb4a5fa9cfc274550b8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840139"
---
# <a name="transformedoperationa-function"></a>TransformedOperationA función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una función y una operación, devuelve una nueva operación cuya entrada se transforma mediante la función especificada.

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a>Entrada

### <a name="fn--u---t"></a>FN: ' U-> ' t

Función que transforma la entrada especificada en un formato esperado por la operación.


### <a name="op--t--unit--is-adj"></a>OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ

Operación que se va a transformar.



## <a name="output--u--unit--is-adj"></a>Salida: ' U = [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ

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
- [Microsoft. Quantum. Canon. TransformedOperationC](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [Microsoft. Quantum. Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. Quantum. Canon. compuestas](xref:Microsoft.Quantum.Canon.Composed)