---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliGenIdx_
title: _PQandPQQRTermToPauliGenIdx_ función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: c4de9593927b12b2387ae0b46513970308f59c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839327"
---
# <a name="_pqandpqqrtermtopauligenidx_-function"></a><span data-ttu-id="460db-102">_PQandPQQRTermToPauliGenIdx_ función)</span><span class="sxs-lookup"><span data-stu-id="460db-102">_PQandPQQRTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="460db-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="460db-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="460db-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="460db-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="460db-105">Convierte un GeneratorIndex que describe un término PQ o PQQR a una expresión ' GeneratorIndex [] ' en términos de Paulis</span><span class="sxs-lookup"><span data-stu-id="460db-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="460db-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="460db-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="460db-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="460db-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="460db-108">`GeneratorIndex` que representa un término de PQ o PQQR.</span><span class="sxs-lookup"><span data-stu-id="460db-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="460db-109">Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="460db-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="460db-110">' GeneratorIndex [] ' que expresa el término PQ o PQQR como términos Pauli.</span><span class="sxs-lookup"><span data-stu-id="460db-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>