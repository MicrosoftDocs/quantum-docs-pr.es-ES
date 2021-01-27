---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: Operación MultiplyAndAddByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: e4de934a5776e80dbf5f0d8334bf806e6a84b743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846512"
---
# <a name="multiplyandaddbymodularinteger-operation"></a>Operación MultiplyAndAddByModularInteger

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Realiza una multiplicación modular y agrega una constante de tipo entero en un registro qubit.

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

Implementa el mapa $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $ $ para un módulo determinado $N $, multiplicador constante $a $ y sumando $y $.

## <a name="input"></a>Entrada

### <a name="constmultiplier--int"></a>constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)

Entero $a $ que se va a agregar a cada etiqueta de estado de base.


### <a name="modulus--int"></a>módulo: [int](xref:microsoft.quantum.lang-ref.int)

El módulo $N $ que se toma la suma y la multiplicación con respecto a.


### <a name="multiplier--littleendian"></a>multiplicador: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Un registro de Quantum que representa un entero sin signo cuyo valor se va a agregar a cada etiqueta de estado de base de `summand` .


### <a name="summand--littleendian"></a>sumando: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Un registro de Quantum que representa un entero sin signo que se va a usar como destino para esta operación.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

- En el diagrama de circuitos y la explicación, consulte la figura 6 de la [Página 7 de arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)
- Esta operación corresponde a CMULT (a) MOD (N) en [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. aritmético. MultiplyAndAddPhaseByModularInteger](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)