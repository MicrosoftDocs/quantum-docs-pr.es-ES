---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 84dc132528f8fd1c45fb2f7345111a05626ee686
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839623"
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