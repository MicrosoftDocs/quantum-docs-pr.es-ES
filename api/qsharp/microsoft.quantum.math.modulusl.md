---
uid: Microsoft.Quantum.Math.ModulusL
title: Función modulus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6be2edb052cf55f8e8465c76b5dcadeb61ff11ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842740"
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

Esta función se comporta de forma diferente a cómo `%` se comporta el operador en C# y Q # como en el resultado es siempre un entero no negativo entre 0 y `modulus - 1` , incluso si el valor es negativo.