---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateCA
title: Operación PrepareChoiStateCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateCA
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.
ms.openlocfilehash: 6398a875923e03adcb31533dadd881d3c0744840
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856886"
---
# <a name="preparechoistateca-operation"></a>Operación PrepareChoiStateCA

Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Prepara el estado Choi – Jamiołkowski para una operación determinada con variantes controladas y contiguas en determinados registros de referencia y de destino.

```qsharp
operation PrepareChoiStateCA (op : (Qubit[] => Unit is Adj + Ctl), reference : Qubit[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="op--qubit--unit--is-adj--ctl"></a>OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL




### <a name="reference--qubit"></a>Referencia: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. preparación. PrepareChoiState](xref:Microsoft.Quantum.Preparation.PrepareChoiState)