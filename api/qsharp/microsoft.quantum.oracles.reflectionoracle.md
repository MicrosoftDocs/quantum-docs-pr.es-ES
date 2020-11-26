---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Tipo definido por el usuario ReflectionOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 7bb0626e7cca9ae0b640699ea57f2e114bda2d06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226662"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="8826f-102">Tipo definido por el usuario ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="8826f-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="8826f-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="8826f-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="8826f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8826f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8826f-105">Representa una reflexión de Oracle.</span><span class="sxs-lookup"><span data-stu-id="8826f-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="8826f-106">Una reflexión de Oracle, $O $, tiene entradas:</span><span class="sxs-lookup"><span data-stu-id="8826f-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="8826f-107">Fase $ \phi $ por la que se va a girar el subespacio reflejado.</span><span class="sxs-lookup"><span data-stu-id="8826f-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="8826f-108">Registro qubit en el que se va a realizar la reflexión determinada.</span><span class="sxs-lookup"><span data-stu-id="8826f-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="8826f-109">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="8826f-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a><span data-ttu-id="8826f-110">ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="8826f-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="8826f-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8826f-111">Remarks</span></span>

<span data-ttu-id="8826f-112">Esta $O de Oracle = \boldone-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ realiza una reflexión parcial en una fase $ \phi $ sobre un único estado puro $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="8826f-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>