---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: Operación ResetAll
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: d22ce607e8e5cb3a1c041dc1973875f2a0777d2b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198697"
---
# <a name="resetall-operation"></a><span data-ttu-id="0ed35-102">Operación ResetAll</span><span class="sxs-lookup"><span data-stu-id="0ed35-102">ResetAll operation</span></span>

<span data-ttu-id="0ed35-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="0ed35-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="0ed35-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0ed35-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0ed35-105">Dada una matriz de qubits, mida y asegúrese de que se encuentran en el estado | 0 ⟩ de modo que se puedan liberar de forma segura.</span><span class="sxs-lookup"><span data-stu-id="0ed35-105">Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.</span></span>

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0ed35-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0ed35-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="0ed35-107">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0ed35-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0ed35-108">Una matriz de qubits cuyos Estados se van a restablecer a $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="0ed35-108">An array of qubits whose states are to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0ed35-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0ed35-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

