---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204069"
---
# <a name="isnotzero-function"></a><span data-ttu-id="9b3fb-102">IsNotZero función)</span><span class="sxs-lookup"><span data-stu-id="9b3fb-102">IsNotZero function</span></span>

<span data-ttu-id="9b3fb-103">Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="9b3fb-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="9b3fb-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="9b3fb-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="9b3fb-105">Comprueba si un `Double` número no es aproximadamente cero.</span><span class="sxs-lookup"><span data-stu-id="9b3fb-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="9b3fb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9b3fb-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="9b3fb-107">número: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9b3fb-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9b3fb-108">Número que se va a comprobar</span><span class="sxs-lookup"><span data-stu-id="9b3fb-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="9b3fb-109">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9b3fb-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9b3fb-110">Devuelve true si `number` tiene un valor absoluto mayor que `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="9b3fb-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>