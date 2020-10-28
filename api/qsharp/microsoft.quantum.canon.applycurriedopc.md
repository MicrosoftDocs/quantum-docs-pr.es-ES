---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpC
title: Operación ApplyCurriedOpC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpC
qsharp.summary: ''
ms.openlocfilehash: 1a00fe91889e3100e4d3272d258877b4ec88618f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729652"
---
# <a name="applycurriedopc-operation"></a><span data-ttu-id="ad089-102">Operación ApplyCurriedOpC</span><span class="sxs-lookup"><span data-stu-id="ad089-102">ApplyCurriedOpC operation</span></span>

<span data-ttu-id="ad089-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ad089-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ad089-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ad089-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="ad089-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="ad089-105">Input</span></span>

### <a name="curriedop--t---u--unit-ctl"></a><span data-ttu-id="ad089-106">curriedOp: ' U = > ' U => de la [unidad](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="ad089-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="ad089-107">primero: ' t</span><span class="sxs-lookup"><span data-stu-id="ad089-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="ad089-108">segundo: ' U</span><span class="sxs-lookup"><span data-stu-id="ad089-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="ad089-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad089-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ad089-110">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="ad089-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ad089-111">Traslada</span><span class="sxs-lookup"><span data-stu-id="ad089-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="ad089-112">' U</span><span class="sxs-lookup"><span data-stu-id="ad089-112">'U</span></span>

