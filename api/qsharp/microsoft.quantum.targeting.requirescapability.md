---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: Tipo definido por el usuario RequiresCapability
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 5e0db49d6f73398ac36003eb0f44e3a6520b7f1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855148"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="d7b93-102">Tipo definido por el usuario RequiresCapability</span><span class="sxs-lookup"><span data-stu-id="d7b93-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="d7b93-103">Espacio de nombres: [Microsoft. Quantum. targeting](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="d7b93-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="d7b93-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d7b93-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d7b93-105">Atributo reconocido por el compilador que se usa para marcar una función que se puede llamar con las capacidades de tiempo de ejecución que requiere.</span><span class="sxs-lookup"><span data-stu-id="d7b93-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="d7b93-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="d7b93-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="d7b93-107">Nivel: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d7b93-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="d7b93-108">Nombre del nivel de capacidad en tiempo de ejecución requerido por el que se puede llamar.</span><span class="sxs-lookup"><span data-stu-id="d7b93-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="d7b93-109">Motivo: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d7b93-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="d7b93-110">Una descripción de por qué la función invocable requiere esta funcionalidad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d7b93-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="d7b93-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d7b93-111">Remarks</span></span>

<span data-ttu-id="d7b93-112">Este atributo se agrega automáticamente para que el compilador pueda invocarlo, a menos que ya exista una instancia de este atributo en el que se pueda llamar.</span><span class="sxs-lookup"><span data-stu-id="d7b93-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="d7b93-113">No debe usarse excepto en casos excepcionales en los que el compilador no deduce correctamente la funcionalidad necesaria.</span><span class="sxs-lookup"><span data-stu-id="d7b93-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="d7b93-114">A continuación se muestra la lista de nombres de nivel de capacidad, con el fin de aumentar las capacidades o reducir las restricciones:</span><span class="sxs-lookup"><span data-stu-id="d7b93-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="d7b93-115">No se puede comparar la igualdad de los resultados de la medida.</span><span class="sxs-lookup"><span data-stu-id="d7b93-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="d7b93-116">Los resultados de la medición solo se pueden comparar para comprobar la igualdad en expresiones condicionales if-Statement en operaciones.</span><span class="sxs-lookup"><span data-stu-id="d7b93-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="d7b93-117">El bloque de una instrucción If que depende de un resultado no puede contener instrucciones SET para variables mutables declaradas fuera del bloque o instrucciones Return.</span><span class="sxs-lookup"><span data-stu-id="d7b93-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="d7b93-118">No hay restricciones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d7b93-118">No runtime restrictions.</span></span> <span data-ttu-id="d7b93-119">Se puede ejecutar cualquier programa de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="d7b93-119">Any Q# program can be executed.</span></span>