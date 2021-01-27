---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: Operación AddFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 60b7cad3d0bd8800e67830ca921f8e2d705b8f39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843869"
---
# <a name="addfxp-operation"></a><span data-ttu-id="06490-102">Operación AddFxP</span><span class="sxs-lookup"><span data-stu-id="06490-102">AddFxP operation</span></span>

<span data-ttu-id="06490-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="06490-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="06490-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="06490-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="06490-105">Agrega dos números de punto fijo almacenados en registros de Quantum.</span><span class="sxs-lookup"><span data-stu-id="06490-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="06490-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="06490-106">Description</span></span>

<span data-ttu-id="06490-107">Dados dos registros de punto fijo, respectivamente en los Estados $ \ket{f_1} $ y $ \ket{f_2} $, realiza la operación $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $.</span><span class="sxs-lookup"><span data-stu-id="06490-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="06490-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="06490-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="06490-109">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="06490-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="06490-110">Primer número de punto fijo</span><span class="sxs-lookup"><span data-stu-id="06490-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="06490-111">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="06490-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="06490-112">Segundo número de punto fijo, se actualizará para que contenga la suma de las dos entradas.</span><span class="sxs-lookup"><span data-stu-id="06490-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="06490-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="06490-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="06490-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="06490-114">Remarks</span></span>

<span data-ttu-id="06490-115">La implementación actual requiere que los dos números de punto fijo tengan la misma posición de punto contando entre el bit menos significativo, es decir, $n _i $ y $p _i $ deben ser iguales.</span><span class="sxs-lookup"><span data-stu-id="06490-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>