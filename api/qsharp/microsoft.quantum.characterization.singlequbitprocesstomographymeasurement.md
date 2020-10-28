---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: Operación SingleQubitProcessTomographyMeasurement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 34e5143d5be316ee42a63124d35475949db0a692
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728168"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="ec5ec-102">Operación SingleQubitProcessTomographyMeasurement</span><span class="sxs-lookup"><span data-stu-id="ec5ec-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="ec5ec-103">Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="ec5ec-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="ec5ec-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ec5ec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ec5ec-105">Realiza una medición de Tomography de proceso de un solo qubit en el Pauli, dado un canal concreto de interés.</span><span class="sxs-lookup"><span data-stu-id="ec5ec-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="ec5ec-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ec5ec-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="ec5ec-107">Preparación: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="ec5ec-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="ec5ec-108">El elemento Pauli base $P $ en el que se va a preparar una qubit.</span><span class="sxs-lookup"><span data-stu-id="ec5ec-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="ec5ec-109">medida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="ec5ec-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="ec5ec-110">El elemento Pauli base $Q $ en el que se va a medir un qubit.</span><span class="sxs-lookup"><span data-stu-id="ec5ec-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="ec5ec-111">canal: [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [unidad](xref:microsoft.quantum.lang-ref.unit) qubit</span><span class="sxs-lookup"><span data-stu-id="ec5ec-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ec5ec-112">Un único canal de qubit $ \Lambda $ cuyo comportamiento se está calculando con el proceso Tomography.</span><span class="sxs-lookup"><span data-stu-id="ec5ec-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="ec5ec-113">Salida: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="ec5ec-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="ec5ec-114">El resultado `Zero` con la probabilidad $ $ \Begin{align} \Pr (\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right).</span><span class="sxs-lookup"><span data-stu-id="ec5ec-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="ec5ec-115">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="ec5ec-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="ec5ec-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ec5ec-116">Remarks</span></span>

<span data-ttu-id="ec5ec-117">La distribución de los resultados devueltos por esta operación es un caso especial de qubit de estado dos Tomography.</span><span class="sxs-lookup"><span data-stu-id="ec5ec-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="ec5ec-118">Permita que $ \rho = J (\Lambda)/$2 sea el estado Choi – Jamiłkowski para $ \Lambda $.</span><span class="sxs-lookup"><span data-stu-id="ec5ec-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="ec5ec-119">Después, la distribución anterior es idéntica a $ $ \begin{align} \Pr (\texttt{Zero} | \rho; M) = \operatorname{Tr} (M \rho), \end{align} $ $ Where $M = 2 (\boldone + P) ^ \mathrm{T}/2 \cdot (\boldone + Q)/$2 es la medida efectiva que corresponde a $P $ y $Q $.</span><span class="sxs-lookup"><span data-stu-id="ec5ec-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>