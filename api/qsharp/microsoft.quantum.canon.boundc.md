---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 02e9b6a9676cdd1996d3a2413b2a6383e3a4e90e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207588"
---
# <a name="boundc-function"></a><span data-ttu-id="0e804-102">BoundC función)</span><span class="sxs-lookup"><span data-stu-id="0e804-102">BoundC function</span></span>

<span data-ttu-id="0e804-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0e804-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0e804-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0e804-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0e804-105">Dada una matriz de operaciones que actúan en una sola entrada, genera una nueva operación que realiza cada operación dada en secuencia.</span><span class="sxs-lookup"><span data-stu-id="0e804-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="0e804-106">El modificador `C` indica que todas las operaciones de la matriz se pueden controlar.</span><span class="sxs-lookup"><span data-stu-id="0e804-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="0e804-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="0e804-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="0e804-108">operaciones: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL []</span><span class="sxs-lookup"><span data-stu-id="0e804-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="0e804-109">Secuencia de operaciones que se va a realizar en una entrada determinada.</span><span class="sxs-lookup"><span data-stu-id="0e804-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="0e804-110">Salida: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="0e804-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="0e804-111">Nueva operación que realiza cada operación dada en secuencia en su entrada.</span><span class="sxs-lookup"><span data-stu-id="0e804-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0e804-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="0e804-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0e804-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="0e804-113">'T</span></span>

<span data-ttu-id="0e804-114">Destino en el que actúa cada una de las operaciones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="0e804-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e804-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e804-115">See Also</span></span>

- [<span data-ttu-id="0e804-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="0e804-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)