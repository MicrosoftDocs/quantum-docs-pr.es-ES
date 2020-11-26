---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 79dcf65956ba9436fb6fdd452f22f35d4852d6f8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213708"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="83a16-102">AllEqualityFactB función)</span><span class="sxs-lookup"><span data-stu-id="83a16-102">AllEqualityFactB function</span></span>

<span data-ttu-id="83a16-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="83a16-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="83a16-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="83a16-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="83a16-105">Valida que dos matrices de valores booleanos son iguales.</span><span class="sxs-lookup"><span data-stu-id="83a16-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="83a16-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="83a16-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="83a16-107">real: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="83a16-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="83a16-108">La matriz generada por un caso de prueba de interés.</span><span class="sxs-lookup"><span data-stu-id="83a16-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="83a16-109">se esperaba: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="83a16-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="83a16-110">La matriz que se espera de un caso de prueba de interés.</span><span class="sxs-lookup"><span data-stu-id="83a16-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="83a16-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="83a16-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="83a16-112">Un mensaje que se va a imprimir si las matrices no son iguales.</span><span class="sxs-lookup"><span data-stu-id="83a16-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="83a16-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="83a16-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

