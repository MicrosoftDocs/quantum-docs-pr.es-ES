---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: Tipo definido por el usuario MCMTMask
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 0d3ca12d55fa4b5e8332d50939954de29e39b715
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734076"
---
# <a name="mcmtmask-user-defined-type"></a>Tipo definido por el usuario MCMTMask

Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Configura [](https://nuget.org/packages/)


Tipo que representa una puerta Toffoli de varios destinos múltiples controlada.

El primer entero es una máscara de bits para las líneas de control.  Los índices de bits establecidos corresponden a los índices de línea de control.

El segundo entero es una máscara de bits para las líneas de destino.  Los índices de bits establecidos corresponden a los índices de línea de destino.

Los índices de bits de ambos enteros deben estar separados.

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="controlmask--int"></a>ControlMask: [int](xref:microsoft.quantum.lang-ref.int)


### <a name="targetmask--int"></a>TargetMask: [int](xref:microsoft.quantum.lang-ref.int)

