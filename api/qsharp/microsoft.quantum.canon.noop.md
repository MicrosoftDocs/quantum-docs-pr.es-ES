---
uid: Microsoft.Quantum.Canon.NoOp
title: Operación NoOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 987e39577c3b736418234431ed7a915ae461f763
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728523"
---
# <a name="noop-operation"></a><span data-ttu-id="5ee33-102">Operación NoOp</span><span class="sxs-lookup"><span data-stu-id="5ee33-102">NoOp operation</span></span>

<span data-ttu-id="5ee33-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5ee33-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5ee33-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5ee33-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5ee33-105">Realiza la operación de identidad (no OP) en un argumento.</span><span class="sxs-lookup"><span data-stu-id="5ee33-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="5ee33-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ee33-106">Description</span></span>

<span data-ttu-id="5ee33-107">Esta operación toma un valor de cualquier tipo y no hace nada.</span><span class="sxs-lookup"><span data-stu-id="5ee33-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="5ee33-108">Esto puede ser útil siempre que se espera una entrada de un tipo de operación, pero no se debe realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5ee33-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="5ee33-109">Por ejemplo, si un síndrome de corrección de errores determinado indica que no se ha producido ningún error, `NoOp<Qubit[]>` puede ser el procedimiento de recuperación correcto.</span><span class="sxs-lookup"><span data-stu-id="5ee33-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="5ee33-110">Del mismo modo, si una operación espera un procedimiento de preparación de estado como entrada, `NoOp<Qubit[]>` se puede usar para preparar el estado $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="5ee33-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="5ee33-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="5ee33-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="5ee33-112">entrada: ' t</span><span class="sxs-lookup"><span data-stu-id="5ee33-112">input : 'T</span></span>

<span data-ttu-id="5ee33-113">Valor que se va a omitir.</span><span class="sxs-lookup"><span data-stu-id="5ee33-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5ee33-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5ee33-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5ee33-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="5ee33-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5ee33-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="5ee33-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="5ee33-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5ee33-117">Remarks</span></span>

<span data-ttu-id="5ee33-118">En casi todos los casos, el parámetro de tipo de `NoOp` debe especificarse explícitamente.</span><span class="sxs-lookup"><span data-stu-id="5ee33-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="5ee33-119">Por ejemplo, `NoOp<Qubit>` es idéntico a <xref:microsoft.quantum.intrinsic.i> .</span><span class="sxs-lookup"><span data-stu-id="5ee33-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ee33-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5ee33-120">See Also</span></span>

- [<span data-ttu-id="5ee33-121">Microsoft. Quantum. Intrinsic. I</span><span class="sxs-lookup"><span data-stu-id="5ee33-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)