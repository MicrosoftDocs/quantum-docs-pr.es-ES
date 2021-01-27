---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliGenIdx
title: _ZZTermToPauliGenIdx función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 0bbb0325406767f9d27e317ccc306f1fe77d00f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839078"
---
# <a name="_zztermtopauligenidx-function"></a><span data-ttu-id="0d108-102">_ZZTermToPauliGenIdx función)</span><span class="sxs-lookup"><span data-stu-id="0d108-102">_ZZTermToPauliGenIdx function</span></span>

<span data-ttu-id="0d108-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="0d108-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="0d108-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0d108-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="0d108-105">Convierte un GeneratorIndex que describe un término ZZ a una expresión ' GeneratorIndex [] ' en términos de Paulis.</span><span class="sxs-lookup"><span data-stu-id="0d108-105">Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="0d108-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0d108-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="0d108-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="0d108-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="0d108-108">`GeneratorIndex` que representa un término ZZ.</span><span class="sxs-lookup"><span data-stu-id="0d108-108">`GeneratorIndex` representing a ZZ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="0d108-109">Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="0d108-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="0d108-110">' GeneratorIndex [] ' que expresa el término ZZ como términos Pauli.</span><span class="sxs-lookup"><span data-stu-id="0d108-110">'GeneratorIndex[]' expressing ZZ term as Pauli terms.</span></span>