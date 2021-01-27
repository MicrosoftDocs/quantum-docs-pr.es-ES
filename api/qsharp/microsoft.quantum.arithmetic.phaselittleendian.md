---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: Tipo definido por el usuario PhaseLittleEndian
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 59df1db31090f875ccd261fe6cc43995ba57b963
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842998"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="8ae64-102">Tipo definido por el usuario PhaseLittleEndian</span><span class="sxs-lookup"><span data-stu-id="8ae64-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="8ae64-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8ae64-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8ae64-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ae64-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ae64-105">Enteros sin signo Little-endian en la base de QFT.</span><span class="sxs-lookup"><span data-stu-id="8ae64-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="8ae64-106">Por ejemplo, si $ \ket{x} $ es la codificación Little-Endian del entero $x $ en la base de cálculo, $ \operatorname{QFTLE} \ket{x} $ es la codificación de $x $ en la base de QFT.</span><span class="sxs-lookup"><span data-stu-id="8ae64-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="8ae64-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8ae64-107">Remarks</span></span>

<span data-ttu-id="8ae64-108">Lo abreviamos `PhaseLittleEndian` como `PhaseLE` en la documentación de.</span><span class="sxs-lookup"><span data-stu-id="8ae64-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ae64-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ae64-109">See Also</span></span>

- [<span data-ttu-id="8ae64-110">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="8ae64-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="8ae64-111">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="8ae64-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)