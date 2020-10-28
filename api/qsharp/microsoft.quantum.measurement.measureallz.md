---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operación MeasureAllZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726518"
---
# <a name="measureallz-operation"></a><span data-ttu-id="ea060-102">Operación MeasureAllZ</span><span class="sxs-lookup"><span data-stu-id="ea060-102">MeasureAllZ operation</span></span>

<span data-ttu-id="ea060-103">Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="ea060-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="ea060-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea060-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea060-105">Mide conjuntamente un registro de qubits en la base de Pauli Z.</span><span class="sxs-lookup"><span data-stu-id="ea060-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="ea060-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea060-106">Description</span></span>

<span data-ttu-id="ea060-107">Mide un registro de qubits en el $Z \otimes Z \otimes \cdots \otimes Z $, que representa la paridad del registro completo.</span><span class="sxs-lookup"><span data-stu-id="ea060-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="ea060-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="ea060-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="ea060-109">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ea060-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ea060-110">El registro que se va a medir.</span><span class="sxs-lookup"><span data-stu-id="ea060-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="ea060-111">Salida: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="ea060-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="ea060-112">El resultado de medir $Z \otimes Z \otimes \cdots \otimes Z $.</span><span class="sxs-lookup"><span data-stu-id="ea060-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>