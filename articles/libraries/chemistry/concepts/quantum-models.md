---
title: Modelos de Quantum para sistemas electrónicos | Microsoft Docs
description: Modelos de Quantum para sistemas electrónicos documentos conceptuales
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantummodels
ms.openlocfilehash: 45d134333c8a3c8937d206cb0a4a9cc6101a85df
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184158"
---
# <a name="quantum-models-for-electronic-systems"></a>Modelos de Quantum para sistemas electrónicos

Con el fin de simular sistemas electrónicos, primero es necesario especificar el Hamiltonian, que se puede encontrar mediante el procedimiento de cuantificación canónico descrito anteriormente.
En concreto, por $N _e $ electrones con Momentum $p _ i (en tres dimensiones) y masa $m _e $ y vectores de posición $x _ h $ junto con núcleos con cargos $Z _k e $ en las posiciones $y _k $, el operador Hamiltonian Lee \begin{Equation} \hat{H} = \sum\_{i = 1} ^ {N @no_ _t_1_ e} \frac{\hat{p}\_i ^ 2} {2m\_e} + \frac{1}{2}\sum\_{i\ne j} \frac{e ^ 2} {| \hat{x}\_i-\hat{x}\_j |}-\sum\_{i , k} \frac{Z\_ke ^ 2} {| \hat{x}\_i-{y}\_k |} + \frac{1}{2} \sum_{k\ne k '} \frac{Z\_kZ\_{k '} e ^ 2} {| y\_k-y\_k ' |}. \label{EQ: jamón} \end{Equation} los operadores de Momentum $ \hat{p}\_i ^ 2 $ se pueden ver en el espacio real como operadores de Laplacian, es decir, $ \hat{p}\_i ^ 2 =-\partial\_{x\_i} ^ 2-\partial\_{y\_i} ^ 2-\partial\_{z\_i} ^ 2 $.
Aquí hemos realizado la suposición de simplificación de que los núcleos están en reposo para la molécula.
Esto se conoce como la aproximación nacida Oppenheimer y tiende a ser válida para el espectro de energía de bajo consumo de $ \hat{H} $, ya que la masa de electrones es aproximadamente 1/1836 $ la masa de una Proton.
Este operador Hamiltonian se puede encontrar fácilmente escribiendo la energía de un sistema de $N\_e $ electrones y aplicando el proceso de cuantificación canónico descrito en [dinámica de Quantum](xref:microsoft.quantum.chemistry.concepts.quantumdynamics).

Para construir la representación de matriz de unitarios para $e ^ {-i\hat {H} t} $ necesitamos representar el operador $ \hat{H} $ como una matriz.
Para ello, es necesario elegir un sistema de coordenadas o una base para representar el problema en.
Por ejemplo, si $ \psi_j $ son un conjunto de funciones de base ortogonal para el $N _e $ electrones, podemos definir la matriz.

\begin{Equation} H\_{i, j} = \int\_{-\infty} ^ \infty\int\_{-\infty} ^ \infty \psi ^ {\*}\_i (x\_1) \hat{H} \psi\_j (x\_2) \dd ^ 3\_1 \dd ^ 3x\_2. \ etiqueta {EQ: discreteHam} \end{Equation}

Aunque en principio el operador $ \hat{H} $ no está enlazado y no actúa en un espacio dimensional finito, la matriz con los elementos $H\_\{i, j\}$ anteriores sí lo hace.
Esto significa que los errores se producen por la selección de un conjunto de base demasiado pequeño. sin embargo, la selección de una base grande puede hacer que la simulación de la dinámica química no sea práctica.
Por esta razón, es fundamental elegir una base que pueda representar el problema de forma concisa para resolver el problema de la estructura electrónica.

Hay muchas bases adecuadas que se pueden usar y la elección de una buena base para adaptarse al problema es gran parte del arte de la química de Quantum.
Es posible que los conjuntos más sencillos de estas bases sean Slater-Type-orbital (ALM), que son soluciones (ortogonales) a la ecuación Schrödinger (es decir, eigenfunctions de $ \hat{H} $) para átomos similares a hidrógeno.
Se pueden usar otros conjuntos, como ondas de plano o órbitas de espacio en tiempo real, y, para obtener más detalles, se hace referencia al lector de curiosidades en el texto estándar ["teoría de la estructura electrónica molecular"](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572) de Helgaker.

Aunque los Estados usados en el modelo anterior pueden parecer arbitrarios, la mecánica de Quantum impone restricciones en los Estados que se pueden encontrar por naturaleza.
En concreto, todos los Estados electrónicos de Quantum válidos deben ser antisimétricos en el intercambio de etiquetas de electrones.
Es decir, si $ \psi (x_1, x_2) $ eran la función de onda para el estado de cuanto conjunto de dos electrones, debemos tener $ $ \psi (x_1, x_2) =-\psi (x_2, x_1).
$ $ El principio de exclusión de Pauli, que prohíbe que dos electrones se encuentren en el mismo estado de Quantum, es fascinante, una consecuencia directa de esta ley como puede ser intuitiva del hecho de que se intercambian dos electrones que se encuentran en la misma posición $ \psi (x_1, x_1) \mapsto \psi ( x_1, x_1) \ne-\psi (x_1, x_1) $ a menos que $ \psi (x_1, x_1) = 0 $.
Por lo tanto, se deben elegir los Estados iniciales para obedecer esta propiedad antisimetría y, a su vez, nunca tener dos electrones en el mismo estado al mismo tiempo.
Esto es fundamental para la estructura electrónica porque prohíbe que varios electrones estén en el mismo estado y, a su vez, permite que los equipos Quantum usen un solo bit de Quantum para almacenar el número de electrones en un estado de Quantum determinado.

Aunque los mecanismos de Quantum se pueden simular en un equipo Quantum mediante la discretización de estos Estados, la mayor parte del trabajo en el campo ha eschewed este enfoque porque requiere muchos qubits para almacenar los Estados y necesita un procedimiento de preparación de estado complicado para preparar un estado inicial antisimétrico.
Afortunadamente, estos problemas se pueden sidestepped mediante la visualización del problema de simulación desde una perspectiva diferente.
