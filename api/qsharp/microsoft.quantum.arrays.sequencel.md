---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Función sequencel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 7e3c5c31428f9be152e28afbe478a3d15eb0a56c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850987"
---
# <a name="sequencel-function"></a><span data-ttu-id="dbfab-102">Función sequencel</span><span class="sxs-lookup"><span data-stu-id="dbfab-102">SequenceL function</span></span>

<span data-ttu-id="dbfab-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="dbfab-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="dbfab-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dbfab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dbfab-105">Obtiene una matriz de enteros en un intervalo determinado.</span><span class="sxs-lookup"><span data-stu-id="dbfab-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="dbfab-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="dbfab-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="dbfab-107">From: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="dbfab-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="dbfab-108">Índice inicial inclusivo del intervalo.</span><span class="sxs-lookup"><span data-stu-id="dbfab-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="dbfab-109">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="dbfab-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="dbfab-110">Índice final inclusivo del intervalo que no es menor que `from` .</span><span class="sxs-lookup"><span data-stu-id="dbfab-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="dbfab-111">Salida: [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="dbfab-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="dbfab-112">Una matriz que contiene la secuencia de números `from` , `from + 1` ,... `to` .</span><span class="sxs-lookup"><span data-stu-id="dbfab-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="example"></a><span data-ttu-id="dbfab-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dbfab-113">Example</span></span>

```qsharp
let arr1 = SequenceL(0L, 3L); // [0L, 1L, 2L, 3L]
let arr2 = SequenceL(23L, 29L); // [23L, 24L, 25L, 26L, 27L, 28L, 29L]
let arr3 = SequenceL(-5L, -2L); // [-5L, -4L, -3L, -2L]
```

## <a name="remarks"></a><span data-ttu-id="dbfab-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dbfab-114">Remarks</span></span>

<span data-ttu-id="dbfab-115">La diferencia entre `from` y `to` debe ajustarse a un `Int` valor.</span><span class="sxs-lookup"><span data-stu-id="dbfab-115">The difference between `from` and `to` must fit into an `Int` value.</span></span>