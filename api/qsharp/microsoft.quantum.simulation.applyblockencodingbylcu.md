---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: Operación ApplyBlockEncodingByLCU
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: a9a9e3bbd598453719f49f78392f3a92c9401b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852824"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="665ae-102">Operación ApplyBlockEncodingByLCU</span><span class="sxs-lookup"><span data-stu-id="665ae-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="665ae-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="665ae-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="665ae-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="665ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="665ae-105">Implementación de `BlockEncodingByLCU`.</span><span class="sxs-lookup"><span data-stu-id="665ae-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="665ae-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="665ae-106">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="665ae-107">statePreparation: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="665ae-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="665ae-108">Selector: (' t, ') => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="665ae-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="665ae-109">auxiliar: ' t '</span><span class="sxs-lookup"><span data-stu-id="665ae-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="665ae-110">sistema:</span><span class="sxs-lookup"><span data-stu-id="665ae-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="665ae-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="665ae-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="665ae-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="665ae-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="665ae-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="665ae-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="665ae-114">Hoy</span><span class="sxs-lookup"><span data-stu-id="665ae-114">'S</span></span>

