---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Contradicción (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727286"
---
# <a name="contradiction-function"></a><span data-ttu-id="7a3eb-102">Contradicción (función)</span><span class="sxs-lookup"><span data-stu-id="7a3eb-102">Contradiction function</span></span>

<span data-ttu-id="7a3eb-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7a3eb-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7a3eb-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7a3eb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7a3eb-105">Declara que una condición clásica es falsa.</span><span class="sxs-lookup"><span data-stu-id="7a3eb-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="7a3eb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7a3eb-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="7a3eb-107">real: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7a3eb-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7a3eb-108">Condición que se va a declarar.</span><span class="sxs-lookup"><span data-stu-id="7a3eb-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="7a3eb-109">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="7a3eb-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="7a3eb-110">Cadena de mensaje de error que se va a imprimir en caso de que la condición clásica sea true.</span><span class="sxs-lookup"><span data-stu-id="7a3eb-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7a3eb-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a3eb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="7a3eb-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a3eb-112">See Also</span></span>

- [<span data-ttu-id="7a3eb-113">Microsoft. Quantum. Diagnostics. Fact</span><span class="sxs-lookup"><span data-stu-id="7a3eb-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)