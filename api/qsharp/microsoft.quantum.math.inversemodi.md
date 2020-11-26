---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 217ce4cd113ecbc6a06ed83c6c1dcb7baa46387d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195382"
---
# <a name="inversemodi-function"></a><span data-ttu-id="4e77d-102">InverseModI función)</span><span class="sxs-lookup"><span data-stu-id="4e77d-102">InverseModI function</span></span>

<span data-ttu-id="4e77d-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4e77d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4e77d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4e77d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4e77d-105">Devuelve $b $ de modo que $a \cdot b = 1 (\operatorname{mod} \texttt{modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="4e77d-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="4e77d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4e77d-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="4e77d-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4e77d-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4e77d-108">Número que se va a invertir.</span><span class="sxs-lookup"><span data-stu-id="4e77d-108">The number being inverted</span></span>


### <a name="modulus--int"></a><span data-ttu-id="4e77d-109">módulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4e77d-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4e77d-110">El módulo según el cual se invierten los números</span><span class="sxs-lookup"><span data-stu-id="4e77d-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--int"></a><span data-ttu-id="4e77d-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4e77d-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4e77d-112">Entero $b $ de modo que $a \cdot b = 1 (\operatorname{mod} \texttt{modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="4e77d-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>