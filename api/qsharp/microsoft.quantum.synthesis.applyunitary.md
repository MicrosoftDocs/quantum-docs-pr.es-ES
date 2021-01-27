---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: Operación ApplyUnitary
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859263"
---
# <a name="applyunitary-operation"></a><span data-ttu-id="0c7c7-102">Operación ApplyUnitary</span><span class="sxs-lookup"><span data-stu-id="0c7c7-102">ApplyUnitary operation</span></span>

<span data-ttu-id="0c7c7-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0c7c7-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0c7c7-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0c7c7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0c7c7-105">Aplica la puerta definida por 2 ^ n x 2 ^ n matriz de unitarios.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-105">Applies gate defined by 2^n x 2^n unitary matrix.</span></span>

<span data-ttu-id="0c7c7-106">Se produce un error si la matriz no es unitario o tiene un tamaño incorrecto.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-106">Fails if matrix is not unitary, or has wrong size.</span></span>

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0c7c7-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="0c7c7-107">Input</span></span>

### <a name="unitary--complex"></a><span data-ttu-id="0c7c7-108">unitario: [complejo](xref:Microsoft.Quantum.Math.Complex)[] []</span><span class="sxs-lookup"><span data-stu-id="0c7c7-108">unitary : [Complex](xref:Microsoft.Quantum.Math.Complex)[][]</span></span>

<span data-ttu-id="0c7c7-109">2 ^ n x 2 ^ n matriz de unitario que describe la operación.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-109">2^n x 2^n unitary matrix describing the operation.</span></span>
<span data-ttu-id="0c7c7-110">Si Matrix no es unitario o no tiene un tamaño adecuado, produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-110">If matrix is not unitary or not of suitable size, throws an exception.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="0c7c7-111">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0c7c7-111">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0c7c7-112">Qubits a la que se aplica la operación: registro de longitud n.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-112">Qubits to which apply the operation - register of length n.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0c7c7-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0c7c7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

