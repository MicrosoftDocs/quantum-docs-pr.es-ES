---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: Operación PrepareSparseMultiConfigurationalState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 1182f79a33784cdb49cb13db5cc97a0a45e59f9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727706"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a><span data-ttu-id="05b2c-102">Operación PrepareSparseMultiConfigurationalState</span><span class="sxs-lookup"><span data-stu-id="05b2c-102">PrepareSparseMultiConfigurationalState operation</span></span>

<span data-ttu-id="05b2c-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="05b2c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="05b2c-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="05b2c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="05b2c-105">La preparación del estado de prueba de la configuración de varias configuraciones múltiple, para lo que se agregan las excitaciones al estado de prueba inicial.</span><span class="sxs-lookup"><span data-stu-id="05b2c-105">Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.</span></span>

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="05b2c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="05b2c-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="05b2c-107">initialStatePreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="05b2c-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="05b2c-108">Unitario para preparar el estado de la prueba inicial.</span><span class="sxs-lookup"><span data-stu-id="05b2c-108">Unitary to prepare initial trial state.</span></span>


### <a name="excitations--jordanwignerinputstate"></a><span data-ttu-id="05b2c-109">exacciones: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="05b2c-109">excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="05b2c-110">Las exacciones del estado de prueba inicial representadas por la amplitud de los índices de excitation y qubit en los que actúa excitation.</span><span class="sxs-lookup"><span data-stu-id="05b2c-110">Excitations of initial trial state represented by the amplitude of the excitation and the qubit indices the excitation acts on.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="05b2c-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="05b2c-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="05b2c-112">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="05b2c-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="05b2c-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="05b2c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

