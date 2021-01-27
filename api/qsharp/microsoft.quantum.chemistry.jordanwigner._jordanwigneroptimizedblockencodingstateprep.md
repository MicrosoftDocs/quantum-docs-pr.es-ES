---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerOptimizedBlockEncodingStatePrep
title: _JordanWignerOptimizedBlockEncodingStatePrep operación
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerOptimizedBlockEncodingStatePrep
qsharp.summary: ''
ms.openlocfilehash: 492248b49faf594adcd37550db9172a17bf02fad
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851580"
---
# <a name="_jordanwigneroptimizedblockencodingstateprep-operation"></a><span data-ttu-id="06e6f-102">_JordanWignerOptimizedBlockEncodingStatePrep operación</span><span class="sxs-lookup"><span data-stu-id="06e6f-102">_JordanWignerOptimizedBlockEncodingStatePrep operation</span></span>

<span data-ttu-id="06e6f-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="06e6f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="06e6f-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="06e6f-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>




```qsharp
operation _JordanWignerOptimizedBlockEncodingStatePrep (targetError : Double, optimizedBEGeneratorSystem : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem, qROMIdxRegister : Microsoft.Quantum.Arithmetic.LittleEndian, qROMGarbage : Qubit[], signQubit : Qubit, selectZControlRegisters : Qubit[], OptimizedBEControlRegisters : Qubit[], pauliBases : Qubit[], pauliBasesIdx : Microsoft.Quantum.Arithmetic.LittleEndian, indexRegisters : Microsoft.Quantum.Arithmetic.LittleEndian[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="06e6f-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="06e6f-105">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="06e6f-106">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="06e6f-106">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="optimizedbegeneratorsystem--optimizedbegeneratorsystem"></a><span data-ttu-id="06e6f-107">optimizedBEGeneratorSystem: [optimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="06e6f-107">optimizedBEGeneratorSystem : [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span></span>




### <a name="qromidxregister--littleendian"></a><span data-ttu-id="06e6f-108">qROMIdxRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="06e6f-108">qROMIdxRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="qromgarbage--qubit"></a><span data-ttu-id="06e6f-109">qROMGarbage: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="06e6f-109">qROMGarbage : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="signqubit--qubit"></a><span data-ttu-id="06e6f-110">signQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="06e6f-110">signQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="selectzcontrolregisters--qubit"></a><span data-ttu-id="06e6f-111">selectZControlRegisters: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="06e6f-111">selectZControlRegisters : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="optimizedbecontrolregisters--qubit"></a><span data-ttu-id="06e6f-112">OptimizedBEControlRegisters: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="06e6f-112">OptimizedBEControlRegisters : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="paulibases--qubit"></a><span data-ttu-id="06e6f-113">pauliBases: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="06e6f-113">pauliBases : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="paulibasesidx--littleendian"></a><span data-ttu-id="06e6f-114">pauliBasesIdx: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="06e6f-114">pauliBasesIdx : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="indexregisters--littleendian"></a><span data-ttu-id="06e6f-115">indexRegisters: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[]</span><span class="sxs-lookup"><span data-stu-id="06e6f-115">indexRegisters : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="06e6f-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="06e6f-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

