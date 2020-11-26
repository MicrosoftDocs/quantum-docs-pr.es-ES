---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: c53ac3f2c46bca955847fc7b380337e3910390ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202930"
---
# <a name="sizeadjustedtruthtable-function"></a>SizeAdjustedTruthTable función)

Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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