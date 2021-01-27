---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Tipo definido por el usuario SyndromeMeasOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 36336f9e47e5f360cf5e19ffb6e15b4af88b2580
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850050"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="54bad-102">Tipo definido por el usuario SyndromeMeasOp</span><span class="sxs-lookup"><span data-stu-id="54bad-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="54bad-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="54bad-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="54bad-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="54bad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="54bad-105">Representa una operación que se utiliza para medir el síndrome de un bloque de código de corrección de errores.</span><span class="sxs-lookup"><span data-stu-id="54bad-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a><span data-ttu-id="54bad-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54bad-106">Example</span></span>

<span data-ttu-id="54bad-107">Mida los síndromes para el código de volteo de bits $S = \langle ZZI, IZZ \rangle $ Using Scratch qubits de una manera no tolerante a errores:</span><span class="sxs-lookup"><span data-stu-id="54bad-107">Measure syndromes for the bit-flip code $S = \langle ZZI, IZZ \rangle$ using scratch qubits in a non–fault tolerant manner:</span></span>

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a><span data-ttu-id="54bad-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="54bad-108">Remarks</span></span>

<span data-ttu-id="54bad-109">La firma `(LogicalRegister => Syndrome)` representa una operación que actúa conjuntamente en el qubits en `LogicalRegister` y algunos qubits auxiliares seguidos de una medida de la qubits auxiliar para extraer un `Syndrome` valor que representa el `Result[]` de estas medidas.</span><span class="sxs-lookup"><span data-stu-id="54bad-109">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="54bad-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54bad-110">See Also</span></span>

- [<span data-ttu-id="54bad-111">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="54bad-111">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="54bad-112">Microsoft. Quantum. ErrorCorrection. síndrome</span><span class="sxs-lookup"><span data-stu-id="54bad-112">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)