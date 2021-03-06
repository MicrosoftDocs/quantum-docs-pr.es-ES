---
uid: Microsoft.Quantum.AmplitudeAmplification
title: Espacio de nombres Microsoft. Quantum. AmplitudeAmplification
ms.date: 1/23/2021 12:00:00 AM
ms.topic: managed-reference
qsharp.kind: namespace
qsharp.name: Microsoft.Quantum.AmplitudeAmplification
qsharp.summary: This namespace contains functions and operations for performing amplitude amplification.
ms.openlocfilehash: a014f923de62c5e660c1c0fc839fbe60e80f8ba9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845828"
---
# <a name="microsoftquantumamplitudeamplification-namespace"></a>Espacio de nombres Microsoft. Quantum. AmplitudeAmplification

Este espacio de nombres contiene funciones y operaciones para realizar amplificación de amplitud.



## <a name="description"></a>Descripción

La amplificación de amplitud desconocen con reflejos parciales es la forma más general de amplificación de amplitud implementada aquí.

Esto se llama a través de la operación AmpAmpObliviousByReflectionPhases.

Tiene dos registros: `ancillaRegister` y `systemRegister` .

Esto acepta dos Oracle para estas reflexiones de tipo `ReflectionOracle` que solo actúan en el `ancillaRegister` registro.

Esto acepta una amplificación de amplitud de Oracle especial a desconocen de tipo `ObliviousOracle` que actúa conjuntamente en ambos registros.

Se supone que el estado de entrada `ancillaRegister` es el único $-$1 eigenstate del primer operador de reflexión $I-2 \ les {s} \ Bra {s} $.

Las reflexiones sobre un estado de cuanto de destino se suelen implementar suponiendo el acceso a un Oracle que preparan ese estado de la base de cálculo $ \ket{0\cdots 0} $.

Nuestra Convención para estos Oracle requiere dos registros: un registro de un solo qubit `flagQubit` y un registro para todo lo demás en el registro de ancillaRegister.

Oracle de tipo `StateOracle` actúa conjuntamente en ambos registros para crear el estado de destino marcado por $ \ket {1} $ en el `flagQubit` registro con alguna amplitud real.

La `ReflectionOracle` operación genera la reflexión sobre el estado de esta marca `TargetStateReflectionOracle` .

La reflexión `ReflectionOracle` sobre el estado de entrada en `ancillaRegister` se genera mediante el StateOracle de inversión y, a continuación, refleja aproximadamente $ \ket{0\cdots 0} $ con ReflectionStart ().

La Oracle de tipo `DeterministicStateOracle` actúa en los `qubitState` registros para crear el estado de destino exactamente sin ninguna marca.

`AmpAmpObliviousByOraclePhases` es una versión de amplificación de amplitud de desconocen que acepta Oracle `StateOracle` y `ObliviousOracle` en lugar de reflejos.

Tenga en cuenta que la amplificación de amplitud es un caso especial de amplificación de amplitud de desconocen donde `ObliviousOracle` es el operador de identidad y no hay ningún qubits del sistema, es decir, `systemRegister` está vacío.

Esto se llama a través de la operación `AmpAmByReflectionPhases` y `AmpAmpByOraclePhases` .

La función AmpAmpPhasesStandard proporciona las fases para las reflexiones parciales en el caso estándar de búsqueda de Grover.

Por ejemplo, tenemos las siguientes dependencias: AmpAmpByOracle-> AmpAmpByOraclePhases-> AmpAmpObliviousByOraclePhases-> AmpAmpObliviousByReflectionPhases.