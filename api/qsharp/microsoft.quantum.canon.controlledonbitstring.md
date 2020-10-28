---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: ca5a6e116eff187060f7a160e42836b170f0362d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728817"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="e1db7-102">ControlledOnBitString función)</span><span class="sxs-lookup"><span data-stu-id="e1db7-102">ControlledOnBitString function</span></span>

<span data-ttu-id="e1db7-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e1db7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e1db7-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1db7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e1db7-105">Devuelve una operación de unitario que aplica un Oracle en el registro de destino si el estado del registro de control corresponde a una máscara de bits especificada.</span><span class="sxs-lookup"><span data-stu-id="e1db7-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="e1db7-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1db7-106">Description</span></span>

<span data-ttu-id="e1db7-107">La salida de esta función es una operación que se puede representar mediante una transformación unitario $U $ como \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{otherwise} \end{Cases}, \end{align} donde $V $ es una transformación de unitario que representa la acción de la `oracle` operación.</span><span class="sxs-lookup"><span data-stu-id="e1db7-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="e1db7-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="e1db7-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="e1db7-109">bits: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="e1db7-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="e1db7-110">Cadena de bits en la que se va a controlar la operación de unitario especificada.</span><span class="sxs-lookup"><span data-stu-id="e1db7-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="e1db7-111">Oracle: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="e1db7-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="e1db7-112">La operación unitario que se va a aplicar al registro de destino.</span><span class="sxs-lookup"><span data-stu-id="e1db7-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit-adj--ctl"></a><span data-ttu-id="e1db7-113">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], ' no) => [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL + CTL</span><span class="sxs-lookup"><span data-stu-id="e1db7-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="e1db7-114">Operación de unitario que se aplica `oracle` en el registro de destino si el estado del registro de control corresponde a la máscara de bits `bits` .</span><span class="sxs-lookup"><span data-stu-id="e1db7-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e1db7-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="e1db7-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e1db7-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="e1db7-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="e1db7-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e1db7-117">Remarks</span></span>

<span data-ttu-id="e1db7-118">El patrón proporcionado por `bits` puede ser más corto que `controlRegister` , en cuyo caso se omiten los qubits de control adicionales (es decir, no se controlan en $ \ket {0} $ ni $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="e1db7-118">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="e1db7-119">Si `bits` es mayor que `controlRegister` , se genera un error.</span><span class="sxs-lookup"><span data-stu-id="e1db7-119">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="e1db7-120">Dada una matriz booleana `bits` y una operación unitario `oracle` , la salida de esta función es una operación que realiza los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e1db7-120">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="e1db7-121">Aplique una `X` operación a cada qubit del registro de control que se corresponda con `false` el elemento de `bits` ;</span><span class="sxs-lookup"><span data-stu-id="e1db7-121">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="e1db7-122">se aplican `Controlled oracle` a los registros de control y de destino;</span><span class="sxs-lookup"><span data-stu-id="e1db7-122">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="e1db7-123">Aplique una `X` operación a cada qubit del registro de control que se corresponda con el `false` elemento de de `bits` nuevo para devolver el registro de control al estado original.</span><span class="sxs-lookup"><span data-stu-id="e1db7-123">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="e1db7-124">La salida del `Controlled` functor es un caso especial de `ControlledOnBitString` donde `bits` es igual a `[true, ..., true]` .</span><span class="sxs-lookup"><span data-stu-id="e1db7-124">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>