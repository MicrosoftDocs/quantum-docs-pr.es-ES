---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Operación ApplyIf
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: 109a5c4748d183f199e420b4b1aef687613d220c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841879"
---
# <a name="applyif-operation"></a><span data-ttu-id="59bb5-102">Operación ApplyIf</span><span class="sxs-lookup"><span data-stu-id="59bb5-102">ApplyIf operation</span></span>

<span data-ttu-id="59bb5-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="59bb5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="59bb5-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59bb5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59bb5-105">Aplica una operación condicionada en un bit clásico.</span><span class="sxs-lookup"><span data-stu-id="59bb5-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="59bb5-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="59bb5-106">Description</span></span>

<span data-ttu-id="59bb5-107">Dada una operación `op` y un valor de bit `bit` , se aplica `op` a `target` si `bit` es `true` .</span><span class="sxs-lookup"><span data-stu-id="59bb5-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="59bb5-108">Si es `false` , no sucede nada con `target` .</span><span class="sxs-lookup"><span data-stu-id="59bb5-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="59bb5-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="59bb5-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="59bb5-110">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="59bb5-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="59bb5-111">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="59bb5-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="59bb5-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="59bb5-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="59bb5-113">un valor booleano que controla si se aplica o no la operación.</span><span class="sxs-lookup"><span data-stu-id="59bb5-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="59bb5-114">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="59bb5-114">target : 'T</span></span>

<span data-ttu-id="59bb5-115">Entrada a la que se aplica la operación.</span><span class="sxs-lookup"><span data-stu-id="59bb5-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="59bb5-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="59bb5-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="59bb5-117">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="59bb5-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="59bb5-118">Traslada</span><span class="sxs-lookup"><span data-stu-id="59bb5-118">'T</span></span>

<span data-ttu-id="59bb5-119">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="59bb5-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="59bb5-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="59bb5-120">Example</span></span>

<span data-ttu-id="59bb5-121">Lo siguiente prepara un registro de qubits en un estado de base de cálculo representado por una cadena de bits clásica dada como una matriz de `Bool` valores:</span><span class="sxs-lookup"><span data-stu-id="59bb5-121">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="59bb5-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59bb5-122">See Also</span></span>

- [<span data-ttu-id="59bb5-123">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="59bb5-123">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="59bb5-124">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="59bb5-124">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="59bb5-125">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="59bb5-125">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)