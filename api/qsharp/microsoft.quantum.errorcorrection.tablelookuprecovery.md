---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: 9f957155e42bb6b5163521171fcba5897f290335
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824396"
---
# <a name="tablelookuprecovery-function"></a><span data-ttu-id="ae16d-102">TableLookupRecovery función)</span><span class="sxs-lookup"><span data-stu-id="ae16d-102">TableLookupRecovery function</span></span>

<span data-ttu-id="ae16d-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ae16d-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ae16d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ae16d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ae16d-105">Para una tabla determinada de operaciones de Pauli en un registro determinado de qubits, esta función devuelve un objeto de tipo `RecoveryFn` que contiene toda la información necesaria para realizar una descodificación de búsqueda de tabla con respecto a la matriz especificada de operaciones de Pauli.</span><span class="sxs-lookup"><span data-stu-id="ae16d-105">For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.</span></span>

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a><span data-ttu-id="ae16d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ae16d-106">Input</span></span>

### <a name="table--pauli"></a><span data-ttu-id="ae16d-107">tabla: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="ae16d-107">table : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="ae16d-108">Tabla de operaciones de Pauli que operan en un registro de qubit determinado</span><span class="sxs-lookup"><span data-stu-id="ae16d-108">Table of Pauli operations that operate on a given qubit register</span></span>



## <a name="output--recoveryfn"></a><span data-ttu-id="ae16d-109">Salida: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="ae16d-109">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="ae16d-110">Objeto de tipo `RecoveryFn` , es decir, un mapa `Syndrome -> Pauli[]` que se asocia a una matriz de síndrome especificada a una operación de corrección de Pauli correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ae16d-110">An object of type `RecoveryFn`, i.e., a map `Syndrome -> Pauli[]` that associates with a given syndrome array a corresponding Pauli correction operation.</span></span>