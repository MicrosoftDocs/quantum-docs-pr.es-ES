---
uid: Microsoft.Quantum.Canon.AndLadder
title: Operación AndLadder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: d44c462c7a9fc9521bdecfe2ca7f607e90482baf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845220"
---
# <a name="andladder-operation"></a>Operación AndLadder

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Realiza una "y escalera" controlada en un registro de qubits de destino.

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj
```


## <a name="description"></a>Descripción

Esta operación aplica una transformación descrita por la siguiente asignación de la base de cálculo: $ $ \begin{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \dots, y \_ {n-1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2), \dots, y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}, \end{align} $ $ Where $ \ket{x \_ 1, \dots, x \_ n} $ hace referencia a los Estados de base de cálculo de `controls` , y donde $ \ket{y \_ 1, \dots, y \_ {n-1}} $ hace referencia a los Estados de base de cálculo de `targets` .

## <a name="input"></a>Entrada

### <a name="ccnot--ccnotop"></a>ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

La puerta CCNOT que se va a usar para la construcción.


### <a name="controls--qubit"></a>controles: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro de qubits que se va a usar como control para la escalera y.
Esta operación deja Estados de base de cálculo `controls` invariable.
La longitud de `controls` debe ser al menos 2 y debe ser igual a uno más la longitud de `targets` .


### <a name="targets--qubit"></a>destinos: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

La longitud de `targets` debe ser al menos 1 y igual a la longitud de `controls` menos uno.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

- Se utiliza como parte de <xref:microsoft.quantum.canon.applymulticontrolledc> y <xref:microsoft.quantum.canon.applymulticontrolledca> .
- En el diagrama de explicación y circuito, consulte la figura 4,10, sección 4,3 de Nielsen & Chuang.

## <a name="references"></a>Referencias

- [*Michael A. Nielsen, Isaac L. Chuang*, cálculo de Quantum e información de Quantum](http://doi.org/10.1017/CBO9780511976667)