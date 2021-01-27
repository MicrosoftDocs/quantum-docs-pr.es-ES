---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 8d69aa119c25a0f64743fec36c00ecdef2450c44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855313"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="879c9-102">SizeAdjustedTruthTable función)</span><span class="sxs-lookup"><span data-stu-id="879c9-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="879c9-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="879c9-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="879c9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="879c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="879c9-105">Ajusta la tabla de verdad de la matriz de valores booleanos según el número de variables.</span><span class="sxs-lookup"><span data-stu-id="879c9-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="879c9-106">Se devuelve una nueva matriz de longitud `2^numVars` , que posiblemente requiere extender `table` el tamaño de `false` las entradas o truncarla en `2^numVars` elementos.</span><span class="sxs-lookup"><span data-stu-id="879c9-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="879c9-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="879c9-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="879c9-108">tabla: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="879c9-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="879c9-109">Tabla de verdad como matriz de valores veracidad</span><span class="sxs-lookup"><span data-stu-id="879c9-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="879c9-110">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="879c9-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="879c9-111">Número de variables</span><span class="sxs-lookup"><span data-stu-id="879c9-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="879c9-112">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="879c9-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="879c9-113">Tabla de veracidad ajustada de tamaño</span><span class="sxs-lookup"><span data-stu-id="879c9-113">Size adjusted truth table</span></span>