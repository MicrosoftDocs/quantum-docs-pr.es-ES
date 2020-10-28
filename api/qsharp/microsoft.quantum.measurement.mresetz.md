---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Operación MResetZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 9f084b03504deea9fcf25e4c797c4bde3c97a995
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726507"
---
# <a name="mresetz-operation"></a><span data-ttu-id="556bc-102">Operación MResetZ</span><span class="sxs-lookup"><span data-stu-id="556bc-102">MResetZ operation</span></span>

<span data-ttu-id="556bc-103">Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="556bc-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="556bc-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="556bc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="556bc-105">Mide un único qubit en la Z y lo restablece a un estado inicial fijo después de la medición.</span><span class="sxs-lookup"><span data-stu-id="556bc-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="556bc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="556bc-106">Description</span></span>

<span data-ttu-id="556bc-107">Realiza una medición de un solo qubit en el $Z $-Basis y garantiza que el qubit se devuelve a $ \ket {0} $ después de la medida.</span><span class="sxs-lookup"><span data-stu-id="556bc-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="556bc-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="556bc-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="556bc-109">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="556bc-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="556bc-110">Un único qubit que se va a medir.</span><span class="sxs-lookup"><span data-stu-id="556bc-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="556bc-111">Salida: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="556bc-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="556bc-112">El resultado de medir `target` en Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="556bc-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>