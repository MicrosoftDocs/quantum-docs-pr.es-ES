---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: a7043b9c670f79e270180c583fef56b70c1a3bcb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830902"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="0b80c-102">AllEqualityFactI función)</span><span class="sxs-lookup"><span data-stu-id="0b80c-102">AllEqualityFactI function</span></span>

<span data-ttu-id="0b80c-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0b80c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0b80c-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b80c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b80c-105">Valida que dos matrices de valores enteros son iguales.</span><span class="sxs-lookup"><span data-stu-id="0b80c-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="0b80c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0b80c-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="0b80c-107">real: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0b80c-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0b80c-108">La matriz generada por un caso de prueba de interés.</span><span class="sxs-lookup"><span data-stu-id="0b80c-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="0b80c-109">se esperaba: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0b80c-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0b80c-110">La matriz que se espera de un caso de prueba de interés.</span><span class="sxs-lookup"><span data-stu-id="0b80c-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="0b80c-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="0b80c-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="0b80c-112">Un mensaje que se va a imprimir si las matrices no son iguales.</span><span class="sxs-lookup"><span data-stu-id="0b80c-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0b80c-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0b80c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

