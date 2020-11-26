---
uid: Microsoft.Quantum.Research.Chemistry.OptimizedTrotterStepOracle
title: OptimizedTrotterStepOracle función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: OptimizedTrotterStepOracle
qsharp.summary: Returns optimized Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: 04b1ea457277e0681596cb564fae3782a2d09db9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229824"
---
# <a name="optimizedtrottersteporacle-function"></a>OptimizedTrotterStepOracle función)

Espacio de nombres: [Microsoft. Quantum. Research. química](xref:Microsoft.Quantum.Research.Chemistry)

Paquete: [Microsoft. Quantum. Research. química](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Devuelve la operación de paso de Trotter optimizada y los parámetros necesarios para ejecutarla.

```qsharp
function OptimizedTrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a>Entrada

### <a name="qsharpdata--jordanwignerencodingdata"></a>qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Hamiltonian descrito por `JordanWignerEncodingData` Format.


### <a name="trotterstepsize--double"></a>trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)

Tamaño del paso del integrador de Trotter.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Orden de integrador de Trotter.



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a>Output: ([int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL))

Una tupla donde: `Int` es el número de qubits asignados, `Double` es `1.0/trotterStepSize` y la operación es el paso Trotter.