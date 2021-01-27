---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846224"
---
# <a name="constantarray-function"></a>ConstantArray función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crea una matriz de longitud determinada con todos los elementos iguales al valor especificado.

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="length--int"></a>longitud: [int](xref:microsoft.quantum.lang-ref.int)

Longitud de la nueva matriz.


### <a name="value--t"></a>valor: ' t

Valor de cada elemento de la nueva matriz.



## <a name="output--t"></a>Salida: ' t []

Nueva matriz de longitud `length` , de modo que todos los elementos son `value` .

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="example"></a>Ejemplo

En el código siguiente se crea una matriz de 3 valores booleanos, cada uno de ellos igual a `true` :

```qsharp
let array = ConstantArray(3, true);
```