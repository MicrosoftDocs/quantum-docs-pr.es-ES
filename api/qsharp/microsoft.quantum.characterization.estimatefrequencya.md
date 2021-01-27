---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: Operación EstimateFrequencyA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 6cca8dff70283e0d69441db8a5b31fb5bfb3082a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839928"
---
# <a name="estimatefrequencya-operation"></a>Operación EstimateFrequencyA

Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una preparación que es adjointable y Measurement, calcula la frecuencia con la que la medida se realiza correctamente (devuelve `Zero` ) mediante la realización de un número determinado de pruebas.

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Entrada

### <a name="preparation--qubit--unit--is-adj"></a>Preparación: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ

Una operación adjointable $P $ que prepara un estado determinado $ \rho $ en su registro de entrada.


### <a name="measurement--qubit--__invalidresult__"></a>medida: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __no <Result> válido__ 

Operación $M $ que representa la medida de interés.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

El número de qubits en el que actúa la preparación y medición de cada uno.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

El número de veces que se debe realizar la medida para calcular la frecuencia de interés.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)

Una estimación de $ \hat{p} $ de la frecuencia con la que $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ devuelve `Zero` , obtenida mediante el estimador binomial no sesgado $ \hat{p} = n \_ {\uparrow}/n \_ {\text{Measurements}} $, donde $n \_ {\uparrow} $ es el número de `Zero` resultados observados.

## <a name="remarks"></a>Observaciones

En el caso de las operaciones de adjointable, se pueden realizar determinadas suposiciones, como llamar a la operación, se preparará el qubits exactamente en el mismo estado, lo que permite a los equipos de destino realizar algunas optimizaciones de rendimiento.