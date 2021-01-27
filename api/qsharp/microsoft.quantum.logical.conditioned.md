---
uid: Microsoft.Quantum.Logical.Conditioned
title: Función condicionada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817299"
---
# <a name="conditioned-function"></a><span data-ttu-id="2496e-102">Función condicionada</span><span class="sxs-lookup"><span data-stu-id="2496e-102">Conditioned function</span></span>

<span data-ttu-id="2496e-103">Espacio de nombres: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2496e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2496e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2496e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2496e-105">Devuelve uno de dos valores, dependiendo del valor de una condición booleana.</span><span class="sxs-lookup"><span data-stu-id="2496e-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="2496e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2496e-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="2496e-107">condición: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2496e-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2496e-108">Condición usada para controlar qué entrada se devuelve.</span><span class="sxs-lookup"><span data-stu-id="2496e-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="2496e-109">ifTrue: ' t</span><span class="sxs-lookup"><span data-stu-id="2496e-109">ifTrue : 'T</span></span>

<span data-ttu-id="2496e-110">Valor que se va a devolver cuando `condition` sea `true` .</span><span class="sxs-lookup"><span data-stu-id="2496e-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="2496e-111">ifFalse: ' t</span><span class="sxs-lookup"><span data-stu-id="2496e-111">ifFalse : 'T</span></span>

<span data-ttu-id="2496e-112">Valor que se va a devolver cuando `condition` sea `false` .</span><span class="sxs-lookup"><span data-stu-id="2496e-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="2496e-113">Salida: ' t</span><span class="sxs-lookup"><span data-stu-id="2496e-113">Output : 'T</span></span>

<span data-ttu-id="2496e-114">`ifTrue` Si `condition` es `true` , y `ifFalse` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="2496e-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2496e-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="2496e-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2496e-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="2496e-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="2496e-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2496e-117">Remarks</span></span>

<span data-ttu-id="2496e-118">A diferencia del `?|` operador, esta función no cortocircuita, de modo que ambas entradas se evalúen por completo.</span><span class="sxs-lookup"><span data-stu-id="2496e-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="2496e-119">Hasta un comportamiento de cortocircuito, los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="2496e-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```