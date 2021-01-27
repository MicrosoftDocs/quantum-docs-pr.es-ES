---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839599"
---
# <a name="isnotzero-function"></a><span data-ttu-id="89e13-102">IsNotZero función)</span><span class="sxs-lookup"><span data-stu-id="89e13-102">IsNotZero function</span></span>

<span data-ttu-id="89e13-103">Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="89e13-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="89e13-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="89e13-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="89e13-105">Comprueba si un `Double` número no es aproximadamente cero.</span><span class="sxs-lookup"><span data-stu-id="89e13-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="89e13-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="89e13-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="89e13-107">número: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="89e13-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="89e13-108">Número que se va a comprobar</span><span class="sxs-lookup"><span data-stu-id="89e13-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="89e13-109">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="89e13-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="89e13-110">Devuelve true si `number` tiene un valor absoluto mayor que `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="89e13-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>