---
title: Introducción a la biblioteca de valores numéricos cuánticos | Microsoft Docs
description: Introducción a la biblioteca de valores numéricos cuánticos
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: 9552f3683e1df8cb10d19d0b3f85223df056f83d
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871355"
---
# <a name="introduction-to-the-quantum-numerics-library"></a>Introducción a la biblioteca de valores numéricos cuánticos

Muchos algoritmos cuánticos se basan en [cajas negras](xref:microsoft.quantum.concepts.oracles) que evalúan funciones matemáticas en una superposición de entradas.
El componente principal del algoritmo de Shor, por ejemplo, evalúa $f(x) = a^x\operatorname{mod} N$ para un $a$ fijo, el número que se va a factorizar $N$, y $x$, el entero $2n$-qubit en una superposición uniforme de las $2n$-bit cadenas.

Para ejecutar el algoritmo de Shor en un equipo cuántico real, esta función debe escribirse en función de las operaciones nativas del equipo de destino.
Usando la representación binaria de $x$, siendo $x _i$ el bit número $i$ contando desde el bit menos significativo, $f(x)$ se puede escribir como $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.
A su vez, esto se puede escribir como un producto (mod N) de términos $a^{2^i x_i}=(a^{2^i})^{x_i}$. Por lo tanto, la función $f(x)$ se puede implementar utilizando una secuencia de $2n$ multiplicaciones (modulares) por $a^{2^i}$, con la condición de que $x_i$ no sea cero. Las constantes $a^{2^i}$ se pueden calcular previamente y reducir al módulo N antes de ejecutar el algoritmo.

Esta secuencia de multiplicaciones modulares controladas se puede simplificar aún más: Cada multiplicación se puede realizar mediante una secuencia de adiciones modulares controladas por $n$; y cada adición modular se puede crear a partir de una suma normal y un comparador.


Como se necesitan muchos pasos para llegar a una implementación real, resultaría muy útil tener dicha funcionalidad disponible desde el principio.
Por este motivo, Quantum Development Kit proporciona compatibilidad con una amplia gama de funciones numéricas.


## <a name="functionality"></a>Funcionalidad

Además de la aritmética de enteros mencionada, la biblioteca de valores numéricos proporciona:

- Funcionalidad de enteros con o sin signo (multiplicación, cuadrado, división con resto, inversión, etc.) con uno o dos números enteros cuánticos como entrada.
- Funcionalidad de punto fijo (suma/resta, multiplicación, cuadrado, 1/x, evaluación polinómica) con uno o dos números de punto fijo cuánticos como entrada.

## <a name="getting-started"></a>Introducción

> [!div class="nextstepaction"]
> [Más información sobre el uso de la biblioteca de valores numéricos](xref:microsoft.quantum.numerics.usage)
