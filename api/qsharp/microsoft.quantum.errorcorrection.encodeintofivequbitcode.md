---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: Operación EncodeIntoFiveQubitCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: c9df4c5c98a78cae8b3af4597020d35469454153
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727083"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="294cb-102">Operación EncodeIntoFiveQubitCode</span><span class="sxs-lookup"><span data-stu-id="294cb-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="294cb-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="294cb-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="294cb-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="294cb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="294cb-105">Codifica en el código de Quantum ⟦ 5, 1, 3 ⟧.</span><span class="sxs-lookup"><span data-stu-id="294cb-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="294cb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="294cb-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="294cb-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="294cb-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="294cb-108">Un qubit que representa un estado sin codificar.</span><span class="sxs-lookup"><span data-stu-id="294cb-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="294cb-109">Esta matriz `Qubit[]` tiene una longitud de 1.</span><span class="sxs-lookup"><span data-stu-id="294cb-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="294cb-110">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="294cb-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="294cb-111">Un registro de qubits auxiliares que se usará para representar el estado codificado.</span><span class="sxs-lookup"><span data-stu-id="294cb-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="294cb-112">Salida: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="294cb-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="294cb-113">Matriz de qubits física de tipo `LogicalRegister` que almacena el estado codificado.</span><span class="sxs-lookup"><span data-stu-id="294cb-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="294cb-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="294cb-114">See Also</span></span>

- [<span data-ttu-id="294cb-115">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="294cb-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)