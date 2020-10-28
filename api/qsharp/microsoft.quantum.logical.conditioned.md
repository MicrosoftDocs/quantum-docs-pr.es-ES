---
uid: Microsoft.Quantum.Logical.Conditioned
title: Función condicionada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: 8aabe8b018129ddee3b934c207d0a62e59fb6f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731293"
---
# <a name="conditioned-function"></a><span data-ttu-id="53621-102">Función condicionada</span><span class="sxs-lookup"><span data-stu-id="53621-102">Conditioned function</span></span>

<span data-ttu-id="53621-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="53621-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="53621-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53621-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53621-105">Devuelve uno de dos valores, dependiendo del valor de una condición booleana.</span><span class="sxs-lookup"><span data-stu-id="53621-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="53621-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="53621-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="53621-107">condición: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="53621-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="53621-108">Condición usada para controlar qué entrada se devuelve.</span><span class="sxs-lookup"><span data-stu-id="53621-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="53621-109">ifTrue: ' t</span><span class="sxs-lookup"><span data-stu-id="53621-109">ifTrue : 'T</span></span>

<span data-ttu-id="53621-110">Valor que se va a devolver cuando `condition` sea `true` .</span><span class="sxs-lookup"><span data-stu-id="53621-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="53621-111">ifFalse: ' t</span><span class="sxs-lookup"><span data-stu-id="53621-111">ifFalse : 'T</span></span>

<span data-ttu-id="53621-112">Valor que se va a devolver cuando `condition` sea `false` .</span><span class="sxs-lookup"><span data-stu-id="53621-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="53621-113">Salida: ' t</span><span class="sxs-lookup"><span data-stu-id="53621-113">Output : 'T</span></span>

<span data-ttu-id="53621-114">`ifTrue` Si `condition` es `true` , y `ifFalse` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="53621-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="53621-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="53621-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="53621-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="53621-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="53621-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="53621-117">Remarks</span></span>

<span data-ttu-id="53621-118">A diferencia del `?|` operador, esta función no cortocircuita, de modo que ambas entradas se evalúen por completo.</span><span class="sxs-lookup"><span data-stu-id="53621-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="53621-119">Hasta un comportamiento de cortocircuito, los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="53621-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```