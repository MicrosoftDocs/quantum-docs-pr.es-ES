---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: Operación ApplyIfCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b9d5e2c6868dc7b876917abf28f68bb5d0d0f2f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845005"
---
# <a name="applyifca-operation"></a><span data-ttu-id="601b7-102">Operación ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="601b7-102">ApplyIfCA operation</span></span>

<span data-ttu-id="601b7-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="601b7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="601b7-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="601b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="601b7-105">Aplica una operación de unitario condicionada en un bit clásico.</span><span class="sxs-lookup"><span data-stu-id="601b7-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="601b7-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="601b7-106">Description</span></span>

<span data-ttu-id="601b7-107">Dada una operación `op` y un valor de bit `bit` , se aplica `op` a `target` si `bit` es `true` .</span><span class="sxs-lookup"><span data-stu-id="601b7-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="601b7-108">Si es `false` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="601b7-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="601b7-109">El sufijo `CA` indica que la operación que se va a aplicar es la unitario (controlable y adjointable).</span><span class="sxs-lookup"><span data-stu-id="601b7-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="601b7-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="601b7-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="601b7-111">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="601b7-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="601b7-112">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="601b7-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="601b7-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="601b7-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="601b7-114">un valor booleano que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="601b7-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="601b7-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="601b7-115">target : 'T</span></span>

<span data-ttu-id="601b7-116">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="601b7-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="601b7-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="601b7-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="601b7-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="601b7-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="601b7-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="601b7-119">'T</span></span>

<span data-ttu-id="601b7-120">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="601b7-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="601b7-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="601b7-121">Example</span></span>

<span data-ttu-id="601b7-122">Lo siguiente prepara un registro de qubits en un estado de base de cálculo representado por una cadena de bits clásica dada como una matriz de `Bool` valores:</span><span class="sxs-lookup"><span data-stu-id="601b7-122">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="601b7-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="601b7-123">See Also</span></span>

- [<span data-ttu-id="601b7-124">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="601b7-124">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="601b7-125">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="601b7-125">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="601b7-126">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="601b7-126">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)