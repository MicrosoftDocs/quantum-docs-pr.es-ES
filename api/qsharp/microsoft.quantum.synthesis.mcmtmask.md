---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: Tipo definido por el usuario MCMTMask
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 0d3ca12d55fa4b5e8332d50939954de29e39b715
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734076"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="6a72a-102">Tipo definido por el usuario MCMTMask</span><span class="sxs-lookup"><span data-stu-id="6a72a-102">MCMTMask user defined type</span></span>

<span data-ttu-id="6a72a-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="6a72a-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="6a72a-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6a72a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6a72a-105">Tipo que representa una puerta Toffoli de varios destinos múltiples controlada.</span><span class="sxs-lookup"><span data-stu-id="6a72a-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="6a72a-106">El primer entero es una máscara de bits para las líneas de control.</span><span class="sxs-lookup"><span data-stu-id="6a72a-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="6a72a-107">Los índices de bits establecidos corresponden a los índices de línea de control.</span><span class="sxs-lookup"><span data-stu-id="6a72a-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="6a72a-108">El segundo entero es una máscara de bits para las líneas de destino.</span><span class="sxs-lookup"><span data-stu-id="6a72a-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="6a72a-109">Los índices de bits establecidos corresponden a los índices de línea de destino.</span><span class="sxs-lookup"><span data-stu-id="6a72a-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="6a72a-110">Los índices de bits de ambos enteros deben estar separados.</span><span class="sxs-lookup"><span data-stu-id="6a72a-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="6a72a-111">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="6a72a-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="6a72a-112">ControlMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6a72a-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="6a72a-113">TargetMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6a72a-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>
