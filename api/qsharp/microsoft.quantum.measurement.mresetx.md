---
uid: Microsoft.Quantum.Measurement.MResetX
title: Operación MResetX
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 44459e681daf1d28ce7d45f91ad59059babe5716
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853755"
---
# <a name="mresetx-operation"></a><span data-ttu-id="16906-102">Operación MResetX</span><span class="sxs-lookup"><span data-stu-id="16906-102">MResetX operation</span></span>

<span data-ttu-id="16906-103">Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="16906-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="16906-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="16906-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="16906-105">Mide un único qubit en X y lo restablece a un estado inicial fijo después de la medición.</span><span class="sxs-lookup"><span data-stu-id="16906-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="16906-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="16906-106">Description</span></span>

<span data-ttu-id="16906-107">Realiza una medición de un solo qubit en el $X $-Basis y garantiza que el qubit se devuelve a $ \ket {0} $ después de la medida.</span><span class="sxs-lookup"><span data-stu-id="16906-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="16906-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="16906-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="16906-109">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="16906-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="16906-110">Un único qubit que se va a medir.</span><span class="sxs-lookup"><span data-stu-id="16906-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="16906-111">Salida: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="16906-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="16906-112">El resultado de medir `target` en Pauli $X $.</span><span class="sxs-lookup"><span data-stu-id="16906-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>