---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 6efc9da5f5ebb64065a90e749daa629dc2dce9cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733012"
---
# <a name="inversemodi-function"></a><span data-ttu-id="c2ece-102">InverseModI función)</span><span class="sxs-lookup"><span data-stu-id="c2ece-102">InverseModI function</span></span>

<span data-ttu-id="c2ece-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c2ece-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c2ece-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c2ece-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c2ece-105">Devuelve $b $ de modo que $a \cdot b = 1 (\operatorname{mod} \texttt{modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="c2ece-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="c2ece-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c2ece-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="c2ece-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c2ece-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c2ece-108">Número que se va a invertir.</span><span class="sxs-lookup"><span data-stu-id="c2ece-108">The number being inverted</span></span>


### <a name="modulus--int"></a><span data-ttu-id="c2ece-109">módulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c2ece-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c2ece-110">El módulo según el cual se invierten los números</span><span class="sxs-lookup"><span data-stu-id="c2ece-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--int"></a><span data-ttu-id="c2ece-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c2ece-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c2ece-112">Entero $b $ de modo que $a \cdot b = 1 (\operatorname{mod} \texttt{modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="c2ece-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>