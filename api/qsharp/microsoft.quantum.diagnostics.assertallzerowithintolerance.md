---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: Operación AssertAllZeroWithinTolerance
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 281855ec79d280c903ebb4d05614081767840778
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830859"
---
# <a name="assertallzerowithintolerance-operation"></a>Operación AssertAllZeroWithinTolerance

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


La aserción de que los qubits proporcionados están todos en $ \ket {0} $ State hasta una tolerancia determinada.

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits que se imponen en $ \ket {0} $ state.


### <a name="tolerance--double"></a>tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)

Precisión con la que el estado debe estar en el {0} Estado $ \ket $



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Diagnostics. AssertQubitWithinTolerance](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)