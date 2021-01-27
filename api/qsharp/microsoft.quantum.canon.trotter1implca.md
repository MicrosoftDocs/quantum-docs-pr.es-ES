---
uid: Microsoft.Quantum.Canon.Trotter1ImplCA
title: Operación Trotter1ImplCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter1ImplCA
qsharp.summary: Implementation of the first-order Trotter–Suzuki integrator.
ms.openlocfilehash: 6de4b6e7a34d66037d83a6e2bd5821402207c743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840105"
---
# <a name="trotter1implca-operation"></a>Operación Trotter1ImplCA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementación del Trotter de primer orden: integrador de Suzuki.

```qsharp
operation Trotter1ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

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

## <a name="example"></a>Ejemplo

Los siguientes son equivalentes:

```qsharp
op(0, deltaT, target);
op(1, deltaT, target);
```

y

```qsharp
Trotter1ImplCA((2, op), deltaT, target);
```