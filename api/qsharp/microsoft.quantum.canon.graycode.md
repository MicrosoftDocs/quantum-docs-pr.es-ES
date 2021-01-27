---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840493"
---
# <a name="graycode-function"></a><span data-ttu-id="3351f-102">GrayCode función)</span><span class="sxs-lookup"><span data-stu-id="3351f-102">GrayCode function</span></span>

<span data-ttu-id="3351f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3351f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3351f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3351f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3351f-105">Crea secuencias de código gris</span><span class="sxs-lookup"><span data-stu-id="3351f-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="3351f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3351f-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="3351f-107">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3351f-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3351f-108">Número de bits</span><span class="sxs-lookup"><span data-stu-id="3351f-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="3351f-109">Salida: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="3351f-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="3351f-110">Matriz de tuplas.</span><span class="sxs-lookup"><span data-stu-id="3351f-110">Array of tuples.</span></span> <span data-ttu-id="3351f-111">El primer valor de la tupla es el valor del segundo valor de la secuencia GrayCode en la tupla es Position para cambiar en el valor actual para obtener el siguiente.</span><span class="sxs-lookup"><span data-stu-id="3351f-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>

## <a name="example"></a><span data-ttu-id="3351f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3351f-112">Example</span></span>

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```