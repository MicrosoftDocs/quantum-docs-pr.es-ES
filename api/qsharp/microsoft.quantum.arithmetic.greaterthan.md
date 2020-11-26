---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: Operación GreaterThan
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: 644d68affbdb508938f76de5025a1a463e7284e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223092"
---
# <a name="greaterthan-operation"></a><span data-ttu-id="b0efb-102">Operación GreaterThan</span><span class="sxs-lookup"><span data-stu-id="b0efb-102">GreaterThan operation</span></span>

<span data-ttu-id="b0efb-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b0efb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b0efb-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0efb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0efb-105">Aplica una comparación mayor que entre dos enteros codificados en registros de qubit, volteando un qubit de destino basándose en el resultado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="b0efb-105">Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.</span></span>

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b0efb-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0efb-106">Description</span></span>

<span data-ttu-id="b0efb-107">Lleva a cabo un valor estrictamente mayor que la comparación de dos enteros $x $ y $y $, codificados en qubit registra XS y calendario.</span><span class="sxs-lookup"><span data-stu-id="b0efb-107">Carries out a strictly greater than comparison of two integers $x$ and $y$, encoded in qubit registers xs and ys.</span></span> <span data-ttu-id="b0efb-108">Si $x > y $, se volteará el resultado qubit; de lo contrario, el resultado qubit mantendrá su estado.</span><span class="sxs-lookup"><span data-stu-id="b0efb-108">If $x > y$, then the result qubit will be flipped, otherwise the result qubit will retain its state.</span></span>

## <a name="input"></a><span data-ttu-id="b0efb-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="b0efb-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="b0efb-110">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b0efb-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b0efb-111">LittleEndian qubit registra el primer entero $x $.</span><span class="sxs-lookup"><span data-stu-id="b0efb-111">LittleEndian qubit register encoding the first integer $x$.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="b0efb-112">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b0efb-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b0efb-113">LittleEndian qubit registra el segundo entero $y $.</span><span class="sxs-lookup"><span data-stu-id="b0efb-113">LittleEndian qubit register encoding the second integer $y$.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="b0efb-114">resultado: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b0efb-114">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b0efb-115">Qubit único que se va a voltear si $x > y $.</span><span class="sxs-lookup"><span data-stu-id="b0efb-115">Single qubit that will be flipped if $x > y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b0efb-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0efb-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b0efb-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b0efb-117">Remarks</span></span>

<span data-ttu-id="b0efb-118">Utiliza el truco que $x-y = (x ' + y) ' $, donde ' denota el complemento de uno.</span><span class="sxs-lookup"><span data-stu-id="b0efb-118">Uses the trick that $x - y = (x'+y)'$, where ' denotes the one's complement.</span></span>

## <a name="references"></a><span data-ttu-id="b0efb-119">Referencias</span><span class="sxs-lookup"><span data-stu-id="b0efb-119">References</span></span>

- <span data-ttu-id="b0efb-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "un nuevo circuito de adición del transporte de onda de Quantum", 2004.</span><span class="sxs-lookup"><span data-stu-id="b0efb-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1

- <span data-ttu-id="b0efb-121">Thomas Haener, Martin Roetteler, KRYSTA M. Svore: "factoring Using 2N + 2 qubits con la multiplicación modular basada en Toffoli", 2016 https://arxiv.org/abs/1611.07995</span><span class="sxs-lookup"><span data-stu-id="b0efb-121">Thomas Haener, Martin Roetteler, Krysta M. Svore: "Factoring using 2n+2 qubits with Toffoli based modular multiplication", 2016 https://arxiv.org/abs/1611.07995</span></span>