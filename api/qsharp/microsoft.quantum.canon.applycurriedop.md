---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: Operación ApplyCurriedOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: c252eceb6a307ea9514aaa8aa3a3de1f9fa1b698
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841934"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="09e40-102">Operación ApplyCurriedOp</span><span class="sxs-lookup"><span data-stu-id="09e40-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="09e40-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="09e40-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="09e40-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="09e40-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="09e40-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="09e40-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="09e40-106">curriedOp: ' U = [unidad](xref:microsoft.quantum.lang-ref.unit) > de></span><span class="sxs-lookup"><span data-stu-id="09e40-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="09e40-107">primero: ' t</span><span class="sxs-lookup"><span data-stu-id="09e40-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="09e40-108">segundo: ' U</span><span class="sxs-lookup"><span data-stu-id="09e40-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="09e40-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09e40-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="09e40-110">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="09e40-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="09e40-111">Traslada</span><span class="sxs-lookup"><span data-stu-id="09e40-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="09e40-112">' U</span><span class="sxs-lookup"><span data-stu-id="09e40-112">'U</span></span>

