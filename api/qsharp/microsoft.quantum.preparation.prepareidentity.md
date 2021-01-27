---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Operación PrepareIdentity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: ec7e813110ccd9e6d499fc469fa27249a182b870
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855889"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="c8fc7-102">Operación PrepareIdentity</span><span class="sxs-lookup"><span data-stu-id="c8fc7-102">PrepareIdentity operation</span></span>

<span data-ttu-id="c8fc7-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="c8fc7-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="c8fc7-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8fc7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8fc7-105">Dado un registro, prepara ese registro en el estado de máxima mezcla.</span><span class="sxs-lookup"><span data-stu-id="c8fc7-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="c8fc7-106">El registro se prepara en el estado $ \boldone/2 ^ N $ aplicando el canal de depolaridad completo a cada qubit, donde $N $ es la longitud del registro.</span><span class="sxs-lookup"><span data-stu-id="c8fc7-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c8fc7-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="c8fc7-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="c8fc7-108">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c8fc7-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c8fc7-109">Registro cuyo estado se va a despolar de la manera descrita anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c8fc7-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c8fc7-110">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c8fc7-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c8fc7-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8fc7-111">See Also</span></span>

- [<span data-ttu-id="c8fc7-112">Microsoft. Quantum. preparación. PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="c8fc7-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)