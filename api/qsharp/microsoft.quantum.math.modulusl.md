---
uid: Microsoft.Quantum.Math.ModulusL
title: Función modulus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 5c9a8ceceac5d2cdac6b82f7f74a85e9443382a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194940"
---
# <a name="modulusl-function"></a>Función modulus

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcula el residuo canónico del `value` módulo `modulus` .

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Entrada

### <a name="value--bigint"></a>valor: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Valor del que se calcula el residuo


### <a name="modulus--bigint"></a>módulo: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

El módulo por el que se toman los residuos, debe ser positivo



## <a name="output--bigint"></a>Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Entero $r $ entre 0 y `modulus - 1` este que `value - r` es divisible por módulo.

## <a name="remarks"></a>Observaciones

Esta función se comporta de forma diferente a cómo `%` se comporta el operador en C# y Q # como en el resultado siempre es un entero positivo entre 0 y `modulus - 1` , incluso si el valor es negativo.