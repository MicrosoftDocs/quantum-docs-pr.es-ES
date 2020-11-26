---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: Operación ApplyObliviousAmplitudeAmplification
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: 9b0060201bcdae02a207362a753a0a403cdbb896
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191523"
---
# <a name="applyobliviousamplitudeamplification-operation"></a>Operación ApplyObliviousAmplitudeAmplification

Espacio de nombres: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Amplificación de amplitud de desconocen mediante la especificación de reflejos parciales.

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="phases--reflectionphases"></a>fases: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Fases de las reflexiones parciales


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Operador de reflexión sobre el estado de inicio del registro auxiliar


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Operador de reflexión sobre el estado de destino del registro auxiliar


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Unitario Oracle $O $ de tipo `ObliviousOracle` que actúa conjuntamente en los registros auxiliares y del sistema.


### <a name="auxiliaryregister--qubit"></a>auxiliaryRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro auxiliar


### <a name="systemregister--qubit"></a>systemRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro del sistema



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Dado un estado de inicio auxiliar determinado $ \ket{\text{Start}} \_ a $, un estado de destino auxiliar determinado $ \ket{\text{Target}} \_ a $ y cualquier estado del sistema $ \ket{\psi} \_ s $, supongamos que \begin{align} O\ket {\ Text {Start}} \_ a\ket {\ PSI} \_ s = \lambda\ket{\text{Target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \Ket{\text{Target} ^ \perp} a\cdots \end{align} para una unidad \_ de $U $.
Mediante una secuencia de reflexiones sobre los Estados de inicio y de destino en el registro auxiliar intercalados por las aplicaciones de `signalOracle` y su contiguo, se puede modificar la probabilidad de éxito de aplicar U.

En la mayoría de `auxiliaryRegister` los casos, se inicializa en el estado $ \ket{\text{Start}} \_ a $.

## <a name="references"></a>Referencias

Vea

- [ *D.W. Berry, AM Childs, r. Cleve, r. Kothari, R.D. Somma*](https://arxiv.org/abs/1312.1414) para la versión estándar.
  Vea
- [ *G.H. Low, I.L. Chuang*](https://arxiv.org/abs/1610.06546) para una generalización de reflexiones parciales.