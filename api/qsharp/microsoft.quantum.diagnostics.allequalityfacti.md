---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 92b57f49407d558e5f8d0365c168b7890f1f4981
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223891"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="98ca2-102">AllEqualityFactI función)</span><span class="sxs-lookup"><span data-stu-id="98ca2-102">AllEqualityFactI function</span></span>

<span data-ttu-id="98ca2-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="98ca2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="98ca2-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="98ca2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="98ca2-105">Valida que dos matrices de valores enteros son iguales.</span><span class="sxs-lookup"><span data-stu-id="98ca2-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="98ca2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="98ca2-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="98ca2-107">real: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="98ca2-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="98ca2-108">La matriz generada por un caso de prueba de interés.</span><span class="sxs-lookup"><span data-stu-id="98ca2-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="98ca2-109">se esperaba: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="98ca2-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="98ca2-110">La matriz que se espera de un caso de prueba de interés.</span><span class="sxs-lookup"><span data-stu-id="98ca2-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="98ca2-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="98ca2-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="98ca2-112">Un mensaje que se va a imprimir si las matrices no son iguales.</span><span class="sxs-lookup"><span data-stu-id="98ca2-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="98ca2-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="98ca2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

