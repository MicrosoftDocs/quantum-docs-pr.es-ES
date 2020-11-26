---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: dc2bd02c40b53eca726f70578e3c5918add8f1bb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230453"
---
# <a name="multiplygeneratorindex-function"></a>MultiplyGeneratorIndex función)

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Multiplica el coeficiente en un `GeneratorIndex` .

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Entrada

### <a name="multiplier--double"></a>multiplicador: [Double](xref:microsoft.quantum.lang-ref.double)

Multiplicador del coeficiente.


### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` que se va a multiplicar.



## <a name="output--generatorindex"></a>Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex`Que representa un término con coeficiente de un factor `multiplier` mayor.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Simulation. GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)