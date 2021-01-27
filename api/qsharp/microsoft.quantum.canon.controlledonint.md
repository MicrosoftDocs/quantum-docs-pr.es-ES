---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 6c7f46c44f2a2427f702e463195f26660cb4fca1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840787"
---
# <a name="controlledonint-function"></a><span data-ttu-id="775bf-102">ControlledOnInt función)</span><span class="sxs-lookup"><span data-stu-id="775bf-102">ControlledOnInt function</span></span>

<span data-ttu-id="775bf-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="775bf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="775bf-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="775bf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="775bf-105">Devuelve un operador unitario que aplica un Oracle en el registro de destino si el estado del registro de control corresponde a un entero positivo especificado.</span><span class="sxs-lookup"><span data-stu-id="775bf-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="775bf-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="775bf-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="775bf-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="775bf-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="775bf-108">Entero positivo.</span><span class="sxs-lookup"><span data-stu-id="775bf-108">Positive integer.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="775bf-109">Oracle: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="775bf-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="775bf-110">Operador unitario.</span><span class="sxs-lookup"><span data-stu-id="775bf-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="775bf-111">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], ' t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="775bf-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="775bf-112">Operador unitario que se aplica `oracle` en el registro de destino si el estado del registro de control corresponde al estado del número `numberState` .</span><span class="sxs-lookup"><span data-stu-id="775bf-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="775bf-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="775bf-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="775bf-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="775bf-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="775bf-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="775bf-115">Remarks</span></span>

<span data-ttu-id="775bf-116">El valor de `numberState` se interpreta utilizando una codificación Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="775bf-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>