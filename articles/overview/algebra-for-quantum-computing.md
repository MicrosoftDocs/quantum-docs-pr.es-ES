---
title: Álgebra lineal para la computación cuántica
description: Más información sobre qué conceptos básicos de álgebra lineal son necesarios para entender la computación cuántica
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.algebra
ms.openlocfilehash: 4750643d16ad8af6240df42c1b93353565561429
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327601"
---
# <a name="linear-algebra-for-quantum-computing"></a>Álgebra lineal para la computación cuántica

El álgebra lineal es el lenguaje de la computación cuántica. Aunque no es necesario que sepa implementar o escribir programas cuánticos, se usa mucho para describir los estados de los cúbits y las operaciones cuánticas, y para predecir lo que hará un equipo cuántico en respuesta a una secuencia de instrucciones.

Al igual que estar familiarizado con los [conceptos básicos de la física cuántica](xref:microsoft.quantum.overview.understanding) puede ayudarle a entender la computación cuántica, conocer algunos aspectos básicos del álgebra lineal puede ayudarle a comprender cómo funcionan los algoritmos cuánticos. Como mínimo, querrá estar familiarizado con los **vectores** y la **multiplicación de matrices**. Si necesita actualizar su conocimiento de estos conceptos de álgebra, estos tutoriales cubren los aspectos básicos:

- [Tutorial de Jupyter Notebook sobre álgebra lineal](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)
- [Tutorial de Jupyter Notebook sobre aritmética compleja](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)
- [Álgebra lineal para la computación cuántica](https://cds.cern.ch/record/1522001/files/978-1-4614-6336-8_BookBackMatter.pdf)
- [Fundamentos del álgebra lineal](https://www.math.ubc.ca/~carrell/NB.pdf)
- [Quantum Computation Primer](https://www.codeproject.com/Articles/5155638/Quantum-Computation-Primer-Part-1#exploring-quantum-superposition)

## <a name="vectors-and-matrices-in-quantum-computing"></a>Vectores y matrices en la computación cuántica

En el tema [Descripción de la computación cuántica](xref:microsoft.quantum.overview.understanding), vimos que un cúbit puede estar en un estado de 1 o 0, en una superposición o en ambos. Si utilizamos el álgebra lineal, el estado de un cúbit se describe como un vector y se representa mediante una **matriz** de una sola columna $\begin{bmatrix} a \\\\  b \end{bmatrix}$. También se conoce como **vector de estado cuántico**, y debe cumplir el requisito $|a|^2 + |b|^2 = 1$.  

Los elementos de la matriz representan la probabilidad de que el cúbit colapse en una u otra forma, siendo $|a|^2$ la probabilidad de que colapse en cero y $|b|^2$ la probabilidad de que colapse en uno. Todas las matrices siguientes representan vectores de estado cuántico válidos:

$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}, \begin{bmatrix} 0 \\\\  1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}, \text{ and }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$

También vimos que, en los [equipos y simuladores cuánticos](xref:microsoft.quantum.overview.simulators), se usan operaciones cuánticas para modificar el estado de un cúbit.  Las operaciones cuánticas también se pueden representar mediante una matriz. Cuando se aplica una operación cuántica a un cúbit, se multiplican las dos matrices que los representan y la respuesta resultante representa el nuevo estado del cúbit después de la operación.  

A continuación, se muestran dos operaciones cuánticas comunes representadas con multiplicación de matrices.


La [operación `X`](xref:microsoft.quantum.intrinsic.x) se representa mediante la matriz de Pauli $X$,

$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix},$$
    
y se usa para cambiar el estado de un cúbit de 0 a 1 (o viceversa); por ejemplo:

$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.$$

La [operación "H"](xref:microsoft.quantum.intrinsic.h) está representada por la transformación de Hadamard $H$,

$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix},$$

 que coloca un cúbit en un estado de superposición, en el que tiene una probabilidad uniforme de colapsar en cualquiera de los modos, como se muestra aquí.

$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}.$$

Una matriz que representa una operación cuántica tiene un requisito: debe ser una matriz **unitaria**. Una matriz es unitaria si la **inversa** de la matriz es igual que la **traspuesta conjugada** de la matriz.

## <a name="representing-two-qubit-states"></a>Representación de dos estados de cúbit

En los ejemplos anteriores, el estado de un cúbit se describía usando una matriz de una sola columna $\begin{bmatrix} a \\\\  b \end{bmatrix}$, y aplicarle una operación se describía multiplicando las dos matrices. Sin embargo, como los equipos cuánticos usan más de un cúbit, ¿cómo se describe el estado combinado de dos cúbits? 

Recuerde que cada cúbit es un espacio vectorial, por lo que no se puede multiplicar sin más. En su lugar, se usa un **producto de tensores**, que es una operación relacionada que crea un nuevo espacio vectorial a partir de espacios vectoriales individuales, y se representa mediante el símbolo $\otimes$. Por ejemplo, se calcula el producto de tensores de dos estados de cúbit $\begin{bmatrix} a \\\\  b \end{bmatrix}$ and $\begin{bmatrix} c \\\\  d \end{bmatrix}$

$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}.
$$

El resultado es una matriz de cuatro dimensiones, en la que cada elemento representa una probabilidad. Por ejemplo, $ac$ es la probabilidad de que los dos cúbits colapsen en 0 y 0, $ad$ es la probabilidad de 0 y 1, y así sucesivamente. 

Al igual que el estado de un solo cúbit  $\begin{bmatrix} a \\\\  b \end{bmatrix}$ debe cumplir el requisito $|a|^2 + |b|^2 = 1$ para que represente un estado cuántico. un estado de dos cúbits $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ debe cumplir el requisito $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$.

## <a name="summary"></a>Resumen

El álgebra lineal es el lenguaje estándar que se utiliza para describir la computación y la física cuánticas. Aunque las [bibliotecas](xref:microsoft.quantum.libraries) incluidas en el kit de desarrollo de Microsoft Quantum ayudan a ejecutar algoritmos cuánticos avanzados sin profundizar en las matemáticas subyacentes, comprender los aspectos básicos le ayudará a empezar a trabajar rápidamente y proporciona una base sólida para la creación.

## <a name="next-steps"></a>Pasos siguientes

[Instalación del QDK](xref:microsoft.quantum.install)