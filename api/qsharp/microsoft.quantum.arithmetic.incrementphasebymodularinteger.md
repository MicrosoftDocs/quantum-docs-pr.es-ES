---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: Operación IncrementPhaseByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 4ba35010d56ad01c73cb563646dc8150842da12e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846577"
---
# <a name="incrementphasebymodularinteger-operation"></a>Operación IncrementPhaseByModularInteger

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Realiza un incremento modular de un registro qubit por una constante de tipo entero.

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

Vamos `increment` a indicar $a $, `modulus` $N $ y un entero codificados en `target` por $y $.
A continuación, la operación realiza la transformación siguiente: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} los enteros se codifican en formato Little-endian en base QFT.

## <a name="input"></a>Entrada

### <a name="increment--int"></a>incremento: [int](xref:microsoft.quantum.lang-ref.int)

Incremento de entero $a $ que se va a agregar a $y $.


### <a name="modulus--int"></a>módulo: [int](xref:microsoft.quantum.lang-ref.int)

Entero $N $ que mods $y + a $.


### <a name="target--phaselittleendian"></a>destino: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Entero $y $ en formato Little-endian con codificación en fases `increment` al que se agrega $a $.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Supone que `target` tiene el bit más alto establecido en 0.
También se supone que el valor de destino es menor que $N $.

En el diagrama de circuitos y la explicación, vea la figura 5 de la [Página 5 de arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. aritmético. IncrementByModularInteger](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)