---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: Operación ApplyIfOne
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: b7c07e01ebcaf2d475283bea0695aa68dd10776e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209407"
---
# <a name="applyifone-operation"></a>Operación ApplyIfOne

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación condicionada a un valor de resultado clásico a uno.

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a>Descripción

Dada una operación `op` y un valor de resultado `result` , se aplica `op` a `target` si `result` es `One` . Si es `Zero` , no sucede nada con `target` .

## <a name="input"></a>Entrada

### <a name="result--__invalidresult__"></a>resultado: __no <Result> válido__

Resultado de la medida que controla si se aplica o no la operación.


### <a name="op--t--unit"></a>OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de> 

Operación que se va a aplicar condicionalmente.


### <a name="target--t"></a>destino: ' t

Entrada a la que se aplica la operación.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a aplicar condicionalmente.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyIfOneC](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [Microsoft. Quantum. Canon. ApplyIfOneA](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [Microsoft. Quantum. Canon. ApplyIfOneCA](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)