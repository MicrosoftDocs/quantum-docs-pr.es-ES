---
uid: Microsoft.Quantum.Measurement.MultiM
title: Operación MultiM
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: b7f4083bde84c204611ea33746ae351a3e27b946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857007"
---
# <a name="multim-operation"></a><span data-ttu-id="e6f82-102">Operación MultiM</span><span class="sxs-lookup"><span data-stu-id="e6f82-102">MultiM operation</span></span>

<span data-ttu-id="e6f82-103">Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="e6f82-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="e6f82-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6f82-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6f82-105">Mide cada qubit en una matriz determinada en función del estándar.</span><span class="sxs-lookup"><span data-stu-id="e6f82-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="e6f82-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e6f82-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="e6f82-107">destinos: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e6f82-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e6f82-108">Matriz de qubits que se va a medir.</span><span class="sxs-lookup"><span data-stu-id="e6f82-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="e6f82-109">Salida: __no <Result> válido__[]</span><span class="sxs-lookup"><span data-stu-id="e6f82-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="e6f82-110">Matriz de resultados de la medición.</span><span class="sxs-lookup"><span data-stu-id="e6f82-110">An array of measurement results.</span></span>