---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: Operación EstimateFrequencyA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 88f0a237975c158bffcc015f79d2134b210ce83b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728228"
---
# <a name="estimatefrequencya-operation"></a><span data-ttu-id="8331e-102">Operación EstimateFrequencyA</span><span class="sxs-lookup"><span data-stu-id="8331e-102">EstimateFrequencyA operation</span></span>

<span data-ttu-id="8331e-103">Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="8331e-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="8331e-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8331e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8331e-105">Dada una preparación que es adjointable y Measurement, calcula la frecuencia con la que la medida se realiza correctamente (devuelve `Zero` ) mediante la realización de un número determinado de pruebas.</span><span class="sxs-lookup"><span data-stu-id="8331e-105">Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="8331e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8331e-106">Input</span></span>

### <a name="preparation--qubit--unit-adj"></a><span data-ttu-id="8331e-107">Preparación: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8331e-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="8331e-108">Una operación adjointable $P $ que prepara un estado determinado $ \rho $ en su registro de entrada.</span><span class="sxs-lookup"><span data-stu-id="8331e-108">An adjointable operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="8331e-109">medida: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="8331e-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="8331e-110">Operación $M $ que representa la medida de interés.</span><span class="sxs-lookup"><span data-stu-id="8331e-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="8331e-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8331e-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8331e-112">El número de qubits en el que actúa la preparación y medición de cada uno.</span><span class="sxs-lookup"><span data-stu-id="8331e-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="8331e-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8331e-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8331e-114">El número de veces que se debe realizar la medida para calcular la frecuencia de interés.</span><span class="sxs-lookup"><span data-stu-id="8331e-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="8331e-115">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8331e-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8331e-116">Una estimación de $ \hat{p} $ de la frecuencia con la que $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ devuelve `Zero` , obtenida mediante el estimador binomial no sesgado $ \hat{p} = n \_ {\uparrow}/n \_ {\text{Measurements}} $, donde $n \_ {\uparrow} $ es el número de `Zero` resultados observados.</span><span class="sxs-lookup"><span data-stu-id="8331e-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="8331e-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8331e-117">Remarks</span></span>

<span data-ttu-id="8331e-118">En el caso de las operaciones de adjointable, se pueden realizar determinadas suposiciones, como llamar a la operación, se preparará el qubits exactamente en el mismo estado, lo que permite a los equipos de destino realizar algunas optimizaciones de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="8331e-118">For adjointable operations, certain assumptions can be made such like calling the operation will prepare the qubits to exactly the same state, which allow target machines to make some performance optimizations.</span></span>