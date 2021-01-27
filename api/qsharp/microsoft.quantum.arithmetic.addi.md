---
uid: Microsoft.Quantum.Arithmetic.AddI
title: Operación AddI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: a17403652cc2b2712defe52112a3ac599330da9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843844"
---
# <a name="addi-operation"></a><span data-ttu-id="c119a-102">Operación AddI</span><span class="sxs-lookup"><span data-stu-id="c119a-102">AddI operation</span></span>

<span data-ttu-id="c119a-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c119a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c119a-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="c119a-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="c119a-105">Elige entre agregar y sin, automáticamente, en función del tamaño del registro de `ys` .</span><span class="sxs-lookup"><span data-stu-id="c119a-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c119a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c119a-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="c119a-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c119a-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c119a-108">$n addend de $ bits.</span><span class="sxs-lookup"><span data-stu-id="c119a-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="c119a-109">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c119a-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c119a-110">Addend con al menos $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="c119a-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="c119a-111">Contendrá el resultado.</span><span class="sxs-lookup"><span data-stu-id="c119a-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c119a-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c119a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

