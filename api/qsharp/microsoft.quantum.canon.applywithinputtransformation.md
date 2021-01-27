---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: Operación ApplyWithInputTransformation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: d4589acbe9f9dc6c6ab665582ed663dbc193edbb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850370"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="90f0b-102">Operación ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="90f0b-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="90f0b-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="90f0b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="90f0b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90f0b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90f0b-105">Dada una operación que acepta alguna entrada, una función que devuelve una salida compatible con esa operación y una entrada a esa función, aplica la operación utilizando la función para transformar la entrada a un formato esperado por la operación.</span><span class="sxs-lookup"><span data-stu-id="90f0b-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="90f0b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="90f0b-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="90f0b-107">FN: ' U-> ' t</span><span class="sxs-lookup"><span data-stu-id="90f0b-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="90f0b-108">Función que transforma la entrada especificada en un formato esperado por la operación.</span><span class="sxs-lookup"><span data-stu-id="90f0b-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="90f0b-109">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="90f0b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="90f0b-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="90f0b-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="90f0b-111">entrada: ' U</span><span class="sxs-lookup"><span data-stu-id="90f0b-111">input : 'U</span></span>

<span data-ttu-id="90f0b-112">Una entrada a la función.</span><span class="sxs-lookup"><span data-stu-id="90f0b-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="90f0b-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="90f0b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="90f0b-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="90f0b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="90f0b-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="90f0b-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="90f0b-116">' U</span><span class="sxs-lookup"><span data-stu-id="90f0b-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="90f0b-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="90f0b-117">Example</span></span>

<span data-ttu-id="90f0b-118">La siguiente llamada utiliza @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" para aplicar una operación diseñada para @"Microsoft.Quantum.Arithmetic.BigEndian" entradas a una entrada de tipo @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="90f0b-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="90f0b-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="90f0b-119">See Also</span></span>

- [<span data-ttu-id="90f0b-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="90f0b-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="90f0b-121">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="90f0b-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="90f0b-122">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="90f0b-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="90f0b-123">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="90f0b-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)