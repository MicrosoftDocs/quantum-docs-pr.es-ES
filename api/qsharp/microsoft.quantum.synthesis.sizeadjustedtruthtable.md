---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: c53ac3f2c46bca955847fc7b380337e3910390ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202930"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="f56aa-102">SizeAdjustedTruthTable función)</span><span class="sxs-lookup"><span data-stu-id="f56aa-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="f56aa-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f56aa-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f56aa-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f56aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f56aa-105">Ajusta la tabla de verdad de la matriz de valores booleanos según el número de variables.</span><span class="sxs-lookup"><span data-stu-id="f56aa-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="f56aa-106">Se devuelve una nueva matriz de longitud `2^numVars` , que posiblemente requiere extender `table` el tamaño de `false` las entradas o truncarla en `2^numVars` elementos.</span><span class="sxs-lookup"><span data-stu-id="f56aa-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="f56aa-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="f56aa-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="f56aa-108">tabla: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="f56aa-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="f56aa-109">Tabla de verdad como matriz de valores veracidad</span><span class="sxs-lookup"><span data-stu-id="f56aa-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="f56aa-110">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f56aa-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f56aa-111">Número de variables</span><span class="sxs-lookup"><span data-stu-id="f56aa-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="f56aa-112">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="f56aa-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="f56aa-113">Tabla de veracidad ajustada de tamaño</span><span class="sxs-lookup"><span data-stu-id="f56aa-113">Size adjusted truth table</span></span>