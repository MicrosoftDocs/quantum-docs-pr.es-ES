---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: Descomponer función
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855524"
---
# <a name="decomposedon-function"></a><span data-ttu-id="26fbf-102">Descomponer función</span><span class="sxs-lookup"><span data-stu-id="26fbf-102">DecomposedOn function</span></span>

<span data-ttu-id="26fbf-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="26fbf-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="26fbf-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26fbf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="26fbf-105">Descompone una permutación en una variable</span><span class="sxs-lookup"><span data-stu-id="26fbf-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="26fbf-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="26fbf-106">Description</span></span>

<span data-ttu-id="26fbf-107">Dada una permutación $ \pi $ ( `perm` ) y un índice $i $ ( `index` ), este método devuelve tres permutaciones $ ((\ pi_l, \ PI_R), \pi ') $ de modo que las imágenes de $ \ pi_l $ y $ \ PI_R $ no cambian bits en sus elementos en índices distintos de $i $ e imágenes de $ \pi ' $ no cambie el bit $i $ en sus elementos.</span><span class="sxs-lookup"><span data-stu-id="26fbf-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="26fbf-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="26fbf-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="26fbf-109">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="26fbf-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="26fbf-110">Índice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="26fbf-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="26fbf-111">Output: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="26fbf-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>



## <a name="example"></a><span data-ttu-id="26fbf-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26fbf-112">Example</span></span>

<span data-ttu-id="26fbf-113">Suponga que la entrada es Perm = [0, 2, 3, 5, 7, 1, 4, 6] e índice = 0. a continuación, esta función calcula tres permutaciones basadas en la tabla siguiente, que muestra la permutación `perm` en notación binaria con los elementos del grupo a y las imágenes del grupo D.  Las columnas enumeran los índices de bits.</span><span class="sxs-lookup"><span data-stu-id="26fbf-113">Assume that the input is perm = [0, 2, 3, 5, 7, 1, 4, 6] and index = 0, then this function computes three permutations based on the following table, which lists the permutation `perm` in binary notation with elements in group A and images in group D.  The columns list the bit indices.</span></span>

<span data-ttu-id="26fbf-114">|   Un |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="26fbf-114">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="26fbf-115">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-115">2 1 0</span></span> | <span data-ttu-id="26fbf-116">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-116">2 1 0</span></span> | <span data-ttu-id="26fbf-117">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-117">2 1 0</span></span> | <span data-ttu-id="26fbf-118">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-118">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="26fbf-119">0 0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-119">0 0 0</span></span> |       |       | <span data-ttu-id="26fbf-120">0 0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-120">0 0 0</span></span> | <span data-ttu-id="26fbf-121">0</span><span class="sxs-lookup"><span data-stu-id="26fbf-121">0</span></span>
| <span data-ttu-id="26fbf-122">0 0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-122">0 0 1</span></span> |       |       | <span data-ttu-id="26fbf-123">0 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-123">0 1 0</span></span> | <span data-ttu-id="26fbf-124">2</span><span class="sxs-lookup"><span data-stu-id="26fbf-124">2</span></span>
| <span data-ttu-id="26fbf-125">0 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-125">0 1 0</span></span> |       |       | <span data-ttu-id="26fbf-126">0 1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-126">0 1 1</span></span> | <span data-ttu-id="26fbf-127">3</span><span class="sxs-lookup"><span data-stu-id="26fbf-127">3</span></span>
| <span data-ttu-id="26fbf-128">0 1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-128">0 1 1</span></span> |       |       | <span data-ttu-id="26fbf-129">1 0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-129">1 0 1</span></span> | <span data-ttu-id="26fbf-130">5</span><span class="sxs-lookup"><span data-stu-id="26fbf-130">5</span></span>
| <span data-ttu-id="26fbf-131">1 0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-131">1 0 0</span></span> |       |       | <span data-ttu-id="26fbf-132">1 1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-132">1 1 1</span></span> | <span data-ttu-id="26fbf-133">7</span><span class="sxs-lookup"><span data-stu-id="26fbf-133">7</span></span>
| <span data-ttu-id="26fbf-134">1 0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-134">1 0 1</span></span> |       |       | <span data-ttu-id="26fbf-135">0 0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-135">0 0 1</span></span> | <span data-ttu-id="26fbf-136">1</span><span class="sxs-lookup"><span data-stu-id="26fbf-136">1</span></span>
| <span data-ttu-id="26fbf-137">1 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-137">1 1 0</span></span> |       |       | <span data-ttu-id="26fbf-138">1 0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-138">1 0 0</span></span> | <span data-ttu-id="26fbf-139">4</span><span class="sxs-lookup"><span data-stu-id="26fbf-139">4</span></span>
| <span data-ttu-id="26fbf-140">1 1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-140">1 1 1</span></span> |       |       | <span data-ttu-id="26fbf-141">1 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-141">1 1 0</span></span> | <span data-ttu-id="26fbf-142">6</span><span class="sxs-lookup"><span data-stu-id="26fbf-142">6</span></span>

<span data-ttu-id="26fbf-143">Todos los valores de los índices que no son iguales a 0 (= índice) se copian de a a B y de D a C.</span><span class="sxs-lookup"><span data-stu-id="26fbf-143">All values for indices not equal to 0 (= index) are copied from A to B and from D to C.</span></span>

<span data-ttu-id="26fbf-144">|   Un |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="26fbf-144">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="26fbf-145">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-145">2 1 0</span></span> | <span data-ttu-id="26fbf-146">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-146">2 1 0</span></span> | <span data-ttu-id="26fbf-147">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-147">2 1 0</span></span> | <span data-ttu-id="26fbf-148">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-148">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="26fbf-149">0 0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-149">0 0 0</span></span> | <span data-ttu-id="26fbf-150">0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-150">0 0</span></span>   | <span data-ttu-id="26fbf-151">0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-151">0 0</span></span>   | <span data-ttu-id="26fbf-152">0 0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-152">0 0 0</span></span> |
| <span data-ttu-id="26fbf-153">0 0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-153">0 0 1</span></span> | <span data-ttu-id="26fbf-154">0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-154">0 0</span></span>   | <span data-ttu-id="26fbf-155">0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-155">0 1</span></span>   | <span data-ttu-id="26fbf-156">0 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-156">0 1 0</span></span> |
| <span data-ttu-id="26fbf-157">0 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-157">0 1 0</span></span> | <span data-ttu-id="26fbf-158">0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-158">0 1</span></span>   | <span data-ttu-id="26fbf-159">0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-159">0 1</span></span>   | <span data-ttu-id="26fbf-160">0 1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-160">0 1 1</span></span> |
| <span data-ttu-id="26fbf-161">0 1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-161">0 1 1</span></span> | <span data-ttu-id="26fbf-162">0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-162">0 1</span></span>   | <span data-ttu-id="26fbf-163">1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-163">1 0</span></span>   | <span data-ttu-id="26fbf-164">1 0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-164">1 0 1</span></span> |
| <span data-ttu-id="26fbf-165">1 0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-165">1 0 0</span></span> | <span data-ttu-id="26fbf-166">1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-166">1 0</span></span>   | <span data-ttu-id="26fbf-167">1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-167">1 1</span></span>   | <span data-ttu-id="26fbf-168">1 1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-168">1 1 1</span></span> |
| <span data-ttu-id="26fbf-169">1 0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-169">1 0 1</span></span> | <span data-ttu-id="26fbf-170">1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-170">1 0</span></span>   | <span data-ttu-id="26fbf-171">0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-171">0 0</span></span>   | <span data-ttu-id="26fbf-172">0 0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-172">0 0 1</span></span> |
| <span data-ttu-id="26fbf-173">1 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-173">1 1 0</span></span> | <span data-ttu-id="26fbf-174">1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-174">1 1</span></span>   | <span data-ttu-id="26fbf-175">1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-175">1 0</span></span>   | <span data-ttu-id="26fbf-176">1 0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-176">1 0 0</span></span> |
| <span data-ttu-id="26fbf-177">1 1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-177">1 1 1</span></span> | <span data-ttu-id="26fbf-178">1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-178">1 1</span></span>   | <span data-ttu-id="26fbf-179">1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-179">1 1</span></span>   | <span data-ttu-id="26fbf-180">1 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-180">1 1 0</span></span> |

<span data-ttu-id="26fbf-181">A continuación, se coloca un 0 para el primer elemento con un índice vacío en la columna 0 del bloque B y, a continuación, se coloca un 1 en B donde el prefijo coincide (en el primer caso, la otra fila con índices 0 0).</span><span class="sxs-lookup"><span data-stu-id="26fbf-181">Next a 0 is placed for the first element with an empty index at column 0 in block B and then a 1 is placed in B where the prefix matches (in the first case the other row with indices 0 0).</span></span>
<span data-ttu-id="26fbf-182">Después, se agrega 1 en la misma fila del bloque C y, a continuación, un 0 para el prefijo correspondiente en el bloque C.  Este proceso se repite hasta que todos los índices se han colocado en la columna 0 en los bloques B y C.</span><span class="sxs-lookup"><span data-stu-id="26fbf-182">Afterwards, a 1 is added in the same row in block C, and then a 0 for the corresponding prefix in block C.  This process is repeated, until all indices have been placed in column 0 in blocks B and C.</span></span>

<span data-ttu-id="26fbf-183">|   Un |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="26fbf-183">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="26fbf-184">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-184">2 1 0</span></span> | <span data-ttu-id="26fbf-185">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-185">2 1 0</span></span> | <span data-ttu-id="26fbf-186">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-186">2 1 0</span></span> | <span data-ttu-id="26fbf-187">2 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-187">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="26fbf-188">0 0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-188">0 0 0</span></span> | <span data-ttu-id="26fbf-189">0 0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-189">0 0 0</span></span> | <span data-ttu-id="26fbf-190">0 0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-190">0 0 0</span></span> | <span data-ttu-id="26fbf-191">0 0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-191">0 0 0</span></span> |
| <span data-ttu-id="26fbf-192">0 0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-192">0 0 1</span></span> | <span data-ttu-id="26fbf-193">0 0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-193">0 0 1</span></span> | <span data-ttu-id="26fbf-194">0 1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-194">0 1 1</span></span> | <span data-ttu-id="26fbf-195">0 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-195">0 1 0</span></span> |
| <span data-ttu-id="26fbf-196">0 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-196">0 1 0</span></span> | <span data-ttu-id="26fbf-197">0 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-197">0 1 0</span></span> | <span data-ttu-id="26fbf-198">0 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-198">0 1 0</span></span> | <span data-ttu-id="26fbf-199">0 1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-199">0 1 1</span></span> |
| <span data-ttu-id="26fbf-200">0 1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-200">0 1 1</span></span> | <span data-ttu-id="26fbf-201">0 1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-201">0 1 1</span></span> | <span data-ttu-id="26fbf-202">1 0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-202">1 0 1</span></span> | <span data-ttu-id="26fbf-203">1 0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-203">1 0 1</span></span> |
| <span data-ttu-id="26fbf-204">1 0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-204">1 0 0</span></span> | <span data-ttu-id="26fbf-205">1 0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-205">1 0 0</span></span> | <span data-ttu-id="26fbf-206">1 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-206">1 1 0</span></span> | <span data-ttu-id="26fbf-207">1 1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-207">1 1 1</span></span> |
| <span data-ttu-id="26fbf-208">1 0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-208">1 0 1</span></span> | <span data-ttu-id="26fbf-209">1 0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-209">1 0 1</span></span> | <span data-ttu-id="26fbf-210">0 0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-210">0 0 1</span></span> | <span data-ttu-id="26fbf-211">0 0 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-211">0 0 1</span></span> |
| <span data-ttu-id="26fbf-212">1 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-212">1 1 0</span></span> | <span data-ttu-id="26fbf-213">1 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-213">1 1 0</span></span> | <span data-ttu-id="26fbf-214">1 0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-214">1 0 0</span></span> | <span data-ttu-id="26fbf-215">1 0 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-215">1 0 0</span></span> |
| <span data-ttu-id="26fbf-216">1 1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-216">1 1 1</span></span> | <span data-ttu-id="26fbf-217">1 1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-217">1 1 1</span></span> | <span data-ttu-id="26fbf-218">1 1 1</span><span class="sxs-lookup"><span data-stu-id="26fbf-218">1 1 1</span></span> | <span data-ttu-id="26fbf-219">1 1 0</span><span class="sxs-lookup"><span data-stu-id="26fbf-219">1 1 0</span></span> |

<span data-ttu-id="26fbf-220">Podemos leer tres nuevas permutaciones de la tabla:</span><span class="sxs-lookup"><span data-stu-id="26fbf-220">We can read three new permutations from the table:</span></span>

- <span data-ttu-id="26fbf-221">$ \ pi_l $ con elementos de A, imágenes en B (izquierda)</span><span class="sxs-lookup"><span data-stu-id="26fbf-221">$\pi_l$ with elements in A, images in B (left)</span></span>
- <span data-ttu-id="26fbf-222">$ \ pi_r $ con elementos en D, imágenes en C (derecha)</span><span class="sxs-lookup"><span data-stu-id="26fbf-222">$\pi_r$ with elements in D, images in C (right)</span></span>
- <span data-ttu-id="26fbf-223">$ \pi ' $ con elementos en B, imágenes en C (resto)</span><span class="sxs-lookup"><span data-stu-id="26fbf-223">$\pi'$  with elements in B, images in C (remainder)</span></span>

<span data-ttu-id="26fbf-224">Tenga en cuenta que los valores de bit de diseño no cambian en $ \ pi_l $ y $ \ pi_r $ para los índices 1 y 2, y los valores de bit no cambian para en $ \ pi_ ' $ para el índice 0.</span><span class="sxs-lookup"><span data-stu-id="26fbf-224">Note that by design bit values do not change in $\pi_l$ and $\pi_r$ for indices 1 and 2, and bit values do not change for in $\pi_'$ for index 0.</span></span>  <span data-ttu-id="26fbf-225">Tenga en cuenta también que $ \ pi_l $ y $ \ PI_R $ deben ser de inverso.</span><span class="sxs-lookup"><span data-stu-id="26fbf-225">Also note that $\pi_l$ and $\pi_r$ must be self-inverse.</span></span>

<span data-ttu-id="26fbf-226">Las permutaciones derivadas y devueltas son: Left = [0, 1, 2, 3, 4, 5, 6, 7] Right = [0, 1, 3, 2, 4, 5, 7, 6] resto = [0, 3, 2, 5, 6, 1, 4, 7]</span><span class="sxs-lookup"><span data-stu-id="26fbf-226">The derived and returned permutations are: left      = [0, 1, 2, 3, 4, 5, 6, 7] right     = [0, 1, 3, 2, 4, 5, 7, 6] remainder = [0, 3, 2, 5, 6, 1, 4, 7]</span></span>