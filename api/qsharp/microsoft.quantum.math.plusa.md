---
uid: Microsoft.Quantum.Math.PlusA
title: Función Plus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 14e9bfdbe4b70b4730e5bfc64a0ee81ab3cecaaf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842712"
---
# <a name="plusa-function"></a><span data-ttu-id="c084e-102">Función Plus</span><span class="sxs-lookup"><span data-stu-id="c084e-102">PlusA function</span></span>

<span data-ttu-id="c084e-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c084e-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c084e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c084e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c084e-105">Devuelve la suma (concatenación) de dos entradas.</span><span class="sxs-lookup"><span data-stu-id="c084e-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="c084e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c084e-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="c084e-107">a: ' elemento []</span><span class="sxs-lookup"><span data-stu-id="c084e-107">a : 'Element[]</span></span>

<span data-ttu-id="c084e-108">Primera entrada $a $ que se va a sumar.</span><span class="sxs-lookup"><span data-stu-id="c084e-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="c084e-109">b: ' elemento []</span><span class="sxs-lookup"><span data-stu-id="c084e-109">b : 'Element[]</span></span>

<span data-ttu-id="c084e-110">Segunda entrada $b $ que se va a sumar.</span><span class="sxs-lookup"><span data-stu-id="c084e-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="c084e-111">Salida: ' elemento []</span><span class="sxs-lookup"><span data-stu-id="c084e-111">Output : 'Element[]</span></span>

<span data-ttu-id="c084e-112">La suma $a + b $.</span><span class="sxs-lookup"><span data-stu-id="c084e-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c084e-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c084e-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="c084e-114">Elemento '</span><span class="sxs-lookup"><span data-stu-id="c084e-114">'Element</span></span>

<span data-ttu-id="c084e-115">Tipo de cada elemento de cada una de las dos matrices de entrada.</span><span class="sxs-lookup"><span data-stu-id="c084e-115">The type of each element in each of the two input arrays.</span></span>