---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: dad90475b2506187282825e143b11adc5120f453
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727125"
---
# <a name="bitfliprecoveryfn-function"></a><span data-ttu-id="f5a4b-102">BitFlipRecoveryFn función)</span><span class="sxs-lookup"><span data-stu-id="f5a4b-102">BitFlipRecoveryFn function</span></span>

<span data-ttu-id="f5a4b-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f5a4b-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f5a4b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f5a4b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f5a4b-105">Función para las operaciones de Pauli de recuperación de la medición de síndrome determinada por búsqueda de tabla para el código de volteo de bits ⟦ de 3, 1, 1 ⟧.</span><span class="sxs-lookup"><span data-stu-id="f5a4b-105">Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.</span></span>

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="f5a4b-106">Salida: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="f5a4b-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="f5a4b-107">Función de tipo `RecoveryFn` que toma una medición del síndrome `Result[]` y devuelve las `Pauli[]` operaciones que corrigen el error detectado.</span><span class="sxs-lookup"><span data-stu-id="f5a4b-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5a4b-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f5a4b-108">See Also</span></span>

- [<span data-ttu-id="f5a4b-109">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="f5a4b-109">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)