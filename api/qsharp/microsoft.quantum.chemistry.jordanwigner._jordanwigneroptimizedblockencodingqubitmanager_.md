---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerOptimizedBlockEncodingQubitManager_
title: _JordanWignerOptimizedBlockEncodingQubitManager_ función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerOptimizedBlockEncodingQubitManager_
qsharp.summary: ''
ms.openlocfilehash: ac7785142879a19d67caaf3fcbde5dc95e566c1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851596"
---
# <a name="_jordanwigneroptimizedblockencodingqubitmanager_-function"></a><span data-ttu-id="603bb-102">_JordanWignerOptimizedBlockEncodingQubitManager_ función)</span><span class="sxs-lookup"><span data-stu-id="603bb-102">_JordanWignerOptimizedBlockEncodingQubitManager_ function</span></span>

<span data-ttu-id="603bb-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="603bb-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="603bb-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="603bb-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>




```qsharp
function _JordanWignerOptimizedBlockEncodingQubitManager_ (targetError : Double, nCoeffs : Int, nZ : Int, nMaj : Int, nIdxRegQubits : Int, ctrlRegister : Qubit[]) : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[], Qubit, Qubit[], Qubit[], Qubit[], Microsoft.Quantum.Arithmetic.LittleEndian, Microsoft.Quantum.Arithmetic.LittleEndian[]), (Qubit, Qubit[], Qubit[], Qubit[], Microsoft.Quantum.Arithmetic.LittleEndian[]), Qubit[])
```


## <a name="input"></a><span data-ttu-id="603bb-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="603bb-105">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="603bb-106">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="603bb-106">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="ncoeffs--int"></a><span data-ttu-id="603bb-107">nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="603bb-107">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="nz--int"></a><span data-ttu-id="603bb-108">nZ: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="603bb-108">nZ : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="nmaj--int"></a><span data-ttu-id="603bb-109">nMaj: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="603bb-109">nMaj : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="nidxregqubits--int"></a><span data-ttu-id="603bb-110">nIdxRegQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="603bb-110">nIdxRegQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="ctrlregister--qubit"></a><span data-ttu-id="603bb-111">ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="603bb-111">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--littleendianqubitqubitqubitqubitqubitlittleendianlittleendianqubitqubitqubitqubitlittleendianqubit"></a><span data-ttu-id="603bb-112">Salida: (([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[],[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[]), ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[],[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[]),[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="603bb-112">Output : (([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[]),([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[]),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

