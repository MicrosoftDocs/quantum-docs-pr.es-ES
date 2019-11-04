---
title: Pila de software | Microsoft Docs
description: Pila de software
author: QuantumWriter
uid: microsoft.quantum.concepts.software-stack
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f97dfacf6cde5fa92e1f368efaae36554a5c944d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184736"
---
# <a name="software-stack-for-quantum-computing"></a>Pila de software para la informática Quantum
Normalmente, cuando pensamos en un equipo en el que se crea un único dispositivo que ejecuta una aplicación, los entornos informáticos modernos son mucho más complejos y avanzados. La aplicación con la que interactuamos normalmente se sitúa en varias capas de software que proporcionan la ejecución de la aplicación hasta el nivel de hardware. Estos niveles de software son necesarios para abstraer el desarrollo de una solución de aplicación de la complejidad subyacente del sistema informático completo. Si un desarrollador tuviera que pensar en buses, arquitecturas de la memoria caché, protocolos de comunicación y mucho más al escribir una aplicación sencilla de smartphone, la tarea sería mucho más compleja.  El concepto de una *pila de software* se desarrolló en informática clásica para solucionar estos problemas.  Tomando como referencia el concepto clásico, una pila de software también es una parte fundamental de la visión detrás de Quantum Computing con preguntas y respuestas.

## <a name="conventional-stack"></a>Pila convencional
La idea clave detrás de una pila de software es la recursividad.  Consta de varios niveles anidados de interfaces que abstraen los detalles de los niveles inferiores del dispositivo del desarrollador.  Por ejemplo, una pila de software utilizada comúnmente implica ejecutar ASP.NET (un lenguaje de programación), sobre SQL Server (un sistema de administración de bases de datos relacionales), que se ejecuta sobre Internet Information Services (un servidor Web), que se ejecuta sobre Windows Server (un sistema operativo), que controla el hardware del equipo.  Al examinar el software como una jerarquía, se puede escribir software en ASP.NET sin necesidad de conocer los detalles de bajo nivel de todo el software que se encuentra debajo de él.

## <a name="quantum-stack"></a>Pila Quantum

La pila de software de Quantum Computing no es diferente en principio y, en la práctica, funciona en un nivel inferior que las pilas tradicionales.  ¿En qué se parece una pila Quantum?  Un equipo Quantum no sustituye a los equipos tradicionales (a menudo denominados clásico).  De hecho, los equipos Quantum funcionarán casi con certeza en conjunto con equipos clásicos para solucionar problemas de cálculo.  En parte, esto se produce debido a la fragilidad de los datos Quantum.  Los datos de Quantum son tan frágiles que, si se observan incluso, se daña la información que se observa.  Por lo tanto, los equipos Quantum deben diseñarse con corrección de errores Quantum en mente para que las interacciones aisladas de su entorno físico no dañen accidentalmente la información y el cálculo. Por esta razón, un destino natural de Q # es un equipo Quantum corregido por errores (a menudo denominado equipo Quantum *tolerante a errores* ) que acepta una lista de instrucciones Quantum (denominadas puertas o operaciones de puerta) y aplica las instrucciones al Quantum. datos almacenados en él.  Tenga en cuenta que si el número de operaciones qubits y de puerta en un algoritmo o un programa Quantum es lo suficientemente pequeño, puede que la corrección de errores no sea absolutamente necesaria.  Sin embargo, a medida que aumenta el número de operaciones de qubits y de puerta, se trata de un requisito, por lo que diseñamos nuestra pila de software y Q # para controlar de forma acertada y eficaz la corrección de errores y habilitar la informática Quantum escalable y tolerante a errores.

### <a name="error-correction"></a>Corrección de errores
La corrección de errores requiere que se ejecute un equipo clásico rápido y confiable junto con el equipo Quantum para corregir los errores que aparecen en el cálculo de Quantum.  En la práctica, es posible que se necesiten componentes como matrices de puertas programables por campo (FPGA) o procesadores de cryogenic rápido para identificar y corregir los errores más rápido que en el equipo Quantum.  Como resultado, un equipo Quantum es una máquina híbrida formada por varios dispositivos computacionales diferentes que funcionan a través de una amplia gama de temperaturas.  Por esta razón, es mucho más útil pensar en la programación de un equipo Quantum a través de la lente de una pila de software, ya que hay muchos niveles de hardware y software (clásico y Quantum) necesarios para lograr en última instancia la implementación de un Quantum. en un equipo Quantum.

