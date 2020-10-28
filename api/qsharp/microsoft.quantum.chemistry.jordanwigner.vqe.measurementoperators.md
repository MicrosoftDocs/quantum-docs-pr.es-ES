---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727634"
---
# <a name="measurementoperators-function"></a><span data-ttu-id="420cc-102">MeasurementOperators función)</span><span class="sxs-lookup"><span data-stu-id="420cc-102">MeasurementOperators function</span></span>

<span data-ttu-id="420cc-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner. vqe](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="420cc-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="420cc-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="420cc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="420cc-105">Calcula todos los operadores de medida necesarios para calcular la expectativa de un término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="420cc-105">Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.</span></span>

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="420cc-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="420cc-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="420cc-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="420cc-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="420cc-108">El número de qubits necesario para simular el sistema molecular.</span><span class="sxs-lookup"><span data-stu-id="420cc-108">The number of qubits required to simulate the molecular system.</span></span>


### <a name="indices--int"></a><span data-ttu-id="420cc-109">índices: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="420cc-109">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="420cc-110">Una matriz que contiene los índices de qubit a los que se aplica cada operador Pauli.</span><span class="sxs-lookup"><span data-stu-id="420cc-110">An array containing the indices of the qubit each Pauli operator is applied to.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="420cc-111">Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="420cc-111">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="420cc-112">Tipo del término Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="420cc-112">The type of the Jordan-Wigner term.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="420cc-113">Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="420cc-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="420cc-114">Matriz de operadores de medida (cada uno de ellos es una matriz de Pauli).</span><span class="sxs-lookup"><span data-stu-id="420cc-114">An array of measurement operators (each being an array of Pauli).</span></span>