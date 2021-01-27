---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: Operación ApplyToTail
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 077e6dedee68b0bd05a668387b22f8bec87a4041
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850436"
---
# <a name="applytotail-operation"></a><span data-ttu-id="a1db0-102">Operación ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="a1db0-102">ApplyToTail operation</span></span>

<span data-ttu-id="a1db0-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a1db0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a1db0-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a1db0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a1db0-105">Aplica una operación al último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="a1db0-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="a1db0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1db0-106">Description</span></span>

<span data-ttu-id="a1db0-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="a1db0-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="a1db0-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="a1db0-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="a1db0-109">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="a1db0-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a1db0-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="a1db0-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="a1db0-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="a1db0-111">targets : 'T[]</span></span>

<span data-ttu-id="a1db0-112">Matriz de destinos, de la que se aplicará el último `op` .</span><span class="sxs-lookup"><span data-stu-id="a1db0-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a1db0-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a1db0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a1db0-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="a1db0-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a1db0-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="a1db0-115">'T</span></span>

<span data-ttu-id="a1db0-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="a1db0-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="a1db0-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1db0-117">Example</span></span>

<span data-ttu-id="a1db0-118">Los siguientes fragmentos de código de Q # son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="a1db0-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToTail(H, register);
H(Tail(register));
```

## <a name="see-also"></a><span data-ttu-id="a1db0-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1db0-119">See Also</span></span>

- [<span data-ttu-id="a1db0-120">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="a1db0-120">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="a1db0-121">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="a1db0-121">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="a1db0-122">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="a1db0-122">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)