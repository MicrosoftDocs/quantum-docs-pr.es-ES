---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229212"
---
# <a name="inttopauli-function"></a><span data-ttu-id="c1eaa-102">IntToPauli función)</span><span class="sxs-lookup"><span data-stu-id="c1eaa-102">IntToPauli function</span></span>

<span data-ttu-id="c1eaa-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c1eaa-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c1eaa-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c1eaa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c1eaa-105">Convierte un entero en un operador Pauli de un solo qubit.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-105">Converts a integer to a single-qubit Pauli operator.</span></span>

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a><span data-ttu-id="c1eaa-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c1eaa-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="c1eaa-107">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c1eaa-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c1eaa-108">Entero en el intervalo `0..3` que se va a convertir en operadores de Pauli.</span><span class="sxs-lookup"><span data-stu-id="c1eaa-108">Integer in the range `0..3` to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="c1eaa-109">Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="c1eaa-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="c1eaa-110">`Pauli`Operador proporcionado por `[PauliI, PauliX, PauliY, PauliZ][idx]` .</span><span class="sxs-lookup"><span data-stu-id="c1eaa-110">A `Pauli` operator given by `[PauliI, PauliX, PauliY, PauliZ][idx]`.</span></span>