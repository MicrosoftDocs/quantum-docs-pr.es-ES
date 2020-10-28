---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: Operación PrepareSingleQubitIdentity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 12a650568aa5682e8fb6498808d188b154527acb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733724"
---
# <a name="preparesinglequbitidentity-operation"></a><span data-ttu-id="4fd63-102">Operación PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="4fd63-102">PrepareSingleQubitIdentity operation</span></span>

<span data-ttu-id="4fd63-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="4fd63-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="4fd63-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4fd63-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4fd63-105">Prepara un qubit en el estado de máxima mezcla.</span><span class="sxs-lookup"><span data-stu-id="4fd63-105">Prepares a qubit in the maximally mixed state.</span></span>

<span data-ttu-id="4fd63-106">Prepara el qubit determinado en el estado $ \boldone/$2 mediante la aplicación del canal de despolar $ $ \begin{align} \Omega (\rho) \mathrel{: =} \frac {1} {4} \ sum_ {\mu \en \{ 0, 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}, \end{align} $ $ Where $ \sigma \_ i $ es el $i operador $ TH Pauli y donde $ \rho $ es un operador de densidad que representa un estado mixto.</span><span class="sxs-lookup"><span data-stu-id="4fd63-106">It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.</span></span>

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="4fd63-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="4fd63-107">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="4fd63-108">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4fd63-108">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4fd63-109">Un qubit cuyo estado se va a despolar de la manera descrita anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4fd63-109">A qubit whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4fd63-110">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4fd63-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4fd63-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4fd63-111">Remarks</span></span>

<span data-ttu-id="4fd63-112">El estado mixto $ \boldone/$2 que describe el resultado de aplicar esta operación a un estado describe implícitamente un valor de expectativa sobre las elecciones aleatorias realizadas en esta operación.</span><span class="sxs-lookup"><span data-stu-id="4fd63-112">The mixed state $\boldone / 2$ describing the result of applying this operation to a state implicitly describes an expectation value over random choices made in this operation.</span></span>
<span data-ttu-id="4fd63-113">Por lo tanto, para una sola aplicación, esta operación asigna Estados puros a Estados puros, pero actúa como se describe en expectativa.</span><span class="sxs-lookup"><span data-stu-id="4fd63-113">Thus, for any single application, this operation maps pure states to pure states, but it acts as described in expectation.</span></span>
<span data-ttu-id="4fd63-114">En concreto, esta operación se puede usar en el proceso Tomography para medir los componentes *no unitarios* de un canal.</span><span class="sxs-lookup"><span data-stu-id="4fd63-114">In particular, this operation can be used in process tomography to measure the *non-unital* components of a channel.</span></span>