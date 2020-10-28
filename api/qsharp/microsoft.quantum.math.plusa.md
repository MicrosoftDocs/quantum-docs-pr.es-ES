---
uid: Microsoft.Quantum.Math.PlusA
title: Función Plus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 0c6fdcf7c59dc5d89bf83e285339046b5ad5a57e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725888"
---
# <a name="plusa-function"></a><span data-ttu-id="28c90-102">Función Plus</span><span class="sxs-lookup"><span data-stu-id="28c90-102">PlusA function</span></span>

<span data-ttu-id="28c90-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="28c90-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="28c90-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="28c90-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="28c90-105">Devuelve la suma (concatenación) de dos entradas.</span><span class="sxs-lookup"><span data-stu-id="28c90-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="28c90-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="28c90-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="28c90-107">a: ' elemento []</span><span class="sxs-lookup"><span data-stu-id="28c90-107">a : 'Element[]</span></span>

<span data-ttu-id="28c90-108">Primera entrada $a $ que se va a sumar.</span><span class="sxs-lookup"><span data-stu-id="28c90-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="28c90-109">b: ' elemento []</span><span class="sxs-lookup"><span data-stu-id="28c90-109">b : 'Element[]</span></span>

<span data-ttu-id="28c90-110">Segunda entrada $b $ que se va a sumar.</span><span class="sxs-lookup"><span data-stu-id="28c90-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="28c90-111">Salida: ' elemento []</span><span class="sxs-lookup"><span data-stu-id="28c90-111">Output : 'Element[]</span></span>

<span data-ttu-id="28c90-112">La suma $a + b $.</span><span class="sxs-lookup"><span data-stu-id="28c90-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="28c90-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="28c90-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="28c90-114">Elemento '</span><span class="sxs-lookup"><span data-stu-id="28c90-114">'Element</span></span>

<span data-ttu-id="28c90-115">Tipo de cada elemento de cada una de las dos matrices de entrada.</span><span class="sxs-lookup"><span data-stu-id="28c90-115">The type of each element in each of the two input arrays.</span></span>