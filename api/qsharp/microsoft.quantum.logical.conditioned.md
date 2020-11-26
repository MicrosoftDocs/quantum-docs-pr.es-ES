---
uid: Microsoft.Quantum.Logical.Conditioned
title: Función condicionada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: c0f55d4db95ad1f0d2b7f291cbc6ba8ae704cb81
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198493"
---
# <a name="conditioned-function"></a><span data-ttu-id="32941-102">Función condicionada</span><span class="sxs-lookup"><span data-stu-id="32941-102">Conditioned function</span></span>

<span data-ttu-id="32941-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="32941-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="32941-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32941-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32941-105">Devuelve uno de dos valores, dependiendo del valor de una condición booleana.</span><span class="sxs-lookup"><span data-stu-id="32941-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="32941-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="32941-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="32941-107">condición: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="32941-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="32941-108">Condición usada para controlar qué entrada se devuelve.</span><span class="sxs-lookup"><span data-stu-id="32941-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="32941-109">ifTrue: ' t</span><span class="sxs-lookup"><span data-stu-id="32941-109">ifTrue : 'T</span></span>

<span data-ttu-id="32941-110">Valor que se va a devolver cuando `condition` sea `true` .</span><span class="sxs-lookup"><span data-stu-id="32941-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="32941-111">ifFalse: ' t</span><span class="sxs-lookup"><span data-stu-id="32941-111">ifFalse : 'T</span></span>

<span data-ttu-id="32941-112">Valor que se va a devolver cuando `condition` sea `false` .</span><span class="sxs-lookup"><span data-stu-id="32941-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="32941-113">Salida: ' t</span><span class="sxs-lookup"><span data-stu-id="32941-113">Output : 'T</span></span>

<span data-ttu-id="32941-114">`ifTrue` Si `condition` es `true` , y `ifFalse` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="32941-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="32941-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="32941-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="32941-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="32941-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="32941-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="32941-117">Remarks</span></span>

<span data-ttu-id="32941-118">A diferencia del `?|` operador, esta función no cortocircuita, de modo que ambas entradas se evalúen por completo.</span><span class="sxs-lookup"><span data-stu-id="32941-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="32941-119">Hasta un comportamiento de cortocircuito, los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="32941-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```