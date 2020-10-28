---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728805"
---
# <a name="controlledonint-function"></a><span data-ttu-id="6a633-102">ControlledOnInt función)</span><span class="sxs-lookup"><span data-stu-id="6a633-102">ControlledOnInt function</span></span>

<span data-ttu-id="6a633-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6a633-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6a633-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6a633-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6a633-105">Devuelve un operador unitario que aplica un Oracle en el registro de destino si el estado del registro de control corresponde a un entero positivo especificado.</span><span class="sxs-lookup"><span data-stu-id="6a633-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="6a633-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6a633-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="6a633-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6a633-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6a633-108">Entero positivo.</span><span class="sxs-lookup"><span data-stu-id="6a633-108">Positive integer.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="6a633-109">Oracle: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="6a633-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="6a633-110">Operador unitario.</span><span class="sxs-lookup"><span data-stu-id="6a633-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit-adj--ctl"></a><span data-ttu-id="6a633-111">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], ' no) => [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL + CTL</span><span class="sxs-lookup"><span data-stu-id="6a633-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="6a633-112">Operador unitario que se aplica `oracle` en el registro de destino si el estado del registro de control corresponde al estado del número `numberState` .</span><span class="sxs-lookup"><span data-stu-id="6a633-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6a633-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="6a633-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6a633-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="6a633-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="6a633-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6a633-115">Remarks</span></span>

<span data-ttu-id="6a633-116">El valor de `numberState` se interpreta utilizando una codificación Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="6a633-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>