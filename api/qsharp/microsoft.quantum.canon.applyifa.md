---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: Operación ApplyIfA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: 8bdca1bf286d564dfbb540bc9d63c035d2196f00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845034"
---
# <a name="applyifa-operation"></a><span data-ttu-id="013cb-102">Operación ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="013cb-102">ApplyIfA operation</span></span>

<span data-ttu-id="013cb-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="013cb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="013cb-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="013cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="013cb-105">Aplica una operación adjointable condicionada en un bit clásico.</span><span class="sxs-lookup"><span data-stu-id="013cb-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="013cb-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="013cb-106">Description</span></span>

<span data-ttu-id="013cb-107">Dada una operación `op` y un valor de bit `bit` , se aplica `op` a `target` si `bit` es `true` .</span><span class="sxs-lookup"><span data-stu-id="013cb-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="013cb-108">Si es `false` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="013cb-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="013cb-109">El sufijo `A` indica que la operación que se va a aplicar es adjointable.</span><span class="sxs-lookup"><span data-stu-id="013cb-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="013cb-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="013cb-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="013cb-111">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ</span><span class="sxs-lookup"><span data-stu-id="013cb-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="013cb-112">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="013cb-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="013cb-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="013cb-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="013cb-114">un valor booleano que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="013cb-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="013cb-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="013cb-115">target : 'T</span></span>

<span data-ttu-id="013cb-116">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="013cb-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="013cb-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="013cb-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="013cb-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="013cb-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="013cb-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="013cb-119">'T</span></span>

<span data-ttu-id="013cb-120">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="013cb-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="013cb-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="013cb-121">Example</span></span>

<span data-ttu-id="013cb-122">Lo siguiente prepara un registro de qubits en un estado de base de cálculo representado por una cadena de bits clásica dada como una matriz de `Bool` valores:</span><span class="sxs-lookup"><span data-stu-id="013cb-122">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="013cb-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="013cb-123">See Also</span></span>

- [<span data-ttu-id="013cb-124">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="013cb-124">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="013cb-125">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="013cb-125">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="013cb-126">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="013cb-126">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)