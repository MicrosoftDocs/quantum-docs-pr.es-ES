---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Operación IncrementByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 271033b32b0de6cf600dca82126dab19c2bb4f5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731501"
---
# <a name="incrementbymodularinteger-operation"></a>Operación IncrementByModularInteger

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Configura [](https://nuget.org/packages/)


Realiza un incremento modular de un registro qubit por una constante de tipo entero.

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Descripción

Vamos `increment` a indicar $a $, `modulus` $N $ y un entero codificados en `target` por $y $.
A continuación, la operación realiza la transformación siguiente: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} los enteros se codifican en formato Little-Endian.

## <a name="input"></a>Entrada

### <a name="increment--int"></a>incremento: [int](xref:microsoft.quantum.lang-ref.int)

Incremento de entero $a $ que se va a agregar a $y $.


### <a name="modulus--int"></a>módulo: [int](xref:microsoft.quantum.lang-ref.int)

Entero $N $ que mods $y + a $.


### <a name="target--littleendian"></a>destino: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Entero $y $ en el `LittleEndian` formato `increment` al que se agrega $a $.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Supone que el valor inicial del destino es menor que $N $ y que el incremento $a $ es menor que $N $.
Tenga en cuenta que <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implementa la misma operación de la `PhaseLittleEndian` base.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. aritmético. IncrementPhaseByModularInteger](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)