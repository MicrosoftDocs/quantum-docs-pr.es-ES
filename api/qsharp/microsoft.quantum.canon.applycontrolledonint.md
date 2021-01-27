---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Operación ApplyControlledOnInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 499a25104742b2d03886065baad4d535ea92e83b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845096"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="04ac7-102">Operación ApplyControlledOnInt</span><span class="sxs-lookup"><span data-stu-id="04ac7-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="04ac7-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="04ac7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="04ac7-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04ac7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04ac7-105">Aplica una operación de unitario en el registro de destino si el estado del registro de control corresponde a un entero positivo especificado.</span><span class="sxs-lookup"><span data-stu-id="04ac7-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="04ac7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="04ac7-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="04ac7-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="04ac7-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="04ac7-108">Entero no negativo en el que `oracle` se debe controlar la operación.</span><span class="sxs-lookup"><span data-stu-id="04ac7-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="04ac7-109">Oracle: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="04ac7-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="04ac7-110">Operación de unitario que se va a controlar.</span><span class="sxs-lookup"><span data-stu-id="04ac7-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="04ac7-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="04ac7-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="04ac7-112">Un registro Quantum que controla la aplicación de `oracle` .</span><span class="sxs-lookup"><span data-stu-id="04ac7-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="04ac7-113">targetRegister: ' t</span><span class="sxs-lookup"><span data-stu-id="04ac7-113">targetRegister : 'T</span></span>

<span data-ttu-id="04ac7-114">Registro en el que se va a aplicar `oracle` .</span><span class="sxs-lookup"><span data-stu-id="04ac7-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="04ac7-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="04ac7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="04ac7-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="04ac7-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="04ac7-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="04ac7-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="04ac7-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="04ac7-118">Remarks</span></span>

<span data-ttu-id="04ac7-119">El valor de `numberState` se interpreta utilizando una codificación Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="04ac7-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="04ac7-120">`numberState` debe ser como máximo $2 ^ \texttt{Length (controlRegister)}-$1.</span><span class="sxs-lookup"><span data-stu-id="04ac7-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="04ac7-121">Por ejemplo, `numberState = 537` significa que `oracle` se aplica si y solo si `controlRegister` está en el estado $ \ket {537} $.</span><span class="sxs-lookup"><span data-stu-id="04ac7-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>