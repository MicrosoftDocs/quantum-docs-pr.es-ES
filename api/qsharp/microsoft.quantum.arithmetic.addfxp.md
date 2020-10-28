---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: Operación AddFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: cf1f1379b7e1c32aefb0fccb55f4d13c95c78d8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731901"
---
# <a name="addfxp-operation"></a><span data-ttu-id="feb17-102">Operación AddFxP</span><span class="sxs-lookup"><span data-stu-id="feb17-102">AddFxP operation</span></span>

<span data-ttu-id="feb17-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="feb17-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="feb17-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="feb17-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="feb17-105">Agrega dos números de punto fijo almacenados en registros de Quantum.</span><span class="sxs-lookup"><span data-stu-id="feb17-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="description"></a><span data-ttu-id="feb17-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="feb17-106">Description</span></span>

<span data-ttu-id="feb17-107">Dados dos registros de punto fijo, respectivamente en los Estados $ \ket{f_1} $ y $ \ket{f_2} $, realiza la operación $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $.</span><span class="sxs-lookup"><span data-stu-id="feb17-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="feb17-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="feb17-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="feb17-109">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="feb17-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="feb17-110">Primer número de punto fijo</span><span class="sxs-lookup"><span data-stu-id="feb17-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="feb17-111">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="feb17-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="feb17-112">Segundo número de punto fijo, se actualizará para que contenga la suma de las dos entradas.</span><span class="sxs-lookup"><span data-stu-id="feb17-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="feb17-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="feb17-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="feb17-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="feb17-114">Remarks</span></span>

<span data-ttu-id="feb17-115">La implementación actual requiere que los dos números de punto fijo tengan la misma posición de punto contando entre el bit menos significativo, es decir, $n _i $ y $p _i $ deben ser iguales.</span><span class="sxs-lookup"><span data-stu-id="feb17-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>