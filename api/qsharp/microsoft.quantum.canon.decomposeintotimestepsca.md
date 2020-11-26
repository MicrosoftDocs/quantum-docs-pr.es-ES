---
uid: Microsoft.Quantum.Canon.DecomposeIntoTimeStepsCA
title: DecomposeIntoTimeStepsCA función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposeIntoTimeStepsCA
qsharp.summary: >-
  > [!WARNING]

  > DecomposeIntoTimeStepsCA has been deprecated. Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.
ms.openlocfilehash: 4443af5884755f72fac6f9b76f95c3831c67b13f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207180"
---
# <a name="decomposeintotimestepsca-function"></a><span data-ttu-id="db151-102">DecomposeIntoTimeStepsCA función)</span><span class="sxs-lookup"><span data-stu-id="db151-102">DecomposeIntoTimeStepsCA function</span></span>

<span data-ttu-id="db151-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="db151-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="db151-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="db151-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="db151-105">DecomposeIntoTimeStepsCA está en desuso.</span><span class="sxs-lookup"><span data-stu-id="db151-105">DecomposeIntoTimeStepsCA has been deprecated.</span></span> <span data-ttu-id="db151-106">Use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="db151-106">Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.</span></span>



```qsharp
function DecomposeIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="db151-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="db151-107">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="db151-108">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db151-108">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="db151-109">OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="db151-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="trotterorder--int"></a><span data-ttu-id="db151-110">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db151-110">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--doublet--unit--is-adj--ctl"></a><span data-ttu-id="db151-111">Salida: ([Double](xref:microsoft.quantum.lang-ref.double), ' t) => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="db151-111">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="type-parameters"></a><span data-ttu-id="db151-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="db151-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="db151-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="db151-113">'T</span></span>

