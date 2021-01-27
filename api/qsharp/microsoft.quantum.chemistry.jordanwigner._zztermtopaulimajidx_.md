---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliMajIdx_
title: _ZZTermToPauliMajIdx_ función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: b18529182083ae6a905036ce6c00c3a0695ffccf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839048"
---
# <a name="_zztermtopaulimajidx_-function"></a><span data-ttu-id="aaf79-102">_ZZTermToPauliMajIdx_ función)</span><span class="sxs-lookup"><span data-stu-id="aaf79-102">_ZZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="aaf79-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="aaf79-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="aaf79-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="aaf79-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="aaf79-105">Convierte un GeneratorIndex que describe un término ZZ a una expresión ' GeneratorIndex [] ' en términos de Paulis.</span><span class="sxs-lookup"><span data-stu-id="aaf79-105">Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="aaf79-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="aaf79-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="aaf79-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="aaf79-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="aaf79-108">`GeneratorIndex` que representa un término ZZ.</span><span class="sxs-lookup"><span data-stu-id="aaf79-108">`GeneratorIndex` representing a ZZ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="aaf79-109">Salida: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="aaf79-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="aaf79-110">' GeneratorIndex [] ' que expresa el término ZZ como términos Pauli.</span><span class="sxs-lookup"><span data-stu-id="aaf79-110">'GeneratorIndex[]' expressing ZZ term as Pauli terms.</span></span>