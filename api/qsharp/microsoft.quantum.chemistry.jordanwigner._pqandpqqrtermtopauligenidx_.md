---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliGenIdx_
title: _PQandPQQRTermToPauliGenIdx_ función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 44a6d6b63d2f6bc8b628603e78931570d1ec22eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727929"
---
# <a name="_pqandpqqrtermtopauligenidx_-function"></a><span data-ttu-id="bac28-102">_PQandPQQRTermToPauliGenIdx_ función)</span><span class="sxs-lookup"><span data-stu-id="bac28-102">_PQandPQQRTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="bac28-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="bac28-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="bac28-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bac28-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bac28-105">Convierte un GeneratorIndex que describe un término PQ o PQQR a una expresión ' GeneratorIndex [] ' en términos de Paulis</span><span class="sxs-lookup"><span data-stu-id="bac28-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="bac28-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bac28-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="bac28-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="bac28-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="bac28-108">`GeneratorIndex` que representa un término de PQ o PQQR.</span><span class="sxs-lookup"><span data-stu-id="bac28-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="bac28-109">Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="bac28-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="bac28-110">' GeneratorIndex [] ' que expresa el término PQ o PQQR como términos Pauli.</span><span class="sxs-lookup"><span data-stu-id="bac28-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>