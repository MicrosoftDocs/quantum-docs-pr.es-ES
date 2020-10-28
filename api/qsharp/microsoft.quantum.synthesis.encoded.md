---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Función codificada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 6b9d21969ee90f3928b65a1c97a5b0f15157e381
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733908"
---
# <a name="encoded-function"></a><span data-ttu-id="f9365-102">Función codificada</span><span class="sxs-lookup"><span data-stu-id="f9365-102">Encoded function</span></span>

<span data-ttu-id="f9365-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f9365-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f9365-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f9365-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f9365-105">Codificar la tabla de verdad en la {1,-1} codificación</span><span class="sxs-lookup"><span data-stu-id="f9365-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="f9365-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f9365-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="f9365-107">tabla: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="f9365-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="f9365-108">Tabla de verdad como matriz de valores veracidad</span><span class="sxs-lookup"><span data-stu-id="f9365-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="f9365-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f9365-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f9365-110">Tabla de verdad como una matriz de {1,-1} enteros</span><span class="sxs-lookup"><span data-stu-id="f9365-110">Truth table as array of {1,-1} integers</span></span>