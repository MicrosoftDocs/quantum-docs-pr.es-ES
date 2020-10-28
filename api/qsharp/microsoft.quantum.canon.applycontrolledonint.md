---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Operación ApplyControlledOnInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729669"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="7299f-102">Operación ApplyControlledOnInt</span><span class="sxs-lookup"><span data-stu-id="7299f-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="7299f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7299f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7299f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7299f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7299f-105">Aplica una operación de unitario en el registro de destino si el estado del registro de control corresponde a un entero positivo especificado.</span><span class="sxs-lookup"><span data-stu-id="7299f-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="7299f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7299f-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="7299f-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7299f-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7299f-108">Entero no negativo en el que `oracle` se debe controlar la operación.</span><span class="sxs-lookup"><span data-stu-id="7299f-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="7299f-109">Oracle: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="7299f-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="7299f-110">Operación de unitario que se va a controlar.</span><span class="sxs-lookup"><span data-stu-id="7299f-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="7299f-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7299f-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7299f-112">Un registro Quantum que controla la aplicación de `oracle` .</span><span class="sxs-lookup"><span data-stu-id="7299f-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="7299f-113">targetRegister: ' t</span><span class="sxs-lookup"><span data-stu-id="7299f-113">targetRegister : 'T</span></span>

<span data-ttu-id="7299f-114">Registro en el que se va a aplicar `oracle` .</span><span class="sxs-lookup"><span data-stu-id="7299f-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7299f-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7299f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7299f-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="7299f-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7299f-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="7299f-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="7299f-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7299f-118">Remarks</span></span>

<span data-ttu-id="7299f-119">El valor de `numberState` se interpreta utilizando una codificación Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="7299f-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="7299f-120">`numberState` debe ser como máximo $2 ^ \texttt{Length (controlRegister)}-$1.</span><span class="sxs-lookup"><span data-stu-id="7299f-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="7299f-121">Por ejemplo, `numberState = 537` significa que `oracle` se aplica si y solo si `controlRegister` está en el estado $ \ket {537} $.</span><span class="sxs-lookup"><span data-stu-id="7299f-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>