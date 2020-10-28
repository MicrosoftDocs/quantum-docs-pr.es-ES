---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateCA
title: Operación PrepareChoiStateCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateCA
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.
ms.openlocfilehash: b9d2cdaea1ebc957719d92bf12901c54a55a56aa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725817"
---
# <a name="preparechoistateca-operation"></a>Operación PrepareChoiStateCA

Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)

Configura [](https://nuget.org/packages/)


Prepara el estado Choi – Jamiłkowski para una operación determinada con variantes controladas y contiguas en determinados registros de referencia y de destino.

```qsharp
operation PrepareChoiStateCA (op : (Qubit[] => Unit is Adj + Ctl), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="op--qubit--unit-adj--ctl"></a>OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL




### <a name="reference--qubit"></a>Referencia: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. preparación. PrepareChoiState](xref:Microsoft.Quantum.Preparation.PrepareChoiState)