---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: Operación ApplyToMost
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a3918233e101f3d8956601dcc7d85edcf6196ac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850586"
---
# <a name="applytomost-operation"></a>Operación ApplyToMost

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una operación a todo menos al último elemento de una matriz.

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Descripción

Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Most(targets))` .

## <a name="input"></a>Entrada

### <a name="op--t--unit"></a>OP: ' t [] = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Operación que se va a aplicar.


### <a name="targets--t"></a>destinos: ' t []

Matriz de destinos, de la que se aplicarán todos los, excepto el último `op` .



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a aplicar.

## <a name="example"></a>Ejemplo

Los siguientes fragmentos de código de Q # son equivalentes:

```qsharp
ApplyToMost(ApplyCNOTChain, register);
ApplyCNOTChain(Most(register));
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyToMostA](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [Microsoft. Quantum. Canon. ApplyToMostC](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [Microsoft. Quantum. Canon. ApplyToMostCA](xref:Microsoft.Quantum.Canon.ApplyToMostCA)