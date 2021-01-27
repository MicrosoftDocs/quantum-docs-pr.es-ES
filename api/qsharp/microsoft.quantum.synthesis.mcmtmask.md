---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: Tipo definido por el usuario MCMTMask
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 50bec0f9aca95afab83491db6b742d1f0323371f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855369"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="6b4c9-102">Tipo definido por el usuario MCMTMask</span><span class="sxs-lookup"><span data-stu-id="6b4c9-102">MCMTMask user defined type</span></span>

<span data-ttu-id="6b4c9-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="6b4c9-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="6b4c9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b4c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b4c9-105">Tipo que representa una puerta Toffoli de varios destinos múltiples controlada.</span><span class="sxs-lookup"><span data-stu-id="6b4c9-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="6b4c9-106">El primer entero es una máscara de bits para las líneas de control.</span><span class="sxs-lookup"><span data-stu-id="6b4c9-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="6b4c9-107">Los índices de bits establecidos corresponden a los índices de línea de control.</span><span class="sxs-lookup"><span data-stu-id="6b4c9-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="6b4c9-108">El segundo entero es una máscara de bits para las líneas de destino.</span><span class="sxs-lookup"><span data-stu-id="6b4c9-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="6b4c9-109">Los índices de bits establecidos corresponden a los índices de línea de destino.</span><span class="sxs-lookup"><span data-stu-id="6b4c9-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="6b4c9-110">Los índices de bits de ambos enteros deben estar separados.</span><span class="sxs-lookup"><span data-stu-id="6b4c9-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="6b4c9-111">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="6b4c9-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="6b4c9-112">ControlMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6b4c9-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="6b4c9-113">TargetMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6b4c9-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

