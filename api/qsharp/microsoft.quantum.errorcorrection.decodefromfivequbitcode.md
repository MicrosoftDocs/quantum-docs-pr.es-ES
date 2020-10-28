---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromFiveQubitCode
title: Operación DecodeFromFiveQubitCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromFiveQubitCode
qsharp.summary: Decodes the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 421da6296b604f30aefed58730091f64f19c3a61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727113"
---
# <a name="decodefromfivequbitcode-operation"></a><span data-ttu-id="fcfad-102">Operación DecodeFromFiveQubitCode</span><span class="sxs-lookup"><span data-stu-id="fcfad-102">DecodeFromFiveQubitCode operation</span></span>

<span data-ttu-id="fcfad-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="fcfad-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="fcfad-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fcfad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fcfad-105">Descodifica el código Quantum de ⟦ 5, 1, 3 ⟧.</span><span class="sxs-lookup"><span data-stu-id="fcfad-105">Decodes the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation DecodeFromFiveQubitCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="fcfad-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fcfad-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="fcfad-107">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="fcfad-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="fcfad-108">Una matriz de qubits que representa el estado lógico de código 5-qubit codificado.</span><span class="sxs-lookup"><span data-stu-id="fcfad-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="fcfad-109">Salida: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="fcfad-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="fcfad-110">Matriz qubit de longitud 1 que representa el estado sin codificar en el primer parámetro, junto con el qubits auxiliar en el segundo parámetro.</span><span class="sxs-lookup"><span data-stu-id="fcfad-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcfad-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fcfad-111">See Also</span></span>

- [<span data-ttu-id="fcfad-112">Microsoft. Quantum. ErrorCorrection. FiveQubitCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="fcfad-112">Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder)
- [<span data-ttu-id="fcfad-113">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="fcfad-113">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)