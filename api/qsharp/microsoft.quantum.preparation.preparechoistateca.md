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
# <a name="preparechoistateca-operation"></a><span data-ttu-id="0d2c5-102">Operación PrepareChoiStateCA</span><span class="sxs-lookup"><span data-stu-id="0d2c5-102">PrepareChoiStateCA operation</span></span>

<span data-ttu-id="0d2c5-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="0d2c5-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="0d2c5-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0d2c5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0d2c5-105">Prepara el estado Choi – Jamiłkowski para una operación determinada con variantes controladas y contiguas en determinados registros de referencia y de destino.</span><span class="sxs-lookup"><span data-stu-id="0d2c5-105">Prepares the Choi–Jamiłkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiStateCA (op : (Qubit[] => Unit is Adj + Ctl), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0d2c5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0d2c5-106">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="0d2c5-107">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="0d2c5-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="reference--qubit"></a><span data-ttu-id="0d2c5-108">Referencia: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0d2c5-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="0d2c5-109">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0d2c5-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="0d2c5-110">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d2c5-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0d2c5-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d2c5-111">See Also</span></span>

- [<span data-ttu-id="0d2c5-112">Microsoft. Quantum. preparación. PrepareChoiState</span><span class="sxs-lookup"><span data-stu-id="0d2c5-112">Microsoft.Quantum.Preparation.PrepareChoiState</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiState)