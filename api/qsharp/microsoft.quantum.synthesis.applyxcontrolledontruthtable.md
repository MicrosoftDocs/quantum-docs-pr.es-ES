---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: Operación ApplyXControlledOnTruthTable
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 6e956038f7cd15db7348ff830da8bc9eae53aa61
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855556"
---
# <a name="applyxcontrolledontruthtable-operation"></a><span data-ttu-id="dd309-102">Operación ApplyXControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="dd309-102">ApplyXControlledOnTruthTable operation</span></span>

<span data-ttu-id="dd309-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="dd309-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="dd309-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd309-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd309-105">Aplica la @"microsoft.quantum.intrinsic.x" operación en `target` , si la función booleana se `func` evalúa como true para la asignación clásica en `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="dd309-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="dd309-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd309-106">Description</span></span>

<span data-ttu-id="dd309-107">La operación implementa la operación unitario \begin{align} U\ket {x} \ les {y} = \ket{x}\ket{y \oplus f (x)} \end{align} donde $x $ y $y $ representan `controlRegister` y `target` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="dd309-107">The operation implements the unitary operation \begin{align} U\ket{x}\ket{y} = \ket{x}\ket{y \oplus f(x)} \end{align} where $x$ and $y$ represent `controlRegister` and `target`, respectively.</span></span>

<span data-ttu-id="dd309-108">La función booleana $f $ se representa como una tabla de verdad en términos de un entero grande.</span><span class="sxs-lookup"><span data-stu-id="dd309-108">The Boolean function $f$ is represented as a truth table in terms of a big integer.</span></span>
<span data-ttu-id="dd309-109">Por ejemplo, la función mayoritario en tres entradas se representa mediante bitstring `11101000` , donde el bit más significativo `1` corresponde a la asignación de entrada `(1, 1, 1)` y el bit menos significativo `0` corresponde a la asignación de entrada `(0, 0, 0)` .</span><span class="sxs-lookup"><span data-stu-id="dd309-109">For example, the majority function on three inputs is represented by the bitstring `11101000`, where the most significant bit `1` corresponds to the input assignment `(1, 1, 1)`, and the least significant bit `0` corresponds to the input assignment `(0, 0, 0)`.</span></span>
<span data-ttu-id="dd309-110">Se puede representar mediante el número entero grande `0xE8L` en notación hexadecimal o como `232L` en notación decimal.</span><span class="sxs-lookup"><span data-stu-id="dd309-110">It can be represented by the big integer `0xE8L` in hexadecimal notation or as `232L` in decimal notation.</span></span>  <span data-ttu-id="dd309-111">El `L` sufijo indica que la constante es de tipo `BigInt` .</span><span class="sxs-lookup"><span data-stu-id="dd309-111">The `L` suffix indicates that the constant is of type `BigInt`.</span></span>
<span data-ttu-id="dd309-112">También se pueden encontrar más detalles sobre esta representación en las [tablas reales Kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span><span class="sxs-lookup"><span data-stu-id="dd309-112">More details on this representation can also be found in the [truth tables kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span></span>

<span data-ttu-id="dd309-113">La implementación de hace uso de las @"microsoft.quantum.intrinsic.cnot" puertas de y @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="dd309-113">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>

## <a name="input"></a><span data-ttu-id="dd309-114">Entrada</span><span class="sxs-lookup"><span data-stu-id="dd309-114">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="dd309-115">FUNC: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="dd309-115">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="dd309-116">Tabla de verdad booleana representada como Big Integer</span><span class="sxs-lookup"><span data-stu-id="dd309-116">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="dd309-117">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dd309-117">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dd309-118">Registro de qubits de control</span><span class="sxs-lookup"><span data-stu-id="dd309-118">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="dd309-119">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dd309-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dd309-120">Qubit de destino</span><span class="sxs-lookup"><span data-stu-id="dd309-120">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="dd309-121">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd309-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="dd309-122">Referencias</span><span class="sxs-lookup"><span data-stu-id="dd309-122">References</span></span>

- [<span data-ttu-id="dd309-123">*N. Schuch*, *J. Siewert*, PRL 91, no. 027902, 2003, arXiv: Quant-pH/0303063</span><span class="sxs-lookup"><span data-stu-id="dd309-123">*N. Schuch*, *J. Siewert*, PRL 91, no. 027902, 2003, arXiv:quant-ph/0303063</span></span>](https://arxiv.org/abs/quant-ph/0303063)
- [<span data-ttu-id="dd309-124">*Dittrich Soeken*, *Martin Roetteler*, arXiv: 2005.12310</span><span class="sxs-lookup"><span data-stu-id="dd309-124">*Mathias Soeken*, *Martin Roetteler*, arXiv:2005.12310</span></span>](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a><span data-ttu-id="dd309-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd309-125">See Also</span></span>

- [<span data-ttu-id="dd309-126">Microsoft. Quantum. Synthesis. ApplyXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="dd309-126">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)