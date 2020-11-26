---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: Operación RippleCarryAdderNoCarryTTK
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: a539d85a4800c2f4452a1c6fe2c4f88a6296c3e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222004"
---
# <a name="ripplecarryaddernocarryttk-operation"></a><span data-ttu-id="e0d02-102">Operación RippleCarryAdderNoCarryTTK</span><span class="sxs-lookup"><span data-stu-id="e0d02-102">RippleCarryAdderNoCarryTTK operation</span></span>

<span data-ttu-id="e0d02-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e0d02-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e0d02-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e0d02-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e0d02-105">La adición de una ondulación en contexto de dos enteros sin llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="e0d02-105">Reversible, in-place ripple-carry addition of two integers without carry out.</span></span>

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e0d02-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0d02-106">Description</span></span>

<span data-ttu-id="e0d02-107">Dado dos $n enteros de $-bit codificados en registros de LittleEndian `xs` y `ys` , la operación calcula la suma de los dos enteros de módulo $2 ^ n $, donde $n $ es el tamaño de bits de las entradas `xs` y `ys` .</span><span class="sxs-lookup"><span data-stu-id="e0d02-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, the operation computes the sum of the two integers modulo $2^n$, where $n$ is the bit size of the inputs `xs` and `ys`.</span></span> <span data-ttu-id="e0d02-108">No calcula el bit de transporte.</span><span class="sxs-lookup"><span data-stu-id="e0d02-108">It does not compute the carry out bit.</span></span>

## <a name="input"></a><span data-ttu-id="e0d02-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="e0d02-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="e0d02-110">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e0d02-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e0d02-111">LittleEndian qubit registra la codificación del primer entero sumando.</span><span class="sxs-lookup"><span data-stu-id="e0d02-111">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="e0d02-112">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e0d02-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e0d02-113">LittleEndian qubit registra la codificación del segundo entero sumando, se modifica para contener los bits $n $ menos significativos de la suma.</span><span class="sxs-lookup"><span data-stu-id="e0d02-113">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e0d02-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e0d02-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e0d02-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e0d02-115">Remarks</span></span>

<span data-ttu-id="e0d02-116">Esta operación tiene la misma funcionalidad que RippleCarryAdderTTK pero no devuelve el bit de transporte.</span><span class="sxs-lookup"><span data-stu-id="e0d02-116">This operation has the same functionality as RippleCarryAdderTTK but does not return the carry bit.</span></span>

## <a name="references"></a><span data-ttu-id="e0d02-117">Referencias</span><span class="sxs-lookup"><span data-stu-id="e0d02-117">References</span></span>

- <span data-ttu-id="e0d02-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Additions de Quantum y ramificación sin límite", información de Quantum y cálculo, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="e0d02-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530