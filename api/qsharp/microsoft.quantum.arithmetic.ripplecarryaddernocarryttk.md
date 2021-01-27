---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: Operación RippleCarryAdderNoCarryTTK
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: 0e131204d3eaff7f99aa9ff7c3c1ae93a1bf611b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846336"
---
# <a name="ripplecarryaddernocarryttk-operation"></a><span data-ttu-id="63101-102">Operación RippleCarryAdderNoCarryTTK</span><span class="sxs-lookup"><span data-stu-id="63101-102">RippleCarryAdderNoCarryTTK operation</span></span>

<span data-ttu-id="63101-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="63101-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="63101-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63101-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63101-105">La adición de una ondulación en contexto de dos enteros sin llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="63101-105">Reversible, in-place ripple-carry addition of two integers without carry out.</span></span>

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="63101-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="63101-106">Description</span></span>

<span data-ttu-id="63101-107">Dado dos $n enteros de $-bit codificados en registros de LittleEndian `xs` y `ys` , la operación calcula la suma de los dos enteros de módulo $2 ^ n $, donde $n $ es el tamaño de bits de las entradas `xs` y `ys` .</span><span class="sxs-lookup"><span data-stu-id="63101-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, the operation computes the sum of the two integers modulo $2^n$, where $n$ is the bit size of the inputs `xs` and `ys`.</span></span> <span data-ttu-id="63101-108">No calcula el bit de transporte.</span><span class="sxs-lookup"><span data-stu-id="63101-108">It does not compute the carry out bit.</span></span>

## <a name="input"></a><span data-ttu-id="63101-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="63101-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="63101-110">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="63101-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="63101-111">LittleEndian qubit registra la codificación del primer entero sumando.</span><span class="sxs-lookup"><span data-stu-id="63101-111">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="63101-112">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="63101-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="63101-113">LittleEndian qubit registra la codificación del segundo entero sumando, se modifica para contener los bits $n $ menos significativos de la suma.</span><span class="sxs-lookup"><span data-stu-id="63101-113">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="63101-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63101-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="63101-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="63101-115">Remarks</span></span>

<span data-ttu-id="63101-116">Esta operación tiene la misma funcionalidad que RippleCarryAdderTTK pero no devuelve el bit de transporte.</span><span class="sxs-lookup"><span data-stu-id="63101-116">This operation has the same functionality as RippleCarryAdderTTK but does not return the carry bit.</span></span>

## <a name="references"></a><span data-ttu-id="63101-117">Referencias</span><span class="sxs-lookup"><span data-stu-id="63101-117">References</span></span>

- <span data-ttu-id="63101-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Additions de Quantum y ramificación sin límite", información de Quantum y cálculo, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="63101-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530