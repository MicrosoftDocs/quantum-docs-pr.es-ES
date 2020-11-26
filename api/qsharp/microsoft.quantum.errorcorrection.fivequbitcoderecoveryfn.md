---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 47e8a74d3631be2209537679ec9786a8dab63c58
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200788"
---
# <a name="fivequbitcoderecoveryfn-function"></a><span data-ttu-id="8ec88-102">FiveQubitCodeRecoveryFn función)</span><span class="sxs-lookup"><span data-stu-id="8ec88-102">FiveQubitCodeRecoveryFn function</span></span>

<span data-ttu-id="8ec88-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="8ec88-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="8ec88-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ec88-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ec88-105">Devuelve la función que asigna las medidas del síndrome de error a los operadores de Pauli de corrección de errores adecuados por búsqueda de tabla para el código de Quantum ⟦ 5, 1, 3 ⟧.</span><span class="sxs-lookup"><span data-stu-id="8ec88-105">Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="8ec88-106">Salida: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="8ec88-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="8ec88-107">Función de tipo `RecoveryFn` que toma una medición del síndrome `Result[]` y devuelve los `Pauli[]` operadores que corrigen el error detectado.</span><span class="sxs-lookup"><span data-stu-id="8ec88-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operators that corrects the detected error.</span></span>

## <a name="remarks"></a><span data-ttu-id="8ec88-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8ec88-108">Remarks</span></span>

<span data-ttu-id="8ec88-109">Al recorrer en iteración todos los errores del peso $1 $, se obtiene un total de $3 \ Times 5 = 15 $ posibles síndrome no triviales.</span><span class="sxs-lookup"><span data-stu-id="8ec88-109">By iterating over all errors of weight $1$, we obtain a total of $3\times 5=15$ possible non-trivial syndromes.</span></span>
<span data-ttu-id="8ec88-110">Junto con la identidad, se crea una tabla de error y el síndrome correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8ec88-110">Together with the identity, a table of error and corresponding syndrome is built up.</span></span> <span data-ttu-id="8ec88-111">Para el código de 5 qubit que proporciona esta tabla: $X \_ 1: (0, 0, 0, 1); X \_ 2: (1, 0, 0, 0); X \_ 3: (1, 1, 0, 0); X \_ 4: (0, 1, 1, 0); X \_ 5: (0, 0, 1,1) $, $Z \_ 1: (1, 0, 1, 0); Z \_ 2: (0, 1, 0, 1); Z \_ 3: (0, 0, 1, 0); Z \_ 4: (1, 0, 0, 1); Z \_ 5: (0, 1, 0, 0) $ con $Y _I $ obtenido agregando la $X _I $ y $Z _I $ síndromes.</span><span class="sxs-lookup"><span data-stu-id="8ec88-111">For the 5 qubit code this table is given by: $X\_1: (0,0,0,1); X\_2: (1,0,0,0); X\_3: (1,1,0,0); X\_4: (0,1,1,0); X\_5: (0,0,1,1)$, $Z\_1: (1,0,1,0); Z\_2: (0,1,0,1); Z\_3: (0,0,1,0); Z\_4: (1,0,0,1); Z\_5: (0,1,0,0)$ with $Y_i$ obtained by adding the $X_i$ and $Z_i$ syndromes.</span></span> <span data-ttu-id="8ec88-112">Tenga en cuenta que la ordenación en la recuperación de la búsqueda de tabla se proporciona mediante la conversión de bitvectors en enteros (mediante little endian).</span><span class="sxs-lookup"><span data-stu-id="8ec88-112">Note that the ordering in the table lookup recovery is given by converting the bitvectors to integers (using little endian).</span></span>

## <a name="see-also"></a><span data-ttu-id="8ec88-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ec88-113">See Also</span></span>

- [<span data-ttu-id="8ec88-114">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="8ec88-114">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)