---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 9ccd212010ae557de5ca4ab2a38d4724c5c29aa8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727371"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="fd2d4-102">AllEqualityFactI función)</span><span class="sxs-lookup"><span data-stu-id="fd2d4-102">AllEqualityFactI function</span></span>

<span data-ttu-id="fd2d4-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="fd2d4-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="fd2d4-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fd2d4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fd2d4-105">Valida que dos matrices de valores enteros son iguales.</span><span class="sxs-lookup"><span data-stu-id="fd2d4-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="fd2d4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fd2d4-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="fd2d4-107">real: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fd2d4-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fd2d4-108">La matriz generada por un caso de prueba de interés.</span><span class="sxs-lookup"><span data-stu-id="fd2d4-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="fd2d4-109">se esperaba: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fd2d4-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fd2d4-110">La matriz que se espera de un caso de prueba de interés.</span><span class="sxs-lookup"><span data-stu-id="fd2d4-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="fd2d4-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="fd2d4-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="fd2d4-112">Un mensaje que se va a imprimir si las matrices no son iguales.</span><span class="sxs-lookup"><span data-stu-id="fd2d4-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fd2d4-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fd2d4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

