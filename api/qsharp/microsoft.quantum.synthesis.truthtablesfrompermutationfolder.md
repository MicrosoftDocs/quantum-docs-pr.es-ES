---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: TruthTablesFromPermutationFolder función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 86e112782825303805029b2f9f6cfd9d6ce9e8b6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231031"
---
# <a name="truthtablesfrompermutationfolder-function"></a>TruthTablesFromPermutationFolder función)

Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Lógica de descomposición para un índice de variable único

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a>Descripción

Esto toma el estado actual y genera una permutación actualizada y, posiblemente, agrega funciones nuevas para las puertas controladas.

## <a name="input"></a>Entrada

### <a name="numvars--int"></a>numVars: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="state--decompositionstate"></a>Estado: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)




### <a name="index--int"></a>Índice: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--decompositionstate"></a>Salida: [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)

