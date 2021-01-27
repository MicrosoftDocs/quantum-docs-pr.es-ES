---
uid: Microsoft.Quantum.Intrinsic.I
title: Operación I
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 0af14a9aff20da493e95c7feba6afbb907d3d69f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849404"
---
# <a name="i-operation"></a><span data-ttu-id="269a8-102">Operación I</span><span class="sxs-lookup"><span data-stu-id="269a8-102">I operation</span></span>

<span data-ttu-id="269a8-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="269a8-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="269a8-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="269a8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="269a8-105">Realiza la operación de identidad (no OP) en un único qubit.</span><span class="sxs-lookup"><span data-stu-id="269a8-105">Performs the identity operation (no-op) on a single qubit.</span></span>

```qsharp
operation I (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="269a8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="269a8-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="269a8-107">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="269a8-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="269a8-108">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="269a8-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="269a8-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="269a8-109">Remarks</span></span>

<span data-ttu-id="269a8-110">Esto no es operativo.</span><span class="sxs-lookup"><span data-stu-id="269a8-110">This is a no-op.</span></span> <span data-ttu-id="269a8-111">Se proporciona por integridad y, a veces, resulta útil llamar a la identidad en un algoritmo o pasarla como parámetro.</span><span class="sxs-lookup"><span data-stu-id="269a8-111">It is provided for completeness and because sometimes it is useful to call the identity in an algorithm or to pass it as a parameter.</span></span>