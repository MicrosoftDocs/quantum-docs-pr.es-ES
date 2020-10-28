---
uid: Microsoft.Quantum.Canon.MultiplexOperationsWithAuxRegister
title: Operación MultiplexOperationsWithAuxRegister
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsWithAuxRegister
qsharp.summary: Implementation step of MultiplexOperations.
ms.openlocfilehash: f6a90657324f8528aaa2e9e511a7f8cbcd2f540f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728540"
---
# <a name="multiplexoperationswithauxregister-operation"></a>Operación MultiplexOperationsWithAuxRegister

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Paso de implementación de MultiplexOperations.

```qsharp
operation MultiplexOperationsWithAuxRegister<'T> (unitaries : ('T => Unit is Adj + Ctl)[], auxillaryRegister : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a>Entrada

### <a name="unitaries--t--unit-adj--ctl"></a>unitaries: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL []




### <a name="auxillaryregister--qubit"></a>auxillaryRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="index--littleendian"></a>Índice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)




### <a name="target--t"></a>destino: ' t





## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. MultiplexOperations](xref:Microsoft.Quantum.Canon.MultiplexOperations)