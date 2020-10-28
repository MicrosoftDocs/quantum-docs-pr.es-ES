---
uid: Microsoft.Quantum.Measurement.MResetY
title: Operación MResetY
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 48aba7317d0e48d089ec6c4814efdee51bb8e2ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733796"
---
# <a name="mresety-operation"></a><span data-ttu-id="c290c-102">Operación MResetY</span><span class="sxs-lookup"><span data-stu-id="c290c-102">MResetY operation</span></span>

<span data-ttu-id="c290c-103">Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="c290c-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="c290c-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c290c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c290c-105">Mide un qubit único en la base y y lo restablece en un estado inicial fijo después de la medición.</span><span class="sxs-lookup"><span data-stu-id="c290c-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="c290c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c290c-106">Description</span></span>

<span data-ttu-id="c290c-107">Realiza una medición de un solo qubit en el $Y $-Basis y garantiza que el qubit se devuelve a $ \ket {0} $ después de la medida.</span><span class="sxs-lookup"><span data-stu-id="c290c-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="c290c-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="c290c-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="c290c-109">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c290c-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c290c-110">Un único qubit que se va a medir.</span><span class="sxs-lookup"><span data-stu-id="c290c-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="c290c-111">Salida: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="c290c-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="c290c-112">El resultado de medir `target` en Pauli $Y $.</span><span class="sxs-lookup"><span data-stu-id="c290c-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>