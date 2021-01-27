---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: Operación MultiplySI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7c7e7dfaee9b9dc717db44956506984e60281dd2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843012"
---
# <a name="multiplysi-operation"></a><span data-ttu-id="f1e80-102">Operación MultiplySI</span><span class="sxs-lookup"><span data-stu-id="f1e80-102">MultiplySI operation</span></span>

<span data-ttu-id="f1e80-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f1e80-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f1e80-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="f1e80-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="f1e80-105">Multiplica un entero con signo `xs` por un entero con signo `ys` y almacena el resultado en `result` , que debe ser cero inicialmente.</span><span class="sxs-lookup"><span data-stu-id="f1e80-105">Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f1e80-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f1e80-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="f1e80-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f1e80-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="f1e80-108">multiplicando de n bits (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f1e80-108">n-bit multiplicand (SignedLittleEndian)</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="f1e80-109">calendario: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f1e80-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="f1e80-110">multiplicador de n bits (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f1e80-110">n-bit multiplier (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="f1e80-111">resultado: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f1e80-111">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="f1e80-112">el resultado de bit 2N (SignedLittleEndian) debe estar en el estado $ \ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="f1e80-112">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f1e80-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f1e80-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

