---
uid: Microsoft.Quantum.Arrays.Merged
title: Función combinada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: da15a36f8f057cdc15062c96070ec21becc4794a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730109"
---
# <a name="merged-function"></a><span data-ttu-id="117c7-102">Función combinada</span><span class="sxs-lookup"><span data-stu-id="117c7-102">Merged function</span></span>

<span data-ttu-id="117c7-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="117c7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="117c7-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="117c7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="117c7-105">Dadas dos matrices ordenadas, devuelve una matriz única que contiene los elementos de ambos en orden.</span><span class="sxs-lookup"><span data-stu-id="117c7-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="117c7-106">Utilizado internamente por orden de combinación.</span><span class="sxs-lookup"><span data-stu-id="117c7-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="117c7-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="117c7-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="117c7-108">comparación: (' t, ')-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="117c7-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="117c7-109">Left: ' t []</span><span class="sxs-lookup"><span data-stu-id="117c7-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="117c7-110">Right: ' t []</span><span class="sxs-lookup"><span data-stu-id="117c7-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="117c7-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="117c7-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="117c7-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="117c7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="117c7-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="117c7-113">'T</span></span>

