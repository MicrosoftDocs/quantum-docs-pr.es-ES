---
title: Dynamics de Quantum
description: Obtenga información sobre las similitudes y las diferencias entre las dinámicas de Quantum y la dinámica.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantumdynamics
no-loc:
- Q#
- $$v
ms.openlocfilehash: e63ec497f2a7747e172d5fbdc249fe4064c482b6
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869501"
---
# <a name="quantum-dynamics"></a>Dynamics de Quantum

La mecánica de Quantum es en gran medida el estudio de la dinámica de Quantum, que busca comprender cómo un estado de Quantum inicial $ \ket{\psi (0)} $ varía con el tiempo (consulte los [documentos conceptuales](xref:microsoft.quantum.concepts.dirac) sobre el procesamiento de quantums para obtener más información sobre la notación de Dirac).
En concreto, dada esta condición inicial, un estado de Quantum, una hora de evolución y una especificación del sistema dinámico Quantum, se busca un estado de Quantum $ \ket{\psi (t)} $.
Antes de continuar con la explicación de la dinámica de Quantum, es útil volver atrás y pensar en la dinámica clásica, ya que proporciona información sobre cómo las mecánicas de Quantum realmente no son las distintas de las dinámicas clásicas.

En la dinámica clásica, sabemos de la segunda ley de movimiento que la posición de una partícula evoluciona según $F (x, t) = MA = m\frac {\ DD ^ 2} {\dd t ^ 2} {x} (t) $, donde $F (x, t) $ es la fuerza, $m $ es la masa y $a $ es la aceleración.
A continuación, dada una posición inicial $x (0) $, el tiempo de evolución $t $ y la descripción de las fuerzas que actúan en la partícula, podemos encontrar $x (t) $ resolviendo la ecuación diferencial proporcionada por las ecuaciones de Newton para $x (t) $.
Especificar las fuerzas de este modo es un poco problemático.
Por lo tanto, a menudo expresamos las fuerzas en términos de la energía potencial del sistema, que nos proporciona $-\ partial_x V (x, t) = m \frac{\dd ^ 2} {\dd t ^ 2} {x} (t) $.
Por lo tanto, en el caso de una partícula, la dinámica del sistema solo se especifica mediante la función de energía potencial, la masa de partículas y el tiempo de evolución.

