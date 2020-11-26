---
uid: Microsoft.Quantum.Math.PlusA
title: Función Plus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: fe19c5d2e075624516376a5d5fa49014acb295ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194838"
---
# <a name="plusa-function"></a><span data-ttu-id="1cb6b-102">Función Plus</span><span class="sxs-lookup"><span data-stu-id="1cb6b-102">PlusA function</span></span>

<span data-ttu-id="1cb6b-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1cb6b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1cb6b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1cb6b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1cb6b-105">Devuelve la suma (concatenación) de dos entradas.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="1cb6b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1cb6b-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="1cb6b-107">a: ' elemento []</span><span class="sxs-lookup"><span data-stu-id="1cb6b-107">a : 'Element[]</span></span>

<span data-ttu-id="1cb6b-108">Primera entrada $a $ que se va a sumar.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="1cb6b-109">b: ' elemento []</span><span class="sxs-lookup"><span data-stu-id="1cb6b-109">b : 'Element[]</span></span>

<span data-ttu-id="1cb6b-110">Segunda entrada $b $ que se va a sumar.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="1cb6b-111">Salida: ' elemento []</span><span class="sxs-lookup"><span data-stu-id="1cb6b-111">Output : 'Element[]</span></span>

<span data-ttu-id="1cb6b-112">La suma $a + b $.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1cb6b-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="1cb6b-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="1cb6b-114">Elemento '</span><span class="sxs-lookup"><span data-stu-id="1cb6b-114">'Element</span></span>

<span data-ttu-id="1cb6b-115">Tipo de cada elemento de cada una de las dos matrices de entrada.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-115">The type of each element in each of the two input arrays.</span></span>