---
uid: Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
title: Tipo definido por el usuario MixedStatePreparationRequirements
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparationRequirements
qsharp.summary: Represents the number of qubits required in order to prepare a given mixed state.
ms.openlocfilehash: df57b7b43fc84f7ddf68392f6a2b7013225da730
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856930"
---
# <a name="mixedstatepreparationrequirements-user-defined-type"></a><span data-ttu-id="2fa16-102">Tipo definido por el usuario MixedStatePreparationRequirements</span><span class="sxs-lookup"><span data-stu-id="2fa16-102">MixedStatePreparationRequirements user defined type</span></span>

<span data-ttu-id="2fa16-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="2fa16-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="2fa16-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2fa16-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2fa16-105">Representa el número de qubits necesarios para preparar un estado mixto determinado.</span><span class="sxs-lookup"><span data-stu-id="2fa16-105">Represents the number of qubits required in order to prepare a given mixed state.</span></span>

```qsharp

newtype MixedStatePreparationRequirements = (NTotalQubits : Int, (NIndexQubits : Int, NGarbageQubits : Int));
```



## <a name="named-items"></a><span data-ttu-id="2fa16-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="2fa16-106">Named Items</span></span>

### <a name="ntotalqubits--int"></a><span data-ttu-id="2fa16-107">NTotalQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2fa16-107">NTotalQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="nindexqubits--int"></a><span data-ttu-id="2fa16-108">NIndexQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2fa16-108">NIndexQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="ngarbagequbits--int"></a><span data-ttu-id="2fa16-109">NGarbageQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2fa16-109">NGarbageQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="see-also"></a><span data-ttu-id="2fa16-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2fa16-110">See Also</span></span>

- [<span data-ttu-id="2fa16-111">Microsoft. Quantum. PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="2fa16-111">Microsoft.Quantum.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.PurifiedMixedState)