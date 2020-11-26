---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: Operación RippleCarryAdderCDKM
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: b08d8823fd539263205aca1ee15ee69adcb163b7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222106"
---
# <a name="ripplecarryaddercdkm-operation"></a>Operación RippleCarryAdderCDKM

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Agregación reversible, en contexto, de dos enteros.

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

Dados dos $n enteros de $ bits codificados en registros de LittleEndian `xs` y `ys` , y un transporte de qubit, la operación calcula la suma de los dos enteros donde se conservan los bits $n $ menos significativos del resultado en `ys` y el bit de transporte es XORed a qubit `carry` .

## <a name="input"></a>Entrada

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registra la codificación del primer entero sumando.


### <a name="ys--littleendian"></a>calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registra la codificación del segundo entero sumando, se modifica para contener los n bits menos significativos de la suma.


### <a name="carry--qubit"></a>transporte: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Transportar qubit, es XORed con el bit más significativo de la suma.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Esta operación tiene la misma funcionalidad que RippleCarryAdderD, pero solo usa un qubit auxiliar en lugar de $n $.

## <a name="references"></a>Referencias

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "un nuevo circuito de adición del transporte de onda de Quantum", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1