A menudo se introduce un lenguaje más amplio para la dinámica clásica que va más allá $F = MA $.
Una formulación, que es especialmente útil en la mecánica de Quantum, es la mecánica Hamiltonian.
En las mecánicas de Hamiltonian, la energía total de un sistema y las posiciones (generalizadas) y Momentum proporcionan toda la información necesaria para describir el movimiento de un objeto clásico arbitrario.
En concreto, deje que $f (x, p, t) $ sea una función de las posiciones generalizadas $x $ y Momentum $p $ de un sistema y deje que $H (x, p, t) $ sea la función Hamiltonian.
Por ejemplo, si tomamos $f (x, p, t) = x (t) $ y $H (x, p, t) = p ^ 2 (t)/2m-V (x, t) $, recuperaremos el caso anterior de Newtonian Dynamics.
Por lo general, tenemos que \begin{align} \frac{d}{DT} f &= \ partial_t f-(\ partial_x H \ partial_p f + \ partial_p H \ partial_x f) \\ \\ & \defeq \ partial_t f + \\ {f, H \\ }.
\end{align} aquí $ \\ {f, H \\ } $ se denomina [corchete de Poisson](https://en.wikipedia.org/wiki/Poisson_bracket) y aparece omnipresentemente en la dinámica clásica debido al rol central que desempeña en la definición de Dynamics.

La dinámica de Quantum se puede describir usando exactamente el mismo lenguaje.
Hamiltonian, o total Energy, especifica completamente la dinámica de cualquier sistema Quantum cerrado.
Sin embargo, hay algunas diferencias sustanciales entre las dos teorías.
En mecánicas clásicas $x $ y $p $ son solo números, mientras que en la mecánica de Quantum no son.
En realidad, ni siquiera Commute: $xp \ne PX $.

El concepto matemático adecuado para describir estos objetos que no son de trabajo es un operador, que en los casos en los que $x $ y $p $ solo pueden tomar un conjunto discreto de valores coincide con el concepto de una matriz.
Por lo tanto, para simplificar, asumimos que el sistema Quantum es finito para que se pueda describir mediante [vectores y matrices](xref:microsoft.quantum.concepts.vectors).
Además, es necesario que estas matrices sean Hermitian (lo que significa que la transjugada de la matriz es la misma que la matriz original).
Esto garantiza que el vectores propios de las matrices sea de valor real; condición que imponemos para asegurarse de que, cuando medimos una cantidad como la posición en la que no obtenemos un número imaginario.

Del mismo modo que los análogos de Position y Momentum en la mecánica de Quantum deben reemplazarse por operadores, la función Hamiltonian debe reemplazarse de manera similar por un operador.
Por ejemplo, en el caso de una partícula en el espacio disponible, tenemos $H (x, p) = p ^ 2/2m $ mientras que en la mecánica de Quantum el operador Hamiltonian $ \hat{H} $ es $ \hat{H} = \hat{p} ^ 2/2m $, donde $ \hat{p} $ es el operador Momentum.
Desde esta perspectiva, pasar de una dinámica de clásica a la de Quantum solo implica reemplazar las variables utilizadas en la dinámica ordinaria con operadores.
Una vez que se ha construido el operador Hamiltonian mediante la traducción de la Hamiltonian clásica normal sobre el lenguaje Quantum, podemos expresar la dinámica de una cantidad mecánica de cuanto (es decir, el operador mecánico mecánico) $ \hat{f} (t) $ Via \begin{align} \frac{d}{DT} \hat{f} = \ partial_t \hat{f} + [\hat{f}, \hat{H}], \end{align} donde $ [f, H] = fH-HF $ se conoce como commutator
Esta expresión es exactamente igual a la expresión clásica que se indicó anteriormente, con la diferencia de que el corchete de Poisson $ \\ {f, H \\ } $ se reemplaza por el commutator entre $f $ y $H $.
Este proceso de tomar un Hamiltonian clásico y usarlo para buscar un Quantum Hamiltonian se conoce en la jerga de Quantum como cuantificación canónica.

¿Qué operadores $f $ le interesan más?  La respuesta a esto depende del problema que se desea resolver.
Quizás la cantidad más útil para encontrar es el operador de estado de Quantum, que se explica en la documentación conceptual anterior que se puede usar para extraer todo lo que nos gustaría obtener información sobre la dinámica.
Después de hacer esto (y simplificar el resultado en caso de que uno tenga un estado puro), se encuentra la ecuación Schrödinger para el estado de Quantum \begin{align} i \ partial_t \ket{\psi (t)} = \hat{H} (t) \ket{\psi (t)}.
\end{align}

Esta ecuación, aunque quizás sea menos intuitiva que la anterior, proporciona quizás la expresión más sencilla para entender cómo simular la dinámica de Quantum en un Quantum o en un equipo clásico.
Esto se debe a que la solución para la ecuación diferencial se puede expresar de la siguiente forma (en el caso en el que Hamiltonian sea constante en $t $) \begin{align} \ket{\psi (t)} = e ^ {-iHt} \ket{\psi (0)}.
\end{align} aquí $e ^ {-iHt} $ es una matriz de unitarios.
Esto significa que existe un circuito de Quantum que se puede diseñar para que lo lleve a cabo, ya que los equipos Quantum pueden aproximar estrechamente cualquier matriz de unitario.
Esta acción de buscar un circuito de Quantum para implementar el operador de evolución de tiempo de Quantum $e ^ {-iHt} $ es lo que se denomina a menudo simulación de Quantum o en una simulación de Quantum dinámicas determinada.
