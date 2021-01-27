---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operación MeasureAllZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854667"
---
# <a name="measureallz-operation"></a><span data-ttu-id="303d0-102">Operación MeasureAllZ</span><span class="sxs-lookup"><span data-stu-id="303d0-102">MeasureAllZ operation</span></span>

<span data-ttu-id="303d0-103">Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="303d0-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="303d0-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="303d0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="303d0-105">Mide conjuntamente un registro de qubits en la base de Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="303d0-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="303d0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="303d0-106">Description</span></span>

<span data-ttu-id="303d0-107">Mide un registro de qubits en el $Z \otimes Z \otimes \cdots \otimes Z $, que representa la paridad del registro completo.</span><span class="sxs-lookup"><span data-stu-id="303d0-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="303d0-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="303d0-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="303d0-109">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="303d0-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="303d0-110">El registro que se va a medir.</span><span class="sxs-lookup"><span data-stu-id="303d0-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="303d0-111">Salida: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="303d0-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="303d0-112">El resultado de medir $Z \otimes Z \otimes \cdots \otimes Z $.</span><span class="sxs-lookup"><span data-stu-id="303d0-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>