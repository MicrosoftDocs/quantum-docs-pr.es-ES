---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Función Fact
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853321"
---
# <a name="fact-function"></a><span data-ttu-id="1c36a-102">Función Fact</span><span class="sxs-lookup"><span data-stu-id="1c36a-102">Fact function</span></span>

<span data-ttu-id="1c36a-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1c36a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1c36a-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1c36a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1c36a-105">Declara que una condición clásica es true.</span><span class="sxs-lookup"><span data-stu-id="1c36a-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="1c36a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1c36a-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="1c36a-107">real: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1c36a-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1c36a-108">Condición que se va a declarar.</span><span class="sxs-lookup"><span data-stu-id="1c36a-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="1c36a-109">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1c36a-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1c36a-110">Cadena de mensaje de error que se va a imprimir en caso de que la condición clásica sea falsa.</span><span class="sxs-lookup"><span data-stu-id="1c36a-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1c36a-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c36a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="1c36a-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c36a-112">Example</span></span>

<span data-ttu-id="1c36a-113">Se producirá un error en el siguiente fragmento de código de Q #:</span><span class="sxs-lookup"><span data-stu-id="1c36a-113">The following Q# snippet will fail:</span></span>

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a><span data-ttu-id="1c36a-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1c36a-114">See Also</span></span>

- [<span data-ttu-id="1c36a-115">Microsoft. Quantum. Diagnostics. contradicción</span><span class="sxs-lookup"><span data-stu-id="1c36a-115">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)