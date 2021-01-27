---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 64ed9aed7c9d9a4a689c5926f3cd085a2521c4db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856813"
---
# <a name="quantumrom-function"></a>QuantumROM función)

Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> QuantumROM está en desuso. Use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> en su lugar.

Usa la técnica de ROM Quantum para representar una matriz de densidad determinada.

Dada una lista de $N $ coeficientes $ \ alpha_j $, se devuelve un valor de unitario $U $ que usa la técnica Quantum-ROM para preparar una aproximación $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ de la depuración de la matriz de densidad $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $. En esta aproximación, el error $ \epsilon $ es tal que $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \le \epsilon/N $ y $ \| \tilde\rho-\rho \| \le \epsilon $. En otras palabras, $ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\rceil} \ les {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{Garbage} _J}.
\end{align} $ $

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a>Entrada

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

El error de destino $ \epsilon $.


### <a name="coefficients--double"></a>coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matriz de $N $ coeficientes que especifican la probabilidad de Estados de base.
Los números negativos $-\ alpha_j $ se tratarán como positivos $ | \ alpha_j | $.



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a>Salida: (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL)

## <a name="first-parameter"></a>Primer parámetro

Una tupla `(x,(y,z))` donde `x = y + z` es el número total de qubits asignados, `y` es el número de qubits para el `LittleEndian` registro y `z` es el número de qubits de elementos no utilizados.

## <a name="second-parameter"></a>Segundo parámetro

La norma $ \ sum_j | \ alpha_j | $ de la matriz de coeficientes.

## <a name="third-parameter"></a>Tercer parámetro

La $U unitario $.

## <a name="example"></a>Ejemplo

El siguiente fragmento de código prepara una purificación del estado $3 $-qubit $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $, donde $ \vec\alpha = (1.0, 2.0, 3.0, 4.0, 5.0) $ y el error es `1e-3` ;

```qsharp
let coefficients = [1.0,2.0,3.0,4.0,5.0];
let targetError = 1e-3;
let ((nTotalQubits, (nIndexQubits, nGarbageQubits)), oneNorm, op) = QuantumROM(targetError, coefficients);
using (indexRegister = Qubit[nIndexQubits]) {
    using (garbageRegister = Qubit[nGarbageQubits]) {
        op(LittleEndian(indexRegister), garbageRegister);
    }
}
```

## <a name="references"></a>Referencias

- Codifique los espectros electrónicos en los circuitos Quantum con la complejidad T lineal Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pálido, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662