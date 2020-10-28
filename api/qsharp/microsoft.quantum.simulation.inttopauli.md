---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: f0f1186f14a0dc30bb34bd29f148cdc830fd1337
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733701"
---
# <a name="inttopauli-function"></a><span data-ttu-id="50d6d-102">IntToPauli función)</span><span class="sxs-lookup"><span data-stu-id="50d6d-102">IntToPauli function</span></span>

<span data-ttu-id="50d6d-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="50d6d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="50d6d-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50d6d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50d6d-105">Convierte un entero en un operador Pauli de un solo qubit.</span><span class="sxs-lookup"><span data-stu-id="50d6d-105">Converts a integer to a single-qubit Pauli operator.</span></span>

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a><span data-ttu-id="50d6d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="50d6d-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="50d6d-107">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="50d6d-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="50d6d-108">Entero en el intervalo `0..3` que se va a convertir en operadores de Pauli.</span><span class="sxs-lookup"><span data-stu-id="50d6d-108">Integer in the range `0..3` to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="50d6d-109">Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="50d6d-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="50d6d-110">`Pauli`Operador proporcionado por `[PauliI, PauliX, PauliY, PauliZ][idx]` .</span><span class="sxs-lookup"><span data-stu-id="50d6d-110">A `Pauli` operator given by `[PauliI, PauliX, PauliY, PauliZ][idx]`.</span></span>