### <a name="quantum-conceptual-stack"></a>Pila conceptual de Quantum
A continuación se muestra una pila conceptual que ilustra el flujo funcional de la factorización 8704143553785700723 en un entorno de proceso de Quantum Computing:

![Pila de software](~/media/concepts_stack.png)

### <a name="specification-and-algorithm"></a>Especificación y algoritmo
Hay varias fases generales de programación de un cálculo de Quantum.  La primera fase, y posiblemente la más difícil, consiste en especificar el problema que desea resolver.  En este caso, el problema es factorizar el número 8704143553785700723 en un producto de dos números primos.  El paso siguiente implica diseñar un algoritmo para resolver este problema de cálculo.  En este caso, se puede usar el algoritmo de factor Quantum famoso de mé para encontrar los factores.  Este algoritmo se expresa en Q # y, a continuación, una secuencia de operaciones Quantum es una salida que podría ejecutarse en un equipo Quantum sin errores ideal.  

### <a name="physical-gates"></a>Puertas físicas
En este ejemplo, supongamos que la naturaleza no es tan amable como para proporcionar un equipo Quantum sin errores, por lo que el paso siguiente toma las operaciones emitidas por Q # y las traduce mediante plantillas especificadas por el método de corrección de errores de Quantum elegido en las puertas físicas que el hardware básico se puede ejecutar.  Este proceso implica reemplazar todos los qubit lógicos descritos en el modelo anterior por un host de qubits físicos que se usan para almacenar y proteger la información dentro de una sola qubit de forma redundante que puede resistir los errores locales del componente físico qubits el tiempo suficiente para detectar y corregir estos errores.  Del mismo modo que el qubits lógico descrito por el código de Q # debe reemplazarse por muchos qubits físicos, de forma similar, cada una de las puertas de Quantum descritas en la salida debe traducirse en una secuencia de puertas físicas que actúan sobre el qubits físico.  Por esta razón, la salida de Q # rara vez es el destino final de la informática Quantum y se necesitan más niveles de abstracción para ejecutar el código en el hardware de un modo desconocen.

### <a name="control-computer"></a>Controlar equipo
La secuencia de la puerta física se carga a continuación en un equipo normal que envía estas instrucciones a un equipo de control que interactúa directamente con el equipo Quantum.  Esta capa dentro de la pila de software suele controlarse mediante software de control experimental como [QCoDeS](http://qcodes.github.io/Qcodes/).

### <a name="interface-computer"></a>Equipo de la interfaz
El paso final de este proceso implica que el equipo de la interfaz streaming primero las puertas según sea necesario a un equipo de control rápido. A continuación, el equipo de control rápido aplica los voltajes necesarios (comúnmente denominados pulsos) para implementar las puertas necesarias en qubits. Esto se debe hacer al corregir los errores que se observan a través de la corrección de errores de Quantum.  Es posible que se necesiten cryogenic FPGA u otro hardware exótica para realizar estos pasos dentro de los estrictos requisitos de tiempo impuestos por la velocidad a la que aparecen los errores en el equipo Quantum.  El lenguaje de destino de este nivel suele ser [VHDL](https://en.wikipedia.org/wiki/VHDL), que requiere una forma distinta de pensar en que se usa en el extremo superior de la pila para analizar una descripción de un algoritmo Quantum.

### <a name="the-q-quantum-programming-language"></a>El lenguaje de programación Q # Quantum
El objetivo de Q # es proporcionar un lenguaje sencillo que permita a los desarrolladores escribir código destinado a una gran variedad de plataformas de informática Quantum e interfaz con las capas de software que intervienen entre el usuario y el dispositivo Quantum.  El lenguaje facilita esto mediante la adopción de la noción de una pila de software y la abstracción de muchos de los detalles del equipo Quantum subyacente, a la vez que permite que otros niveles de la pila C#se expongan a través de un lenguaje como, para realizar las tareas necesarias. traducciones del código de preguntas y respuestas a operaciones fundamentales.  Esto permite que el desarrollador se Centre en lo que mejor hace: diseñar algoritmos y solucionar problemas.
