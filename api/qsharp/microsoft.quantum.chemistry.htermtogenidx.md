---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 46745632e2f6bafad0d7359141522b84f48c039d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839615"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="fe80d-102">HTermToGenIdx función)</span><span class="sxs-lookup"><span data-stu-id="fe80d-102">HTermToGenIdx function</span></span>

<span data-ttu-id="fe80d-103">Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="fe80d-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="fe80d-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="fe80d-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="fe80d-105">Convierte un término Hamiltonian en `HTerm` formato de datos en un GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="fe80d-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="fe80d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fe80d-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="fe80d-107">término: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="fe80d-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="fe80d-108">Datos de entrada en `HTerm` formato.</span><span class="sxs-lookup"><span data-stu-id="fe80d-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="fe80d-109">Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fe80d-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fe80d-110">Información adicional agregada a GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="fe80d-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="fe80d-111">Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="fe80d-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="fe80d-112">Un GeneratorIndex que representa un término Hamiltonian representado por `term` , junto con información adicional agregada por `termType` .</span><span class="sxs-lookup"><span data-stu-id="fe80d-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>