---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Operación MResetZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 494f11c8129175ddd84c6539f5e9df1a758e8a82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194141"
---
# <a name="mresetz-operation"></a><span data-ttu-id="f54ce-102">Operación MResetZ</span><span class="sxs-lookup"><span data-stu-id="f54ce-102">MResetZ operation</span></span>

<span data-ttu-id="f54ce-103">Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="f54ce-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="f54ce-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f54ce-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f54ce-105">Mide un único qubit en la Z y lo restablece a un estado inicial fijo después de la medición.</span><span class="sxs-lookup"><span data-stu-id="f54ce-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="f54ce-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f54ce-106">Description</span></span>

<span data-ttu-id="f54ce-107">Realiza una medición de un solo qubit en el $Z $-Basis y garantiza que el qubit se devuelve a $ \ket {0} $ después de la medida.</span><span class="sxs-lookup"><span data-stu-id="f54ce-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="f54ce-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="f54ce-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="f54ce-109">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f54ce-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f54ce-110">Un único qubit que se va a medir.</span><span class="sxs-lookup"><span data-stu-id="f54ce-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="f54ce-111">Salida: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="f54ce-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="f54ce-112">El resultado de medir `target` en Pauli $Z $.</span><span class="sxs-lookup"><span data-stu-id="f54ce-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>