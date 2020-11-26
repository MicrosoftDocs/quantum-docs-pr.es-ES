---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: Operación ReflectAboutInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: d4bae0cba5ee45e8d48070e36efab0159ade9137
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222378"
---
# <a name="reflectaboutinteger-operation"></a>Operación ReflectAboutInteger

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Refleja un registro de Quantum sobre un entero clásico determinado.

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

Dado un registro de Quantum inicialmente en el estado $ \ sum_i \ alpha_i \ket{i} $, donde cada $ \ket{i} $ es un estado de base que representa un entero $i $, refleja el estado del registro sobre el estado de base de un entero determinado $ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {ij}} \ alpha_i \ket{i} $ $

## <a name="input"></a>Entrada

### <a name="index--int"></a>Índice: [int](xref:microsoft.quantum.lang-ref.int)

Entero clásico que indiza el estado base sobre el que se va a reflejar.


### <a name="reg--littleendian"></a>reg: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Esta operación se implementa en contexto, sin la asignación explícita de qubits auxiliares adicionales.