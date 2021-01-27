---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 176170cc972ca67b812b84f79cf97ba5418be9b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840797"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="06f35-102">ControlledOnBitString función)</span><span class="sxs-lookup"><span data-stu-id="06f35-102">ControlledOnBitString function</span></span>

<span data-ttu-id="06f35-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="06f35-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="06f35-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="06f35-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="06f35-105">Devuelve una operación de unitario que aplica un Oracle en el registro de destino si el estado del registro de control corresponde a una máscara de bits especificada.</span><span class="sxs-lookup"><span data-stu-id="06f35-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="06f35-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="06f35-106">Description</span></span>

<span data-ttu-id="06f35-107">La salida de esta función es una operación que se puede representar mediante una transformación unitario $U $ como \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{otherwise} \end{Cases}, \end{align} donde $V $ es una transformación de unitario que representa la acción de la `oracle` operación.</span><span class="sxs-lookup"><span data-stu-id="06f35-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="06f35-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="06f35-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="06f35-109">bits: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="06f35-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="06f35-110">Cadena de bits en la que se va a controlar la operación de unitario especificada.</span><span class="sxs-lookup"><span data-stu-id="06f35-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="06f35-111">Oracle: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="06f35-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="06f35-112">La operación unitario que se va a aplicar al registro de destino.</span><span class="sxs-lookup"><span data-stu-id="06f35-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="06f35-113">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], ' t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="06f35-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="06f35-114">Operación de unitario que se aplica `oracle` en el registro de destino si el estado del registro de control corresponde a la máscara de bits `bits` .</span><span class="sxs-lookup"><span data-stu-id="06f35-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="06f35-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="06f35-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="06f35-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="06f35-116">'T</span></span>



## <a name="example"></a><span data-ttu-id="06f35-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06f35-117">Example</span></span>

<span data-ttu-id="06f35-118">Los siguientes fragmentos de código son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="06f35-118">The following code snippets are equivalent:</span></span>

```qsharp
(ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
```

<span data-ttu-id="06f35-119">y</span><span class="sxs-lookup"><span data-stu-id="06f35-119">and</span></span>

```qsharp
within {
    ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
} apply {
    Controlled oracle(controlRegister, targetRegister);
}
```

<span data-ttu-id="06f35-120">En el código siguiente se prepara un estado $ \frac {1} {2} (\ket {00} -\ket {01} + \ket {10} + \ket {11} ) $:</span><span class="sxs-lookup"><span data-stu-id="06f35-120">The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:</span></span>

```qsharp
using (register = Qubit[2]) {
    ApplyToEach(H, register);
    (ControlledOnBitString([false], Z))(register[0..0], register[1]);
}
```

## <a name="remarks"></a><span data-ttu-id="06f35-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="06f35-121">Remarks</span></span>

<span data-ttu-id="06f35-122">El patrón proporcionado por `bits` puede ser más corto que `controlRegister` , en cuyo caso se omiten los qubits de control adicionales (es decir, no se controlan en $ \ket {0} $ ni $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="06f35-122">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="06f35-123">Si `bits` es mayor que `controlRegister` , se genera un error.</span><span class="sxs-lookup"><span data-stu-id="06f35-123">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="06f35-124">Dada una matriz booleana `bits` y una operación unitario `oracle` , la salida de esta función es una operación que realiza los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="06f35-124">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="06f35-125">Aplique una `X` operación a cada qubit del registro de control que se corresponda con `false` el elemento de `bits` ;</span><span class="sxs-lookup"><span data-stu-id="06f35-125">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="06f35-126">se aplican `Controlled oracle` a los registros de control y de destino;</span><span class="sxs-lookup"><span data-stu-id="06f35-126">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="06f35-127">Aplique una `X` operación a cada qubit del registro de control que se corresponda con el `false` elemento de de `bits` nuevo para devolver el registro de control al estado original.</span><span class="sxs-lookup"><span data-stu-id="06f35-127">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="06f35-128">La salida del `Controlled` functor es un caso especial de `ControlledOnBitString` donde `bits` es igual a `[true, ..., true]` .</span><span class="sxs-lookup"><span data-stu-id="06f35-128">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>