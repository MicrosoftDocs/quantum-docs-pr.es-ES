---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855206"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="76500-102">WithZeroInsertedAt función)</span><span class="sxs-lookup"><span data-stu-id="76500-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="76500-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="76500-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="76500-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76500-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76500-105">Insertar un bit de 0 en un entero</span><span class="sxs-lookup"><span data-stu-id="76500-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="76500-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="76500-106">Description</span></span>

<span data-ttu-id="76500-107">Esta operación toma un entero, inserta un 0 en `position` el bit y devuelve el valor actualizado como un entero.</span><span class="sxs-lookup"><span data-stu-id="76500-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="76500-108">Por ejemplo, si se inserta un 0 en la posición 2 del número 10 (10 $ {10} = 1010_ {2} $), se devuelve el número 18 ($18 _ {10} = 10010_ {2} $).</span><span class="sxs-lookup"><span data-stu-id="76500-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="76500-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="76500-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="76500-110">posición: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="76500-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="76500-111">Posición en la que se inserta 0</span><span class="sxs-lookup"><span data-stu-id="76500-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="76500-112">valor: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="76500-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="76500-113">Valor que se modifica</span><span class="sxs-lookup"><span data-stu-id="76500-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="76500-114">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="76500-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="76500-115">Valor modificado</span><span class="sxs-lookup"><span data-stu-id="76500-115">Modified value</span></span>