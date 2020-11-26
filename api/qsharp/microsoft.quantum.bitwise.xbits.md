---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 969be01204bad497496ff24cb64213f5fe1f089b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209764"
---
# <a name="xbits-function"></a>XBits función)

Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devuelve un entero que representa los bits X de una matriz de operadores Pauli.

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>Entrada

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matriz de operadores Pauli que se va a representar como un entero.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Entero $x $ con la representación binaria $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, donde $p _I = $0 si `paulis[i]` es `PauliI` o `PauliZ` y donde $p _I = $1 si `paulis[i]` es `PauliX` o `PauliY` .

## <a name="remarks"></a>Observaciones

La función producirá una excepción si la longitud de la `paulis` matriz es mayor que 63.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. bit a bit. ZBits](xref:Microsoft.Quantum.Bitwise.ZBits)