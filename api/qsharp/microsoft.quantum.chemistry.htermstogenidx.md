---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: dbe0718fa3b5439a2987d455fdad73731c988678
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216020"
---
# <a name="htermstogenidx-function"></a>HTermsToGenIdx función)

Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)

Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Convierte un índice en un término Hamiltonian en `HTerm[]` formato de datos en un GeneratorIndex.

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Entrada

### <a name="data--hterm"></a>datos: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

Datos de entrada en `HTerm[]` formato.


### <a name="termtype--int"></a>Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)[]

Información adicional agregada a GeneratorIndex.


### <a name="idx--int"></a>IDX: [int](xref:microsoft.quantum.lang-ref.int)

Índice para un término de Hamiltonian



## <a name="output--generatorindex"></a>Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Un GeneratorIndex que representa un término Hamiltonian representado por `data[idx]` , junto con información adicional agregada por `termType` .