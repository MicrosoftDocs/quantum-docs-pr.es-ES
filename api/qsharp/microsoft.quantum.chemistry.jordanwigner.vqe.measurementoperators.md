---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 204ae621b77559a894f0bce14e494824d58e4ad6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835397"
---
# <a name="measurementoperators-function"></a><span data-ttu-id="e0c99-102">MeasurementOperators función)</span><span class="sxs-lookup"><span data-stu-id="e0c99-102">MeasurementOperators function</span></span>

<span data-ttu-id="e0c99-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner. vqe](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="e0c99-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="e0c99-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e0c99-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="e0c99-105">Calcula todos los operadores de medida necesarios para calcular la expectativa de un término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="e0c99-105">Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.</span></span>

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="e0c99-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e0c99-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="e0c99-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e0c99-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e0c99-108">El número de qubits necesario para simular el sistema molecular.</span><span class="sxs-lookup"><span data-stu-id="e0c99-108">The number of qubits required to simulate the molecular system.</span></span>


### <a name="indices--int"></a><span data-ttu-id="e0c99-109">índices: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e0c99-109">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e0c99-110">Una matriz que contiene los índices de qubit a los que se aplica cada operador Pauli.</span><span class="sxs-lookup"><span data-stu-id="e0c99-110">An array containing the indices of the qubit each Pauli operator is applied to.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="e0c99-111">Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e0c99-111">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e0c99-112">Tipo del término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="e0c99-112">The type of the Jordan-Wigner term.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="e0c99-113">Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="e0c99-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="e0c99-114">Matriz de operadores de medida (cada uno de ellos es una matriz de Pauli).</span><span class="sxs-lookup"><span data-stu-id="e0c99-114">An array of measurement operators (each being an array of Pauli).</span></span>