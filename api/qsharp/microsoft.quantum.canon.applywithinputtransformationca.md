---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: Operación ApplyWithInputTransformationCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: b31ed1b3da0d5467588f4cb2e4368e68f0dbe9d5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841111"
---
# <a name="applywithinputtransformationca-operation"></a><span data-ttu-id="4f6fd-102">Operación ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="4f6fd-102">ApplyWithInputTransformationCA operation</span></span>

<span data-ttu-id="4f6fd-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4f6fd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4f6fd-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f6fd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f6fd-105">Dada una operación que acepta alguna entrada, una función que devuelve una salida compatible con esa operación y una entrada a esa función, aplica la operación utilizando la función para transformar la entrada a un formato esperado por la operación.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4f6fd-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4f6fd-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="4f6fd-107">FN: ' U-> ' t</span><span class="sxs-lookup"><span data-stu-id="4f6fd-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="4f6fd-108">Función que transforma la entrada especificada en un formato esperado por la operación.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="4f6fd-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="4f6fd-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="4f6fd-110">Operación que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="4f6fd-111">entrada: ' U</span><span class="sxs-lookup"><span data-stu-id="4f6fd-111">input : 'U</span></span>

<span data-ttu-id="4f6fd-112">Una entrada a la función.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4f6fd-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4f6fd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4f6fd-114">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="4f6fd-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4f6fd-115">Traslada</span><span class="sxs-lookup"><span data-stu-id="4f6fd-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="4f6fd-116">' U</span><span class="sxs-lookup"><span data-stu-id="4f6fd-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="4f6fd-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f6fd-117">Example</span></span>

<span data-ttu-id="4f6fd-118">La siguiente llamada utiliza @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" para aplicar una operación diseñada para @"Microsoft.Quantum.Arithmetic.BigEndian" entradas a una entrada de tipo @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="4f6fd-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="4f6fd-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f6fd-119">See Also</span></span>

- [<span data-ttu-id="4f6fd-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="4f6fd-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="4f6fd-121">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="4f6fd-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="4f6fd-122">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="4f6fd-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="4f6fd-123">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="4f6fd-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)