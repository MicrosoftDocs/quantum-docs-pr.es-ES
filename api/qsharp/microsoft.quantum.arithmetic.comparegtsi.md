---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: Operación CompareGTSI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: 735ae21168d8efb3e626a8f1ea36e97f5cdf8760
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731621"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="2c1dd-102">Operación CompareGTSI</span><span class="sxs-lookup"><span data-stu-id="2c1dd-102">CompareGTSI operation</span></span>

<span data-ttu-id="2c1dd-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2c1dd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2c1dd-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2c1dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2c1dd-105">Contenedor para la comparación de enteros con signo: `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="2c1dd-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="2c1dd-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2c1dd-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="2c1dd-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2c1dd-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="2c1dd-108">Primer $n número de $ bits</span><span class="sxs-lookup"><span data-stu-id="2c1dd-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="2c1dd-109">calendario: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2c1dd-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="2c1dd-110">Second $n número de $-bit</span><span class="sxs-lookup"><span data-stu-id="2c1dd-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="2c1dd-111">resultado: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2c1dd-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2c1dd-112">Se volteará si $xs > calendario $</span><span class="sxs-lookup"><span data-stu-id="2c1dd-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="2c1dd-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c1dd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
