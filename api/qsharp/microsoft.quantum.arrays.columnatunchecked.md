---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 06fce23bbf7142ee0e0b0ed3f2c0578676f2097b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221596"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="a3653-102">ColumnAtUnchecked función)</span><span class="sxs-lookup"><span data-stu-id="a3653-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="a3653-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a3653-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a3653-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a3653-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a3653-105">Esta función no comprueba la forma de matriz</span><span class="sxs-lookup"><span data-stu-id="a3653-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="a3653-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3653-106">Description</span></span>

<span data-ttu-id="a3653-107">Esta función se puede usar en otras funciones multidimensionales, que ya comprueban la matriz de entrada para una forma rectangular válida.</span><span class="sxs-lookup"><span data-stu-id="a3653-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="a3653-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="a3653-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="a3653-109">columna: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a3653-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="a3653-110">matriz: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="a3653-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="a3653-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="a3653-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a3653-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="a3653-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a3653-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="a3653-113">'T</span></span>

