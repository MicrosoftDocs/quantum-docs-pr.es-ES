---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Operación ApplyControlledOnBitString
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 7a054511bacff574e6f7e889ace048c78886cf91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729676"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="d87f1-102">Operación ApplyControlledOnBitString</span><span class="sxs-lookup"><span data-stu-id="d87f1-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="d87f1-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d87f1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d87f1-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d87f1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d87f1-105">Aplica una operación de unitario en el registro de destino, controlada en un estado especificado por una máscara de bits determinada.</span><span class="sxs-lookup"><span data-stu-id="d87f1-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="d87f1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d87f1-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="d87f1-107">bits: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="d87f1-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="d87f1-108">Cadena de bits en la que se va a controlar la operación de unitario especificada.</span><span class="sxs-lookup"><span data-stu-id="d87f1-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="d87f1-109">Oracle: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="d87f1-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="d87f1-110">La operación unitario que se va a aplicar al registro de destino.</span><span class="sxs-lookup"><span data-stu-id="d87f1-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="d87f1-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d87f1-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d87f1-112">Un registro Quantum que controla la aplicación de `oracle` .</span><span class="sxs-lookup"><span data-stu-id="d87f1-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="d87f1-113">targetRegister: ' t</span><span class="sxs-lookup"><span data-stu-id="d87f1-113">targetRegister : 'T</span></span>

<span data-ttu-id="d87f1-114">Registro de destino que se va a pasar a `oracle` como entrada.</span><span class="sxs-lookup"><span data-stu-id="d87f1-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d87f1-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d87f1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d87f1-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="d87f1-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d87f1-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="d87f1-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="d87f1-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d87f1-118">Remarks</span></span>

<span data-ttu-id="d87f1-119">El patrón proporcionado por `bits` puede ser más corto que `controlRegister` , en cuyo caso se omiten los qubits de control adicionales (es decir, no se controlan en $ \ket {0} $ ni $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="d87f1-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="d87f1-120">Si `bits` es mayor que `controlRegister` , se genera un error.</span><span class="sxs-lookup"><span data-stu-id="d87f1-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="d87f1-121">Por ejemplo, `bits = [0,1,0,0,1]` significa que `oracle` se aplica si y solo si `controlRegister` está en el estado $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="d87f1-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>