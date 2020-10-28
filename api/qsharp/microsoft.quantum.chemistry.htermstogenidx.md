---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 73324a48cc4b42de0d5d8618ad9e833d289125f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728138"
---
# <a name="htermstogenidx-function"></a>HTermsToGenIdx función)

Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)

Configura [](https://nuget.org/packages/)


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