---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: Operación TrotterArbitraryImplCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: bb93517a479ce344277bfe97d070e6630a8fccc0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840094"
---
# <a name="trotterarbitraryimplca-operation"></a>Operación TrotterArbitraryImplCA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementación recursiva de Trotter de orden uniforme: integrador de Suzuki.

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="order--int"></a>orden: [int](xref:microsoft.quantum.lang-ref.int)

Orden de Trotter-Suzuki integrador.


### <a name="nsteps--int"></a>nSteps: [int](xref:microsoft.quantum.lang-ref.int)

El número de operaciones que se van a descomponer en pasos temporales.


### <a name="op--intdoublet--unit--is-adj--ctl"></a>OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL

Una operación que acepta una entrada de índice (tipo `Int` ) y una entrada de hora (tipo `Double` ) y un registro de Quantum (tipo `'T` ) para la descomposición.


### <a name="stepsize--double"></a>Pasos: [Double](xref:microsoft.quantum.lang-ref.double)

Multiplicador en el tamaño de cada paso de la simulación.


### <a name="target--t"></a>destino: ' t

Registro de Quantum en el que actúan las operaciones.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo en el que debe actuar cada paso de tiempo; Normalmente, `Qubit[]` o `Qubit` .