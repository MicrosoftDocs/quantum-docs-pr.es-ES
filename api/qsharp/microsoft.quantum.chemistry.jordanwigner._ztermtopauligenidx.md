---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliGenIdx
title: _ZTermToPauliGenIdx función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 4e08ef7f5033b22cb69e77936f83229cbd85aa64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839103"
---
# <a name="_ztermtopauligenidx-function"></a><span data-ttu-id="66b9e-102">_ZTermToPauliGenIdx función)</span><span class="sxs-lookup"><span data-stu-id="66b9e-102">_ZTermToPauliGenIdx function</span></span>

<span data-ttu-id="66b9e-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="66b9e-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="66b9e-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="66b9e-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="66b9e-105">Convierte un GeneratorIndex que describe un término Z a una expresión ' GeneratorIndex [] ' en términos de Paulis.</span><span class="sxs-lookup"><span data-stu-id="66b9e-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="66b9e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="66b9e-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="66b9e-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="66b9e-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="66b9e-108">`GeneratorIndex` que representa un término Z.</span><span class="sxs-lookup"><span data-stu-id="66b9e-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="66b9e-109">Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="66b9e-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="66b9e-110">' GeneratorIndex [] ' expresando el término Z como términos Pauli.</span><span class="sxs-lookup"><span data-stu-id="66b9e-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>