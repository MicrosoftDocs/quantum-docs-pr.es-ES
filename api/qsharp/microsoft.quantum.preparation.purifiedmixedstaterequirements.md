---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 6ddb48ba66eea87a07d515ff791bfb34f2d98b76
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856828"
---
# <a name="purifiedmixedstaterequirements-function"></a><span data-ttu-id="2eb86-102">PurifiedMixedStateRequirements función)</span><span class="sxs-lookup"><span data-stu-id="2eb86-102">PurifiedMixedStateRequirements function</span></span>

<span data-ttu-id="2eb86-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="2eb86-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="2eb86-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2eb86-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2eb86-105">Devuelve el número total de qubits que deben asignarse para aplicar la operación devuelta por @"microsoft.quantum.preparation.purifiedmixedstate" .</span><span class="sxs-lookup"><span data-stu-id="2eb86-105">Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".</span></span>

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a><span data-ttu-id="2eb86-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2eb86-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="2eb86-107">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2eb86-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2eb86-108">El error de destino $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="2eb86-108">The target error $\epsilon$.</span></span>


### <a name="ncoefficients--int"></a><span data-ttu-id="2eb86-109">nCoefficients: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2eb86-109">nCoefficients : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2eb86-110">El número de coeficientes que se van a especificar en la preparación de un estado mixto.</span><span class="sxs-lookup"><span data-stu-id="2eb86-110">The number of coefficients to be specified in preparing a mixed state.</span></span>



## <a name="output--mixedstatepreparationrequirements"></a><span data-ttu-id="2eb86-111">Salida: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span><span class="sxs-lookup"><span data-stu-id="2eb86-111">Output : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span></span>

<span data-ttu-id="2eb86-112">Una descripción de cuántos qubits son necesarias en total y para cada uno de los registros de índice y de elementos no utilizados usados por la @"microsoft.quantum.preparation.purifiedmixedstate" función.</span><span class="sxs-lookup"><span data-stu-id="2eb86-112">A description of how many qubits are required in total, and for each of the index and garbage registers used by the @"microsoft.quantum.preparation.purifiedmixedstate" function.</span></span>

## <a name="see-also"></a><span data-ttu-id="2eb86-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2eb86-113">See Also</span></span>

- [<span data-ttu-id="2eb86-114">Microsoft. Quantum. preparación. PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="2eb86-114">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)