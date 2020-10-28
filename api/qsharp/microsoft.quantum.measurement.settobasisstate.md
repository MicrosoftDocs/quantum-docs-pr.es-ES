---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Operación SetToBasisState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733604"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="eef58-102">Operación SetToBasisState</span><span class="sxs-lookup"><span data-stu-id="eef58-102">SetToBasisState operation</span></span>

<span data-ttu-id="eef58-103">Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="eef58-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="eef58-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eef58-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eef58-105">Establece un qubit en un estado de base de cálculo determinado midiendo el qubit y aplicando un volteo de bits si es necesario.</span><span class="sxs-lookup"><span data-stu-id="eef58-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="eef58-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="eef58-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="eef58-107">deseado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="eef58-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="eef58-108">El estado de base en el que debe establecerse el valor de qubit.</span><span class="sxs-lookup"><span data-stu-id="eef58-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="eef58-109">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="eef58-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="eef58-110">Qubit cuyo estado se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="eef58-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eef58-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eef58-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="eef58-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eef58-112">Remarks</span></span>

<span data-ttu-id="eef58-113">Como invariable de esta operación, al llamar a `M(q)` inmediatamente después de, `SetToBasisState(result, q)` se devolverá `result` .</span><span class="sxs-lookup"><span data-stu-id="eef58-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>