---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3cc5c00d9c7295106901149e06571ef1963d1323
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207265"
---
# <a name="controlledonint-function"></a><span data-ttu-id="99aa1-102">ControlledOnInt función)</span><span class="sxs-lookup"><span data-stu-id="99aa1-102">ControlledOnInt function</span></span>

<span data-ttu-id="99aa1-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="99aa1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="99aa1-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="99aa1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="99aa1-105">Devuelve un operador unitario que aplica un Oracle en el registro de destino si el estado del registro de control corresponde a un entero positivo especificado.</span><span class="sxs-lookup"><span data-stu-id="99aa1-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="99aa1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="99aa1-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="99aa1-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="99aa1-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="99aa1-108">Entero positivo.</span><span class="sxs-lookup"><span data-stu-id="99aa1-108">Positive integer.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="99aa1-109">Oracle: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="99aa1-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="99aa1-110">Operador unitario.</span><span class="sxs-lookup"><span data-stu-id="99aa1-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="99aa1-111">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], ' t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="99aa1-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="99aa1-112">Operador unitario que se aplica `oracle` en el registro de destino si el estado del registro de control corresponde al estado del número `numberState` .</span><span class="sxs-lookup"><span data-stu-id="99aa1-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="99aa1-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="99aa1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="99aa1-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="99aa1-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="99aa1-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="99aa1-115">Remarks</span></span>

<span data-ttu-id="99aa1-116">El valor de `numberState` se interpreta utilizando una codificación Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="99aa1-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>