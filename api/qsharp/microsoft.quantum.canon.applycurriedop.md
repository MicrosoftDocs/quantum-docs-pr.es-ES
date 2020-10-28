---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: Operación ApplyCurriedOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: 22e2ace51175ed9df1c70bf75ce2b497f8449020
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729661"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="261f6-102">Operación ApplyCurriedOp</span><span class="sxs-lookup"><span data-stu-id="261f6-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="261f6-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="261f6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="261f6-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="261f6-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="261f6-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="261f6-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="261f6-106">curriedOp: ' U = [unidad](xref:microsoft.quantum.lang-ref.unit) > de></span><span class="sxs-lookup"><span data-stu-id="261f6-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="261f6-107">primero: ' t</span><span class="sxs-lookup"><span data-stu-id="261f6-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="261f6-108">segundo: ' U</span><span class="sxs-lookup"><span data-stu-id="261f6-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="261f6-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="261f6-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="261f6-110">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="261f6-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="261f6-111">Traslada</span><span class="sxs-lookup"><span data-stu-id="261f6-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="261f6-112">' U</span><span class="sxs-lookup"><span data-stu-id="261f6-112">'U</span></span>

