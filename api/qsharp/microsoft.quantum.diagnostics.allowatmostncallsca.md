---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: Operación AllowAtMostNCallsCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: bb6ba2615b571b0d9d056b93f8e36d2dec0c4a21
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853534"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="974ed-102">Operación AllowAtMostNCallsCA</span><span class="sxs-lookup"><span data-stu-id="974ed-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="974ed-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="974ed-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="974ed-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="974ed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="974ed-105">Entre una llamada a esta operación y su método contiguo, se declara que se llama a una operación determinada a lo sumo un número determinado de veces.</span><span class="sxs-lookup"><span data-stu-id="974ed-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="974ed-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="974ed-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="974ed-107">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="974ed-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="974ed-108">Número máximo de veces que `op` se puede llamar a.</span><span class="sxs-lookup"><span data-stu-id="974ed-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="974ed-109">OP: ' TInput => ' TOutput es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="974ed-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="974ed-110">Operación cuyas llamadas se van a restringir.</span><span class="sxs-lookup"><span data-stu-id="974ed-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="974ed-111">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="974ed-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="974ed-112">Mensaje que se va a mostrar cuando se produzca un error.</span><span class="sxs-lookup"><span data-stu-id="974ed-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="974ed-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="974ed-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="974ed-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="974ed-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="974ed-115">' TInput</span><span class="sxs-lookup"><span data-stu-id="974ed-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="974ed-116">' TOutput '</span><span class="sxs-lookup"><span data-stu-id="974ed-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="974ed-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="974ed-117">Example</span></span>

<span data-ttu-id="974ed-118">El siguiente fragmento de código producirá un error cuando se ejecute en equipos que admiten este diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="974ed-118">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
using (register = Qubit[4]) {
    within {
        AllowAtMostNCallsCA(3, H, "Too many calls to H.");
    } apply {
        // Fails since this calls H four times, rather than the
        // allowed maximum of three.
        ApplyToEach(H, register);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="974ed-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="974ed-119">Remarks</span></span>

<span data-ttu-id="974ed-120">Esta operación se puede reemplazar por una no operativa en destinos que no la admitan.</span><span class="sxs-lookup"><span data-stu-id="974ed-120">This operation may be replaced by a no-op on targets which do not support it.</span></span>