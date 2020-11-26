---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 59391a882fdbc55172ee93a7428c1735bbb29500
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216037"
---
# <a name="htermtogenidx-function"></a>HTermToGenIdx función)

Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)

Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Convierte un término Hamiltonian en `HTerm` formato de datos en un GeneratorIndex.

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Entrada

### <a name="term--hterm"></a>término: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)

Datos de entrada en `HTerm` formato.


### <a name="termtype--int"></a>Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)[]

Información adicional agregada a GeneratorIndex.



## <a name="output--generatorindex"></a>Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Un GeneratorIndex que representa un término Hamiltonian representado por `term` , junto con información adicional agregada por `termType` .