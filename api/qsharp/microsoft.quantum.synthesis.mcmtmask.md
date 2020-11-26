---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: Tipo definido por el usuario MCMTMask
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 3c2debbb1f2019c7188dcb00f8ac09154fd4fd4f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203031"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="55c4f-102">Tipo definido por el usuario MCMTMask</span><span class="sxs-lookup"><span data-stu-id="55c4f-102">MCMTMask user defined type</span></span>

<span data-ttu-id="55c4f-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="55c4f-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="55c4f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="55c4f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="55c4f-105">Tipo que representa una puerta Toffoli de varios destinos múltiples controlada.</span><span class="sxs-lookup"><span data-stu-id="55c4f-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="55c4f-106">El primer entero es una máscara de bits para las líneas de control.</span><span class="sxs-lookup"><span data-stu-id="55c4f-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="55c4f-107">Los índices de bits establecidos corresponden a los índices de línea de control.</span><span class="sxs-lookup"><span data-stu-id="55c4f-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="55c4f-108">El segundo entero es una máscara de bits para las líneas de destino.</span><span class="sxs-lookup"><span data-stu-id="55c4f-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="55c4f-109">Los índices de bits establecidos corresponden a los índices de línea de destino.</span><span class="sxs-lookup"><span data-stu-id="55c4f-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="55c4f-110">Los índices de bits de ambos enteros deben estar separados.</span><span class="sxs-lookup"><span data-stu-id="55c4f-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="55c4f-111">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="55c4f-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="55c4f-112">ControlMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55c4f-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="55c4f-113">TargetMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55c4f-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

