---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: Operación ApplyCurriedOpA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: db3f63cbe2ee5ef048c7e378864d68696f55331f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218961"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="b0ff9-102">Operación ApplyCurriedOpA</span><span class="sxs-lookup"><span data-stu-id="b0ff9-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="b0ff9-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b0ff9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b0ff9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0ff9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="b0ff9-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="b0ff9-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="b0ff9-106">curriedOp: ' t-> ' U = [unidad](xref:microsoft.quantum.lang-ref.unit)  de> es ADJ</span><span class="sxs-lookup"><span data-stu-id="b0ff9-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="b0ff9-107">primero: ' t</span><span class="sxs-lookup"><span data-stu-id="b0ff9-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="b0ff9-108">segundo: ' U</span><span class="sxs-lookup"><span data-stu-id="b0ff9-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="b0ff9-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0ff9-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b0ff9-110">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="b0ff9-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b0ff9-111">Traslada</span><span class="sxs-lookup"><span data-stu-id="b0ff9-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="b0ff9-112">' U</span><span class="sxs-lookup"><span data-stu-id="b0ff9-112">'U</span></span>

