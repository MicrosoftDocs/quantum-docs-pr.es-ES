---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: Operación EncodeIntoSteaneCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 2f65423a17dafadd1f9f10a07335150dfc8bf886
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826206"
---
# <a name="encodeintosteanecode-operation"></a><span data-ttu-id="85f5a-102">Operación EncodeIntoSteaneCode</span><span class="sxs-lookup"><span data-stu-id="85f5a-102">EncodeIntoSteaneCode operation</span></span>

<span data-ttu-id="85f5a-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="85f5a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="85f5a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="85f5a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="85f5a-105">Una operación de codificación que asigna un registro de Quantum sin codificar a un registro de Quantum codificado en el Código ⟦ 7, 1, 3 ⟧ Steane Quantum.</span><span class="sxs-lookup"><span data-stu-id="85f5a-105">An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="85f5a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="85f5a-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="85f5a-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="85f5a-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="85f5a-108">Un registro qubit que contiene el estado de Quantum sin codificar</span><span class="sxs-lookup"><span data-stu-id="85f5a-108">A qubit register which holds the an unencoded quantum state</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="85f5a-109">auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="85f5a-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="85f5a-110">Un registro qubit que es inicialmente cero y que se agrega al sistema Quantum para que se pueda realizar una operación de codificación.</span><span class="sxs-lookup"><span data-stu-id="85f5a-110">A qubit register which is initially zero and which gets added to the quantum system so that an encoding operation can be performed</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="85f5a-111">Salida: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="85f5a-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="85f5a-112">Un registro de Quantum que contiene el estado después de haber aplicado el codificador Steane</span><span class="sxs-lookup"><span data-stu-id="85f5a-112">A quantum register holding the state after the Steane encoder has been applied</span></span>

## <a name="see-also"></a><span data-ttu-id="85f5a-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85f5a-113">See Also</span></span>

- [<span data-ttu-id="85f5a-114">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="85f5a-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="85f5a-115">Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="85f5a-115">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)