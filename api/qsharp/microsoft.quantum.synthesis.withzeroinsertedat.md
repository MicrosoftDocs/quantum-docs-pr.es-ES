---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 414b703151b9152aa69709d9c28e68e5ae63506f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228872"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="97e6a-102">WithZeroInsertedAt función)</span><span class="sxs-lookup"><span data-stu-id="97e6a-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="97e6a-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="97e6a-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="97e6a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="97e6a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="97e6a-105">Insertar un bit de 0 en un entero</span><span class="sxs-lookup"><span data-stu-id="97e6a-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="97e6a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="97e6a-106">Description</span></span>

<span data-ttu-id="97e6a-107">Esta operación toma un entero, inserta un 0 en `position` el bit y devuelve el valor actualizado como un entero.</span><span class="sxs-lookup"><span data-stu-id="97e6a-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="97e6a-108">Por ejemplo, si se inserta un 0 en la posición 2 del número 10 (10 $ {10} = 1010_ {2} $), se devuelve el número 18 ($18 _ {10} = 10010_ {2} $).</span><span class="sxs-lookup"><span data-stu-id="97e6a-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="97e6a-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="97e6a-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="97e6a-110">posición: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97e6a-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="97e6a-111">Posición en la que se inserta 0</span><span class="sxs-lookup"><span data-stu-id="97e6a-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="97e6a-112">valor: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97e6a-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="97e6a-113">Valor que se modifica</span><span class="sxs-lookup"><span data-stu-id="97e6a-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="97e6a-114">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97e6a-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="97e6a-115">Valor modificado</span><span class="sxs-lookup"><span data-stu-id="97e6a-115">Modified value</span></span>