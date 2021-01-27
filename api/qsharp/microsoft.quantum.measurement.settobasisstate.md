---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Operación SetToBasisState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: dfa054360a5e82b7ae6ec5a6d52e7d5fe566f42e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854619"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="6d51b-102">Operación SetToBasisState</span><span class="sxs-lookup"><span data-stu-id="6d51b-102">SetToBasisState operation</span></span>

<span data-ttu-id="6d51b-103">Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="6d51b-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="6d51b-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6d51b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6d51b-105">Establece un qubit en un estado de base de cálculo determinado midiendo el qubit y aplicando un volteo de bits si es necesario.</span><span class="sxs-lookup"><span data-stu-id="6d51b-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="6d51b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6d51b-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="6d51b-107">deseado: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="6d51b-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="6d51b-108">El estado de base en el que debe establecerse el valor de qubit.</span><span class="sxs-lookup"><span data-stu-id="6d51b-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6d51b-109">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6d51b-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6d51b-110">Qubit cuyo estado se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="6d51b-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6d51b-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6d51b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6d51b-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6d51b-112">Remarks</span></span>

<span data-ttu-id="6d51b-113">Como invariable de esta operación, al llamar a `M(q)` inmediatamente después de, `SetToBasisState(result, q)` se devolverá `result` .</span><span class="sxs-lookup"><span data-stu-id="6d51b-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>