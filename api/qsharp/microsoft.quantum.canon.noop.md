---
uid: Microsoft.Quantum.Canon.NoOp
title: Operación NoOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 35b6b62cab35f941f04b150dcca763457ddaa084
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205973"
---
# <a name="noop-operation"></a><span data-ttu-id="fa840-102">Operación NoOp</span><span class="sxs-lookup"><span data-stu-id="fa840-102">NoOp operation</span></span>

<span data-ttu-id="fa840-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fa840-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fa840-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="fa840-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fa840-105">Realiza la operación de identidad (no OP) en un argumento.</span><span class="sxs-lookup"><span data-stu-id="fa840-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="fa840-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa840-106">Description</span></span>

<span data-ttu-id="fa840-107">Esta operación toma un valor de cualquier tipo y no hace nada.</span><span class="sxs-lookup"><span data-stu-id="fa840-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="fa840-108">Esto puede ser útil siempre que se espera una entrada de un tipo de operación, pero no se debe realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="fa840-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="fa840-109">Por ejemplo, si un síndrome de corrección de errores determinado indica que no se ha producido ningún error, `NoOp<Qubit[]>` puede ser el procedimiento de recuperación correcto.</span><span class="sxs-lookup"><span data-stu-id="fa840-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="fa840-110">Del mismo modo, si una operación espera un procedimiento de preparación de estado como entrada, `NoOp<Qubit[]>` se puede usar para preparar el estado $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="fa840-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="fa840-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="fa840-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="fa840-112">entrada: ' t</span><span class="sxs-lookup"><span data-stu-id="fa840-112">input : 'T</span></span>

<span data-ttu-id="fa840-113">Valor que se va a omitir.</span><span class="sxs-lookup"><span data-stu-id="fa840-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fa840-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fa840-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fa840-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="fa840-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fa840-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="fa840-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="fa840-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fa840-117">Remarks</span></span>

<span data-ttu-id="fa840-118">En casi todos los casos, el parámetro de tipo de `NoOp` debe especificarse explícitamente.</span><span class="sxs-lookup"><span data-stu-id="fa840-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="fa840-119">Por ejemplo, `NoOp<Qubit>` es idéntico a <xref:microsoft.quantum.intrinsic.i> .</span><span class="sxs-lookup"><span data-stu-id="fa840-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa840-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa840-120">See Also</span></span>

- [<span data-ttu-id="fa840-121">Microsoft. Quantum. Intrinsic. I</span><span class="sxs-lookup"><span data-stu-id="fa840-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)