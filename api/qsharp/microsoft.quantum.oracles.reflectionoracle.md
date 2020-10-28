---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Tipo definido por el usuario ReflectionOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733340"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="b3641-102">Tipo definido por el usuario ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="b3641-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="b3641-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="b3641-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="b3641-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b3641-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b3641-105">Representa una reflexión de Oracle.</span><span class="sxs-lookup"><span data-stu-id="b3641-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="b3641-106">Una reflexión de Oracle, $O $, tiene entradas:</span><span class="sxs-lookup"><span data-stu-id="b3641-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="b3641-107">Fase $ \phi $ por la que se va a girar el subespacio reflejado.</span><span class="sxs-lookup"><span data-stu-id="b3641-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="b3641-108">Registro qubit en el que se va a realizar la reflexión determinada.</span><span class="sxs-lookup"><span data-stu-id="b3641-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="b3641-109">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="b3641-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a><span data-ttu-id="b3641-110">ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="b3641-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="b3641-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b3641-111">Remarks</span></span>

<span data-ttu-id="b3641-112">Esta $O de Oracle = \boldone-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ realiza una reflexión parcial en una fase $ \phi $ sobre un único estado puro $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="b3641-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>