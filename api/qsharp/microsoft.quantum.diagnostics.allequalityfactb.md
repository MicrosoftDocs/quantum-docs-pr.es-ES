---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 100aacccbfd5b45ac9f859cd89424b0ed4007f72
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727376"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="b5745-102">AllEqualityFactB función)</span><span class="sxs-lookup"><span data-stu-id="b5745-102">AllEqualityFactB function</span></span>

<span data-ttu-id="b5745-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b5745-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b5745-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b5745-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b5745-105">Valida que dos matrices de valores booleanos son iguales.</span><span class="sxs-lookup"><span data-stu-id="b5745-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b5745-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b5745-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="b5745-107">real: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b5745-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b5745-108">La matriz generada por un caso de prueba de interés.</span><span class="sxs-lookup"><span data-stu-id="b5745-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="b5745-109">se esperaba: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b5745-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b5745-110">La matriz que se espera de un caso de prueba de interés.</span><span class="sxs-lookup"><span data-stu-id="b5745-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="b5745-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b5745-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b5745-112">Un mensaje que se va a imprimir si las matrices no son iguales.</span><span class="sxs-lookup"><span data-stu-id="b5745-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b5745-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b5745-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

