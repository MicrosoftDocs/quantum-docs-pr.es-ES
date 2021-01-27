---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Operación IncrementByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: f5bacef299ab0b3627e757abdcaa798cf9b2e7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846598"
---
# <a name="incrementbymodularinteger-operation"></a><span data-ttu-id="adc5b-102">Operación IncrementByModularInteger</span><span class="sxs-lookup"><span data-stu-id="adc5b-102">IncrementByModularInteger operation</span></span>

<span data-ttu-id="adc5b-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="adc5b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="adc5b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="adc5b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="adc5b-105">Realiza un incremento modular de un registro qubit por una constante de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="adc5b-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="adc5b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="adc5b-106">Description</span></span>

<span data-ttu-id="adc5b-107">Vamos `increment` a indicar $a $, `modulus` $N $ y un entero codificados en `target` por $y $.</span><span class="sxs-lookup"><span data-stu-id="adc5b-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="adc5b-108">A continuación, la operación realiza la transformación siguiente: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} los enteros se codifican en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="adc5b-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format.</span></span>

## <a name="input"></a><span data-ttu-id="adc5b-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="adc5b-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="adc5b-110">incremento: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="adc5b-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="adc5b-111">Incremento de entero $a $ que se va a agregar a $y $.</span><span class="sxs-lookup"><span data-stu-id="adc5b-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="adc5b-112">módulo: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="adc5b-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="adc5b-113">Entero $N $ que mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="adc5b-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="adc5b-114">destino: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="adc5b-114">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="adc5b-115">Entero $y $ en el `LittleEndian` formato `increment` al que se agrega $a $.</span><span class="sxs-lookup"><span data-stu-id="adc5b-115">Integer $y$ in `LittleEndian` format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="adc5b-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="adc5b-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="adc5b-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="adc5b-117">Remarks</span></span>

<span data-ttu-id="adc5b-118">Supone que el valor inicial del destino es menor que $N $ y que el incremento $a $ es menor que $N $.</span><span class="sxs-lookup"><span data-stu-id="adc5b-118">Assumes that the initial value of target is less than $N$ and that the increment $a$ is less than $N$.</span></span>
<span data-ttu-id="adc5b-119">Tenga en cuenta que <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implementa la misma operación de la `PhaseLittleEndian` base.</span><span class="sxs-lookup"><span data-stu-id="adc5b-119">Note that <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implements the same operation in the `PhaseLittleEndian` basis.</span></span>

## <a name="see-also"></a><span data-ttu-id="adc5b-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="adc5b-120">See Also</span></span>

- [<span data-ttu-id="adc5b-121">Microsoft. Quantum. aritmético. IncrementPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="adc5b-121">Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)