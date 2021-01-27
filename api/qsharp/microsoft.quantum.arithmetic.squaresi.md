---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: Operación de cuadrados
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 161b45766c6f4d500d25def24aa509ee7fdc8628
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842921"
---
# <a name="squaresi-operation"></a><span data-ttu-id="c5264-102">Operación de cuadrados</span><span class="sxs-lookup"><span data-stu-id="c5264-102">SquareSI operation</span></span>

<span data-ttu-id="c5264-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c5264-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c5264-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="c5264-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="c5264-105">Entero con signo cuadrado `xs` y almacene el resultado en `result` , que debe ser cero inicialmente.</span><span class="sxs-lookup"><span data-stu-id="c5264-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c5264-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c5264-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="c5264-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c5264-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="c5264-108">entero de n bits a Square (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c5264-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="c5264-109">resultado: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c5264-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="c5264-110">el resultado de bit 2N (SignedLittleEndian) debe estar en el estado $ \ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="c5264-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c5264-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c5264-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c5264-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c5264-112">Remarks</span></span>

<span data-ttu-id="c5264-113">La implementación se basa en IntegerSquare.</span><span class="sxs-lookup"><span data-stu-id="c5264-113">The implementation relies on IntegerSquare.</span></span>