---
title: Descripción de la computación cuántica
description: ¿Qué son los equipos cuánticos y cómo usan los principios de la mecánica cuántica?
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.understanding
no-loc:
- Q#
- $$v
ms.openlocfilehash: 214fe809aaeba759005fa76ba3615f376d402bc9
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866968"
---
# <a name="understanding-quantum-computing"></a>Descripción de la computación cuántica

La computación cuántica usa los principios de la mecánica cuántica para procesar la información. Por este motivo, la computación cuántica requiere un enfoque diferente de la computación clásica.  Un ejemplo de esta diferencia es el procesador que usan los equipos cuánticos.  Los equipos clásicos usan los conocidos chips de silicio, mientras que los equipos cuánticos usan materiales cuánticos como átomos, iones o electrones.  

El material cuántico se comporta de acuerdo con las leyes de las mecánicas cuántica, lo que permite aprovechar conceptos como la computación probabilística, la superposición y el entrelazamiento. Estos conceptos son la base de los algoritmos cuánticos, que aprovechan la eficacia de la computación cuántica para solucionar problemas complejos. En este artículo se describen algunos de los conceptos esenciales de la mecánica cuántica en la que se basa la computación cuántica.

## <a name="a-birds-eye-view-of-quantum-mechanics"></a>Un vistazo rápido a la mecánica cuántica

La mecánica cuántica, también llamada teoría cuántica, es una rama de la física que se ocupa de las partículas en los niveles atómico y subatómico. Sin embargo, en el nivel cuántico, no se aplican muchas de las leyes de la mecánica que se dan por hechas. La superposición, la medición cuántica y el entrelazamiento son tres fenómenos fundamentales de la computación cuántica.  

### <a name="superposition-vs-binary-computing"></a>Superposición frente a computación binaria

Imagine que está haciendo ejercicio en su salón. Gira completamente a la izquierda y, a continuación, gira completamente a la derecha. Ahora, gire a la izquierda y a la derecha al mismo tiempo. No se puede (no sin dividirse en dos, al menos).  Obviamente, no puede estar en ambos estados a la vez: no puede estar mirando a la izquierda y a la derecha al mismo tiempo.

Sin embargo, si fuera una partícula cuántica, tendría una probabilidad determinada de estar *mirando a la izquierda* y una probabilidad determinada de estar *mirando a la derecha* debido a un fenómeno conocido como **superposición** (o también **coherencia**).

Una partícula cuántica, como el electrón, tiene sus propias propiedades "orientadas a la izquierda o a la derecha", por ejemplo el **espín**, que se conoce como arriba o abajo o, en el ámbito de la informática binaria clásica, simplemente 1 o 0. Cuando una partícula cuántica está en un estado de superposición, se trata de una combinación lineal de un número infinito de estados entre 1 y 0, pero no se sabe cuál será hasta que realmente se mire, lo que nos lleva al siguiente fenómeno, la **medición cuántica**.

### <a name="quantum-measurement"></a>Medición cuántica

Ahora, supongamos que un amigo quiere hacerle una foto mientras hace ejercicio. Lo más probable es que obtenga una imagen borrosa de usted girando, en algún lugar entre la izquierda y la derecha.

Pero si fuera un objeto cuántico, se produce algo interesante. Sea cual sea el lugar en el que se encuentre cuando le hagan la foto, siempre se mostrará totalmente girado a la izquierda o a la derecha, sin nada en medio.

Esto se debe a que la acción de observar o medir un objeto cuántico **colapsa** el estado de superposición (lo que también se conoce como **decoherencia**) y la partícula toma un estado binario clásico de 1 o 0.

Este estado binario es útil, porque en computación se pueden hacer muchas cosas con 1 y 0. Sin embargo, una vez que una partícula cuántica se ha medido y ha colapsado, permanece en ese estado siempre (al igual que la imagen) y siempre será 1 o 0. Sin embargo, como veremos más adelante, en computación cuántica hay operaciones que pueden "restablecer" una partícula de nuevo al estado de superposición para poder usarla de nuevo para los cálculos cuánticos.

### <a name="entanglement"></a>Entrelazamiento

El fenómeno más interesante de la mecánica cuántica probablemente sea la capacidad que dos o más partículas cuánticas tienen de **entrelazarse**. Cuando los objetos se entrelazan, forman un único sistema, de modo que el estado cuántico de cualquiera de las partículas no se puede describir independientemente del estado cuántico de las demás. Esto significa que cualquier operación o proceso que se aplique a una partícula se correlaciona también con las demás.

Además de esta interdependencia, las partículas pueden mantener esta conexión, aunque se separen a distancias increíblemente grandes, incluso a años luz. Los efectos de la medición cuántica también se aplican a las partículas entrelazadas, de modo que cuando se mide una partícula y colapsa, la otra partícula también colapsa. Dado que hay una correlación entre los cúbits entrelazados, al medir el estado de un cúbit se obtiene información sobre el estado del otro cúbit; esta propiedad concreta es muy útil en la computación cuántica.

### <a name="qubits-and-probability"></a>Cúbits y probabilidad

Los equipos clásicos almacenan y procesan información en bits, que pueden tener un estado de 1 o 0, pero nunca ambos. El equivalente en la computación cuántica es el **cúbit**, que representa el estado de una partícula cuántica. Debido a la superposición, cúbits puede ser 1 o 0 o cualquier cosa entre ellos. En función de su configuración, un cúbit tiene una determinada *probabilidad* de colapsar en 1 o 0. La probabilidad de que un cúbit colapse en una u otra forma está determinada por la **interferencia cuántica**. 

¿Recuerda el amigo que le estaba haciendo la foto? Supongamos que tiene unos filtros especiales en su cámara llamados filtros de *interferencia*. Si selecciona el filtro *70/30* y empieza a hacer fotos, en el 70 % de ellas se le verá a la izquierda y, en un 30 % se le verá a la derecha. El filtro ha interferido con el estado normal de la cámara y ha influido en la probabilidad de su comportamiento.

Del mismo modo, la interferencia cuántica afecta al estado de un cúbit e influye en la probabilidad de un determinado resultado durante la medición. En este estado probabilístico es donde destacan las capacidades de la informática cuántica.

Por ejemplo, con dos bits en un equipo clásico, cada bit puede almacenar 1 o 0, por lo que juntos puede almacenar cuatro valores posibles: **00**, **01**, **10** y **11**, pero solo uno de ellos a la vez. Sin embargo, con dos cúbits en superposición, cada cúbit puede ser 1 o 0 o *ambos*, por lo que se pueden representar los mismos cuatro valores simultáneamente. Con tres cúbits, se pueden representar ocho valores, con cuatro cúbits, puede representar 16 valores, etc.

## <a name="summary"></a>Resumen

Estos conceptos solo una pequeñísima muestra de la mecánica cuántica, pero son conceptos importantes que hay que conocer para trabajar con la computación cuántica.

- **Superposición**: capacidad de las partículas cuánticas para ser una combinación de todos los estados posibles.
- **Medición cuántica**: acto de observar una partícula cuántica en superposición y producir uno de los estados posibles.
- **Entrelazamiento**: capacidad de las partículas cuánticas para correlacionar entre sí los resultados de la medición.
- **Cúbit**: unidad básica de información en la computación cuántica. Un cúbit representa una partícula cuántica en superposición de todos los estados posibles.
- **Interferencia**: comportamiento intrínseco de un cúbit debido a la influencia de la superposición en la probabilidad de que colapse en una forma u otra.

## <a name="next-steps"></a>Pasos siguientes

[Simuladores y equipos cuánticos](xref:microsoft.quantum.overview.simulators)
