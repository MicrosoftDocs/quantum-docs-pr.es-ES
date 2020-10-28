---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: Operación ApplyBlockEncodingByLCU
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 1575b93b6c3242e1dffafb330c44cc017a72a8b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732148"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="75310-102">Operación ApplyBlockEncodingByLCU</span><span class="sxs-lookup"><span data-stu-id="75310-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="75310-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="75310-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="75310-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="75310-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="75310-105">Implementación de `BlockEncodingByLCU`.</span><span class="sxs-lookup"><span data-stu-id="75310-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit
```


## <a name="input"></a><span data-ttu-id="75310-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="75310-106">Input</span></span>

### <a name="statepreparation--t--unit-adj--ctl"></a><span data-ttu-id="75310-107">statePreparation: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="75310-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="selector--ts--unit-adj--ctl"></a><span data-ttu-id="75310-108">Selector: (' t, ') => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="75310-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="75310-109">auxiliar: ' t '</span><span class="sxs-lookup"><span data-stu-id="75310-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="75310-110">sistema:</span><span class="sxs-lookup"><span data-stu-id="75310-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="75310-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="75310-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="75310-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="75310-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="75310-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="75310-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="75310-114">Hoy</span><span class="sxs-lookup"><span data-stu-id="75310-114">'S</span></span>

