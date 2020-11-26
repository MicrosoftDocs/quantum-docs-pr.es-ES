---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: Operación ApplyOuterTTKAdder
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: aed15a4d1f3ca7121d6da665f5c08442fd495619
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190622"
---
# <a name="applyouterttkadder-operation"></a>Operación ApplyOuterTTKAdder

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementa la operación externa para que RippleCarryAdderTTK conjugado la operación interna para construir el agregador completo.

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registra la codificación del primer entero sumando entrada en RippleCarryAdderTTK.


### <a name="ys--littleendian"></a>calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registra la codificación del segundo entero sumando entrada en RippleCarryAdderTTK.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referencias

- Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Additions de Quantum y ramificación sin límite", información de Quantum y cálculo, Vol. 10, 2010.
  https://arxiv.org/abs/0910.2530