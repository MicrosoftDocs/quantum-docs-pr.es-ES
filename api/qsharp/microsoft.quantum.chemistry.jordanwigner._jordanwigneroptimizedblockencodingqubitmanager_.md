---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerOptimizedBlockEncodingQubitManager_
title: _JordanWignerOptimizedBlockEncodingQubitManager_ función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerOptimizedBlockEncodingQubitManager_
qsharp.summary: ''
ms.openlocfilehash: 3d6e442a126579966dd5d007e7ec58473c490caf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728012"
---
# <a name="_jordanwigneroptimizedblockencodingqubitmanager_-function"></a><span data-ttu-id="5d092-102">_JordanWignerOptimizedBlockEncodingQubitManager_ función)</span><span class="sxs-lookup"><span data-stu-id="5d092-102">_JordanWignerOptimizedBlockEncodingQubitManager_ function</span></span>

<span data-ttu-id="5d092-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="5d092-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="5d092-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5d092-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
function _JordanWignerOptimizedBlockEncodingQubitManager_ (targetError : Double, nCoeffs : Int, nZ : Int, nMaj : Int, nIdxRegQubits : Int, ctrlRegister : Qubit[]) : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[], Qubit, Qubit[], Qubit[], Qubit[], Microsoft.Quantum.Arithmetic.LittleEndian, Microsoft.Quantum.Arithmetic.LittleEndian[]), (Qubit, Qubit[], Qubit[], Qubit[], Microsoft.Quantum.Arithmetic.LittleEndian[]), Qubit[])
```


## <a name="input"></a><span data-ttu-id="5d092-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="5d092-105">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="5d092-106">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5d092-106">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="ncoeffs--int"></a><span data-ttu-id="5d092-107">nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d092-107">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="nz--int"></a><span data-ttu-id="5d092-108">nZ: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d092-108">nZ : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="nmaj--int"></a><span data-ttu-id="5d092-109">nMaj: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d092-109">nMaj : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="nidxregqubits--int"></a><span data-ttu-id="5d092-110">nIdxRegQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d092-110">nIdxRegQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="ctrlregister--qubit"></a><span data-ttu-id="5d092-111">ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5d092-111">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--littleendianqubitqubitqubitqubitqubitlittleendianlittleendianqubitqubitqubitqubitlittleendianqubit"></a><span data-ttu-id="5d092-112">Salida: (([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[],[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[]), ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[],[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[]),[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="5d092-112">Output : (([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[]),([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[]),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>
