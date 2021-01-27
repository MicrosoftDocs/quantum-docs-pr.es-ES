---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: Operación ApplyToRest
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: f18536a056935220feedc4ea50531c5def61d650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850511"
---
# <a name="applytorest-operation"></a><span data-ttu-id="58e07-102">Operación ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="58e07-102">ApplyToRest operation</span></span>

<span data-ttu-id="58e07-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="58e07-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="58e07-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="58e07-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="58e07-105">Aplica una operación a todo menos al primer elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="58e07-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="58e07-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="58e07-106">Description</span></span>

<span data-ttu-id="58e07-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="58e07-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="58e07-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="58e07-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="58e07-109">OP: ' t [] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="58e07-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="58e07-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="58e07-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="58e07-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="58e07-111">targets : 'T[]</span></span>

<span data-ttu-id="58e07-112">Matriz de destinos, de la que se aplicarán todos los, excepto el primero `op` .</span><span class="sxs-lookup"><span data-stu-id="58e07-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="58e07-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="58e07-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="58e07-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="58e07-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="58e07-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="58e07-115">'T</span></span>

<span data-ttu-id="58e07-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="58e07-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="58e07-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="58e07-117">Example</span></span>

<span data-ttu-id="58e07-118">Los siguientes fragmentos de código de Q # son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="58e07-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToRest(ApplyCNOTChain, register);
ApplyCNOTChain(Rest(register));
```

## <a name="see-also"></a><span data-ttu-id="58e07-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="58e07-119">See Also</span></span>

- [<span data-ttu-id="58e07-120">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="58e07-120">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="58e07-121">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="58e07-121">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="58e07-122">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="58e07-122">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)