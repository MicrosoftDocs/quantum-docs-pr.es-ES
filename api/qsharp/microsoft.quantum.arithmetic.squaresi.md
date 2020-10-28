---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: Operación de cuadrados
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: c8c4e3cca001aa6d7ce1b9df106ce77f74524301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730460"
---
# <a name="squaresi-operation"></a><span data-ttu-id="6aa21-102">Operación de cuadrados</span><span class="sxs-lookup"><span data-stu-id="6aa21-102">SquareSI operation</span></span>

<span data-ttu-id="6aa21-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6aa21-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6aa21-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6aa21-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6aa21-105">Entero con signo cuadrado `xs` y almacene el resultado en `result` , que debe ser cero inicialmente.</span><span class="sxs-lookup"><span data-stu-id="6aa21-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="6aa21-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6aa21-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="6aa21-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6aa21-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="6aa21-108">entero de n bits a Square (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6aa21-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="6aa21-109">resultado: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6aa21-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="6aa21-110">el resultado de bit 2N (SignedLittleEndian) debe estar en el estado $ \ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="6aa21-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6aa21-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6aa21-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6aa21-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6aa21-112">Remarks</span></span>

<span data-ttu-id="6aa21-113">La implementación se basa en IntegerSquare.</span><span class="sxs-lookup"><span data-stu-id="6aa21-113">The implementation relies on IntegerSquare.</span></span>