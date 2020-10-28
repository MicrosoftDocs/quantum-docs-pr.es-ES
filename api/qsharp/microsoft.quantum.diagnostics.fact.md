---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Función Fact
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 6a08703f68f9f38f2224fe4c6a4d255b00756908
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727208"
---
# <a name="fact-function"></a><span data-ttu-id="de376-102">Función Fact</span><span class="sxs-lookup"><span data-stu-id="de376-102">Fact function</span></span>

<span data-ttu-id="de376-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="de376-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="de376-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="de376-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="de376-105">Declara que una condición clásica es true.</span><span class="sxs-lookup"><span data-stu-id="de376-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="de376-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="de376-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="de376-107">real: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="de376-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="de376-108">Condición que se va a declarar.</span><span class="sxs-lookup"><span data-stu-id="de376-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="de376-109">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="de376-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="de376-110">Cadena de mensaje de error que se va a imprimir en caso de que la condición clásica sea falsa.</span><span class="sxs-lookup"><span data-stu-id="de376-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="de376-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="de376-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="de376-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de376-112">See Also</span></span>

- [<span data-ttu-id="de376-113">Microsoft. Quantum. Diagnostics. contradicción</span><span class="sxs-lookup"><span data-stu-id="de376-113">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)