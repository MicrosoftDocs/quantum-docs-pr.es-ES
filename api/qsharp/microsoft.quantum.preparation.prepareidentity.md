---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Operación PrepareIdentity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: a3f96fbdafb19c90fb2b563243600cca60841566
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733725"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="e3bb1-102">Operación PrepareIdentity</span><span class="sxs-lookup"><span data-stu-id="e3bb1-102">PrepareIdentity operation</span></span>

<span data-ttu-id="e3bb1-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e3bb1-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e3bb1-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e3bb1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e3bb1-105">Dado un registro, prepara ese registro en el estado de máxima mezcla.</span><span class="sxs-lookup"><span data-stu-id="e3bb1-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="e3bb1-106">El registro se prepara en el estado $ \boldone/2 ^ N $ aplicando el canal de depolaridad completo a cada qubit, donde $N $ es la longitud del registro.</span><span class="sxs-lookup"><span data-stu-id="e3bb1-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e3bb1-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="e3bb1-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="e3bb1-108">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e3bb1-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e3bb1-109">Registro cuyo estado se va a despolar de la manera descrita anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e3bb1-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e3bb1-110">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e3bb1-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e3bb1-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3bb1-111">See Also</span></span>

- [<span data-ttu-id="e3bb1-112">Microsoft. Quantum. preparación. PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="e3bb1-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)