---
uid: Microsoft.Quantum.Arithmetic.AddI
title: Operación AddI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 7ee2b9099ea65b95647422dadc1efe4bf043d147
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731893"
---
# <a name="addi-operation"></a><span data-ttu-id="04fde-102">Operación AddI</span><span class="sxs-lookup"><span data-stu-id="04fde-102">AddI operation</span></span>

<span data-ttu-id="04fde-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="04fde-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="04fde-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="04fde-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="04fde-105">Elige entre agregar y sin, automáticamente, en función del tamaño del registro de `ys` .</span><span class="sxs-lookup"><span data-stu-id="04fde-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="04fde-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="04fde-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="04fde-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="04fde-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="04fde-108">$n addend de $ bits.</span><span class="sxs-lookup"><span data-stu-id="04fde-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="04fde-109">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="04fde-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="04fde-110">Addend con al menos $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="04fde-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="04fde-111">Contendrá el resultado.</span><span class="sxs-lookup"><span data-stu-id="04fde-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="04fde-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="04fde-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

