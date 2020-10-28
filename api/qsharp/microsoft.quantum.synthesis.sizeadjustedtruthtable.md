---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 3480f022df7a289594b003f201d16d8bf7c29d7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734060"
---
# <a name="sizeadjustedtruthtable-function"></a>SizeAdjustedTruthTable función)

Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Configura [](https://nuget.org/packages/)


Ajusta la tabla de verdad de la matriz de valores booleanos según el número de variables.

Se devuelve una nueva matriz de longitud `2^numVars` , que posiblemente requiere extender `table` el tamaño de `false` las entradas o truncarla en `2^numVars` elementos.

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a>Entrada

### <a name="table--bool"></a>tabla: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Tabla de verdad como matriz de valores veracidad


### <a name="numvars--int"></a>numVars: [int](xref:microsoft.quantum.lang-ref.int)

Número de variables



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Tabla de veracidad ajustada de tamaño