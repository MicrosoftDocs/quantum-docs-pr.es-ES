---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: Operación CompareGTSI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: f725bdbaa945a4f87e90fc71930c37642113c21a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846707"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="5e488-102">Operación CompareGTSI</span><span class="sxs-lookup"><span data-stu-id="5e488-102">CompareGTSI operation</span></span>

<span data-ttu-id="5e488-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5e488-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5e488-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="5e488-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="5e488-105">Contenedor para la comparación de enteros con signo: `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="5e488-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5e488-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5e488-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="5e488-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5e488-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="5e488-108">Primer $n número de $ bits</span><span class="sxs-lookup"><span data-stu-id="5e488-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="5e488-109">calendario: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5e488-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="5e488-110">Second $n número de $-bit</span><span class="sxs-lookup"><span data-stu-id="5e488-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="5e488-111">resultado: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5e488-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5e488-112">Se volteará si $xs > calendario $</span><span class="sxs-lookup"><span data-stu-id="5e488-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="5e488-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e488-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

