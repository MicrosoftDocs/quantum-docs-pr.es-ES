---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: Operación ApplyToMostA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: eb793b3d6bc1f75a14e97420d36d0aea3038e0f5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850583"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="924fe-102">Operación ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="924fe-102">ApplyToMostA operation</span></span>

<span data-ttu-id="924fe-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="924fe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="924fe-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="924fe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="924fe-105">Aplica una operación a todo menos al último elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="924fe-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="924fe-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="924fe-106">Description</span></span>

<span data-ttu-id="924fe-107">Dada una operación `op` y una matriz de destinos `targets` , se aplica `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="924fe-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="924fe-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="924fe-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="924fe-109">OP: ' t [] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="924fe-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="924fe-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="924fe-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="924fe-111">destinos: ' t []</span><span class="sxs-lookup"><span data-stu-id="924fe-111">targets : 'T[]</span></span>

<span data-ttu-id="924fe-112">Matriz de destinos, de la que se aplicarán todos los, excepto el último `op` .</span><span class="sxs-lookup"><span data-stu-id="924fe-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="924fe-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="924fe-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="924fe-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="924fe-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="924fe-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="924fe-115">'T</span></span>

<span data-ttu-id="924fe-116">Tipo de entrada de la operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="924fe-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="924fe-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="924fe-117">See Also</span></span>

- [<span data-ttu-id="924fe-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="924fe-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="924fe-119">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="924fe-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="924fe-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="924fe-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)