---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpCA
title: Operación ApplyCurriedOpCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpCA
qsharp.summary: ''
ms.openlocfilehash: 4e57772bc5440a473c28279ac125170caaa120f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729645"
---
# <a name="applycurriedopca-operation"></a><span data-ttu-id="a3b51-102">Operación ApplyCurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="a3b51-102">ApplyCurriedOpCA operation</span></span>

<span data-ttu-id="a3b51-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a3b51-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a3b51-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a3b51-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="a3b51-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="a3b51-105">Input</span></span>

### <a name="curriedop--t---u--unit-ctl--adj"></a><span data-ttu-id="a3b51-106">curriedOp: ' t-> ' U => [unidad](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="a3b51-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="a3b51-107">primero: ' t</span><span class="sxs-lookup"><span data-stu-id="a3b51-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="a3b51-108">segundo: ' U</span><span class="sxs-lookup"><span data-stu-id="a3b51-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="a3b51-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3b51-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a3b51-110">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="a3b51-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a3b51-111">Traslada</span><span class="sxs-lookup"><span data-stu-id="a3b51-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="a3b51-112">' U</span><span class="sxs-lookup"><span data-stu-id="a3b51-112">'U</span></span>

