---
title: 比較セマンティクス (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: da7b8f662d10376abd649e674701b43b7b740a6f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251181"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="4ea94-102">比較セマンティクス (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4ea94-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="4ea94-103">次のいずれかの [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 演算子を実行すると、型インスタンスの比較が行われます。</span><span class="sxs-lookup"><span data-stu-id="4ea94-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="4ea94-104">明示的な比較</span><span class="sxs-lookup"><span data-stu-id="4ea94-104">Explicit comparison</span></span>  
 <span data-ttu-id="4ea94-105">等価演算</span><span class="sxs-lookup"><span data-stu-id="4ea94-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="4ea94-106">!=</span><span class="sxs-lookup"><span data-stu-id="4ea94-106">!=</span></span>  
  
 <span data-ttu-id="4ea94-107">順序付け操作</span><span class="sxs-lookup"><span data-stu-id="4ea94-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="4ea94-108">NULL 値が許容される操作</span><span class="sxs-lookup"><span data-stu-id="4ea94-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="4ea94-109">IS_NULL</span><span class="sxs-lookup"><span data-stu-id="4ea94-109">IS NULL</span></span>  
  
- <span data-ttu-id="4ea94-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="4ea94-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="4ea94-111">明示的な区別</span><span class="sxs-lookup"><span data-stu-id="4ea94-111">Explicit distinction</span></span>  
 <span data-ttu-id="4ea94-112">等価区別</span><span class="sxs-lookup"><span data-stu-id="4ea94-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="4ea94-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="4ea94-113">DISTINCT</span></span>  
  
- <span data-ttu-id="4ea94-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="4ea94-114">GROUP BY</span></span>  
  
 <span data-ttu-id="4ea94-115">順序付け区別</span><span class="sxs-lookup"><span data-stu-id="4ea94-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="4ea94-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="4ea94-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="4ea94-117">暗黙的な区別</span><span class="sxs-lookup"><span data-stu-id="4ea94-117">Implicit distinction</span></span>  
 <span data-ttu-id="4ea94-118">設定操作および述語 (等価)</span><span class="sxs-lookup"><span data-stu-id="4ea94-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="4ea94-119">UNION</span><span class="sxs-lookup"><span data-stu-id="4ea94-119">UNION</span></span>  
  
- <span data-ttu-id="4ea94-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="4ea94-120">INTERSECT</span></span>  
  
- <span data-ttu-id="4ea94-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="4ea94-121">EXCEPT</span></span>  
  
- <span data-ttu-id="4ea94-122">SET</span><span class="sxs-lookup"><span data-stu-id="4ea94-122">SET</span></span>  
  
- <span data-ttu-id="4ea94-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="4ea94-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="4ea94-124">項目述語 (等価)</span><span class="sxs-lookup"><span data-stu-id="4ea94-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="4ea94-125">IN</span><span class="sxs-lookup"><span data-stu-id="4ea94-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="4ea94-126">サポートされている組み合わせ</span><span class="sxs-lookup"><span data-stu-id="4ea94-126">Supported Combinations</span></span>  
 <span data-ttu-id="4ea94-127">次の表は、各種類の型の比較演算子のサポートされているすべての組み合わせを示します。</span><span class="sxs-lookup"><span data-stu-id="4ea94-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="4ea94-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="4ea94-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="4ea94-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="4ea94-129">**!=**</span></span>|<span data-ttu-id="4ea94-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="4ea94-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="4ea94-131">**独特**</span><span class="sxs-lookup"><span data-stu-id="4ea94-131">**DISTINCT**</span></span>|<span data-ttu-id="4ea94-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="4ea94-132">**UNION**</span></span><br /><br /> <span data-ttu-id="4ea94-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="4ea94-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="4ea94-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="4ea94-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="4ea94-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="4ea94-135">**SET**</span></span><br /><br /> <span data-ttu-id="4ea94-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="4ea94-136">**OVERLAPS**</span></span>|<span data-ttu-id="4ea94-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="4ea94-137">**IN**</span></span>|<span data-ttu-id="4ea94-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="4ea94-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="4ea94-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="4ea94-139">**>   >=**</span></span>|<span data-ttu-id="4ea94-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="4ea94-140">**ORDER BY**</span></span>|<span data-ttu-id="4ea94-141">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="4ea94-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="4ea94-142">**NULL ではない**</span><span class="sxs-lookup"><span data-stu-id="4ea94-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="4ea94-143">エンティティ型</span><span class="sxs-lookup"><span data-stu-id="4ea94-143">Entity type</span></span>|<span data-ttu-id="4ea94-144">参照<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="4ea94-145">すべてのプロパティ<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="4ea94-146">すべてのプロパティ<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="4ea94-147">すべてのプロパティ<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="4ea94-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-150">参照<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="4ea94-151">複合型</span><span class="sxs-lookup"><span data-stu-id="4ea94-151">Complex type</span></span>|<span data-ttu-id="4ea94-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="4ea94-159">行</span><span class="sxs-lookup"><span data-stu-id="4ea94-159">Row</span></span>|<span data-ttu-id="4ea94-160">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="4ea94-161">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="4ea94-162">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="4ea94-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-165">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="4ea94-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="4ea94-167">プリミティブ型</span><span class="sxs-lookup"><span data-stu-id="4ea94-167">Primitive type</span></span>|<span data-ttu-id="4ea94-168">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="4ea94-168">Provider-specific</span></span>|<span data-ttu-id="4ea94-169">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="4ea94-169">Provider-specific</span></span>|<span data-ttu-id="4ea94-170">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="4ea94-170">Provider-specific</span></span>|<span data-ttu-id="4ea94-171">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="4ea94-171">Provider-specific</span></span>|<span data-ttu-id="4ea94-172">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="4ea94-172">Provider-specific</span></span>|<span data-ttu-id="4ea94-173">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="4ea94-173">Provider-specific</span></span>|<span data-ttu-id="4ea94-174">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="4ea94-174">Provider-specific</span></span>|  
|<span data-ttu-id="4ea94-175">マルチセット</span><span class="sxs-lookup"><span data-stu-id="4ea94-175">Multiset</span></span>|<span data-ttu-id="4ea94-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="4ea94-183">参照</span><span class="sxs-lookup"><span data-stu-id="4ea94-183">Ref</span></span>|<span data-ttu-id="4ea94-184">可<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="4ea94-185">可<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="4ea94-186">可<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="4ea94-187">可<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="4ea94-188">スロー</span><span class="sxs-lookup"><span data-stu-id="4ea94-188">Throw</span></span>|<span data-ttu-id="4ea94-189">スロー</span><span class="sxs-lookup"><span data-stu-id="4ea94-189">Throw</span></span>|<span data-ttu-id="4ea94-190">可<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="4ea94-191">アソシエーション</span><span class="sxs-lookup"><span data-stu-id="4ea94-191">Association</span></span><br /><br /> <span data-ttu-id="4ea94-192">型</span><span class="sxs-lookup"><span data-stu-id="4ea94-192">type</span></span>|<span data-ttu-id="4ea94-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-194">スロー</span><span class="sxs-lookup"><span data-stu-id="4ea94-194">Throw</span></span>|<span data-ttu-id="4ea94-195">スロー</span><span class="sxs-lookup"><span data-stu-id="4ea94-195">Throw</span></span>|<span data-ttu-id="4ea94-196">スロー</span><span class="sxs-lookup"><span data-stu-id="4ea94-196">Throw</span></span>|<span data-ttu-id="4ea94-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="4ea94-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="4ea94-200"><sup>1</sup>次の例に示すように、指定されたエンティティ型インスタンスの参照は、暗黙的に比較されます。</span><span class="sxs-lookup"><span data-stu-id="4ea94-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="4ea94-201">エンティティ インスタンスは、明示的な参照に対して比較できません。</span><span class="sxs-lookup"><span data-stu-id="4ea94-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="4ea94-202">明示的な参照に対する比較を行った場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4ea94-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="4ea94-203">たとえば、次のクエリを実行すると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4ea94-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="4ea94-204"><sup>2</sup>複合型のプロパティは、ストアに送信される前にフラット化されるため、すべてのプロパティが比較可能である限り、比較可能になります。</span><span class="sxs-lookup"><span data-stu-id="4ea94-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="4ea94-205">「4」も参照してください<sup>。</sup></span><span class="sxs-lookup"><span data-stu-id="4ea94-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="4ea94-206"><sup>3</sup>Entity Framework ランタイムはサポートされていないケースを検出し、プロバイダー/ストアに関与せずに意味のある例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="4ea94-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="4ea94-207"><sup>4</sup>すべてのプロパティを比較しようとしました。</span><span class="sxs-lookup"><span data-stu-id="4ea94-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="4ea94-208">比較不能な型のプロパティ (text、ntext、image など) がある場合、サーバー例外がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="4ea94-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="4ea94-209"><sup>5</sup>参照の個々の要素がすべて比較されます (これには、エンティティセット名とエンティティ型のすべてのキープロパティが含まれます)。</span><span class="sxs-lookup"><span data-stu-id="4ea94-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ea94-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ea94-210">See also</span></span>

- [<span data-ttu-id="4ea94-211">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="4ea94-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
