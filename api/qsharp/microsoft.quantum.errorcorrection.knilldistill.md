---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: Operación KnillDistill
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 1135db83cf750918347df10c6f1301b636aaee0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727034"
---
# <a name="knilldistill-operation"></a>Operación KnillDistill

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Configura [](https://nuget.org/packages/)


Implementa el algoritmo de destilación de estado mágico de Knill.

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a>Descripción

Dadas 15 copias aproximadas de un estado mágico $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} \end{align}, $ $ produce una copia de mayor calidad.

## <a name="input"></a>Entrada

### <a name="roughmagic--qubit"></a>roughMagic: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registro de quince qubits que contiene copias aproximadas de un estado mágico. La siguiente aplicación de este procedimiento de destilación contendrá `roughMagic[0]` una copia de mayor calidad y el resto del registro se restablecerá al estado $ \ket{00\cdots 0} $.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)

Si `true` es, el procedimiento se realizó correctamente y se debe aceptar la copia de mayor calidad. Si `false` es, se produce un error en el procedimiento, y el estado del registro se debe considerar sin definir.

## <a name="remarks"></a>Observaciones

Seguimos el algoritmo de Knill.
Sin embargo, la implementación actual está lejos de ser óptima, ya que utiliza demasiados qubits.
Los Estados mágicos se insertan en esta rutina, en cuyo caso hay mejores protocolos.

## <a name="references"></a>Referencias

- [Knill](https://arxiv.org/abs/quant-ph/0402171)