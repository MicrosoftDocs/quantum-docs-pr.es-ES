---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: Operación EstimateFrequency
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 83589637a7bfa328812207271844411f57d42097
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728235"
---
# <a name="estimatefrequency-operation"></a>Operación EstimateFrequency

Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)

Configura [](https://nuget.org/packages/)


Dada una preparación y medida, calcula la frecuencia con la que la medida se realiza correctamente (devuelve `Zero` ) mediante la realización de un número determinado de pruebas.

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Entrada

### <a name="preparation--qubit--unit"></a>Preparación: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)> 

Operación $P $ que prepara un estado determinado $ \rho $ en su registro de entrada.


### <a name="measurement--qubit--__invalidresult__"></a>medida: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __no <Result> válido__ 

Operación $M $ que representa la medida de interés.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

El número de qubits en el que actúa la preparación y medición de cada uno.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

El número de veces que se debe realizar la medida para calcular la frecuencia de interés.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)

Una estimación de $ \hat{p} $ de la frecuencia con la que $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ devuelve `Zero` , obtenida mediante el estimador binomial no sesgado $ \hat{p} = n \_ {\uparrow}/n \_ {\text{Measurements}} $, donde $n \_ {\uparrow} $ es el número de `Zero` resultados observados.

Esto es especialmente importante en las máquinas de destino que respetan las limitaciones físicas, de modo que no se pueden medir las probabilidades.