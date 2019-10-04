---
title: 比較セマンティクス (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 8d7868b0166f0a18824ec25e6cdf639deec665ac
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833942"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="d7b6b-102">比較セマンティクス (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d7b6b-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="d7b6b-103">次のいずれかの [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 演算子を実行すると、型インスタンスの比較が行われます。</span><span class="sxs-lookup"><span data-stu-id="d7b6b-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="d7b6b-104">明示的な比較</span><span class="sxs-lookup"><span data-stu-id="d7b6b-104">Explicit comparison</span></span>  
 <span data-ttu-id="d7b6b-105">等価演算</span><span class="sxs-lookup"><span data-stu-id="d7b6b-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="d7b6b-106">!=</span><span class="sxs-lookup"><span data-stu-id="d7b6b-106">!=</span></span>  
  
 <span data-ttu-id="d7b6b-107">順序付け操作</span><span class="sxs-lookup"><span data-stu-id="d7b6b-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="d7b6b-108">NULL 値が許容される操作</span><span class="sxs-lookup"><span data-stu-id="d7b6b-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="d7b6b-109">IS_NULL</span><span class="sxs-lookup"><span data-stu-id="d7b6b-109">IS NULL</span></span>  
  
- <span data-ttu-id="d7b6b-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="d7b6b-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="d7b6b-111">明示的な区別</span><span class="sxs-lookup"><span data-stu-id="d7b6b-111">Explicit distinction</span></span>  
 <span data-ttu-id="d7b6b-112">等価区別</span><span class="sxs-lookup"><span data-stu-id="d7b6b-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="d7b6b-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="d7b6b-113">DISTINCT</span></span>  
  
- <span data-ttu-id="d7b6b-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="d7b6b-114">GROUP BY</span></span>  
  
 <span data-ttu-id="d7b6b-115">順序付け区別</span><span class="sxs-lookup"><span data-stu-id="d7b6b-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="d7b6b-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="d7b6b-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="d7b6b-117">暗黙的な区別</span><span class="sxs-lookup"><span data-stu-id="d7b6b-117">Implicit distinction</span></span>  
 <span data-ttu-id="d7b6b-118">設定操作および述語 (等価)</span><span class="sxs-lookup"><span data-stu-id="d7b6b-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="d7b6b-119">UNION</span><span class="sxs-lookup"><span data-stu-id="d7b6b-119">UNION</span></span>  
  
- <span data-ttu-id="d7b6b-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="d7b6b-120">INTERSECT</span></span>  
  
- <span data-ttu-id="d7b6b-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="d7b6b-121">EXCEPT</span></span>  
  
- <span data-ttu-id="d7b6b-122">SET</span><span class="sxs-lookup"><span data-stu-id="d7b6b-122">SET</span></span>  
  
- <span data-ttu-id="d7b6b-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="d7b6b-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="d7b6b-124">項目述語 (等価)</span><span class="sxs-lookup"><span data-stu-id="d7b6b-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="d7b6b-125">IN</span><span class="sxs-lookup"><span data-stu-id="d7b6b-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="d7b6b-126">サポートされている組み合わせ</span><span class="sxs-lookup"><span data-stu-id="d7b6b-126">Supported Combinations</span></span>  
 <span data-ttu-id="d7b6b-127">次の表は、各種類の型の比較演算子のサポートされているすべての組み合わせを示します。</span><span class="sxs-lookup"><span data-stu-id="d7b6b-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="d7b6b-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="d7b6b-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="d7b6b-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="d7b6b-129">**!=**</span></span>|<span data-ttu-id="d7b6b-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="d7b6b-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="d7b6b-131">**独特**</span><span class="sxs-lookup"><span data-stu-id="d7b6b-131">**DISTINCT**</span></span>|<span data-ttu-id="d7b6b-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="d7b6b-132">**UNION**</span></span><br /><br /> <span data-ttu-id="d7b6b-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="d7b6b-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="d7b6b-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="d7b6b-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="d7b6b-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="d7b6b-135">**SET**</span></span><br /><br /> <span data-ttu-id="d7b6b-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="d7b6b-136">**OVERLAPS**</span></span>|<span data-ttu-id="d7b6b-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="d7b6b-137">**IN**</span></span>|<span data-ttu-id="d7b6b-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="d7b6b-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="d7b6b-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="d7b6b-139">**>   >=**</span></span>|<span data-ttu-id="d7b6b-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="d7b6b-140">**ORDER BY**</span></span>|<span data-ttu-id="d7b6b-141">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="d7b6b-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="d7b6b-142">**NULL ではない**</span><span class="sxs-lookup"><span data-stu-id="d7b6b-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="d7b6b-143">エンティティの種類</span><span class="sxs-lookup"><span data-stu-id="d7b6b-143">Entity type</span></span>|<span data-ttu-id="d7b6b-144">参照<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="d7b6b-145">すべてのプロパティ<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="d7b6b-146">すべてのプロパティ<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="d7b6b-147">すべてのプロパティ<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="d7b6b-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-150">参照<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="d7b6b-151">複合型</span><span class="sxs-lookup"><span data-stu-id="d7b6b-151">Complex type</span></span>|<span data-ttu-id="d7b6b-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d7b6b-159">行</span><span class="sxs-lookup"><span data-stu-id="d7b6b-159">Row</span></span>|<span data-ttu-id="d7b6b-160">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="d7b6b-161">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="d7b6b-162">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="d7b6b-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-165">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="d7b6b-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d7b6b-167">プリミティブ型</span><span class="sxs-lookup"><span data-stu-id="d7b6b-167">Primitive type</span></span>|<span data-ttu-id="d7b6b-168">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="d7b6b-168">Provider-specific</span></span>|<span data-ttu-id="d7b6b-169">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="d7b6b-169">Provider-specific</span></span>|<span data-ttu-id="d7b6b-170">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="d7b6b-170">Provider-specific</span></span>|<span data-ttu-id="d7b6b-171">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="d7b6b-171">Provider-specific</span></span>|<span data-ttu-id="d7b6b-172">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="d7b6b-172">Provider-specific</span></span>|<span data-ttu-id="d7b6b-173">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="d7b6b-173">Provider-specific</span></span>|<span data-ttu-id="d7b6b-174">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="d7b6b-174">Provider-specific</span></span>|  
|<span data-ttu-id="d7b6b-175">マルチセット</span><span class="sxs-lookup"><span data-stu-id="d7b6b-175">Multiset</span></span>|<span data-ttu-id="d7b6b-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="d7b6b-183">参照</span><span class="sxs-lookup"><span data-stu-id="d7b6b-183">Ref</span></span>|<span data-ttu-id="d7b6b-184">可<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="d7b6b-185">可<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="d7b6b-186">可<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="d7b6b-187">可<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="d7b6b-188">スロー</span><span class="sxs-lookup"><span data-stu-id="d7b6b-188">Throw</span></span>|<span data-ttu-id="d7b6b-189">スロー</span><span class="sxs-lookup"><span data-stu-id="d7b6b-189">Throw</span></span>|<span data-ttu-id="d7b6b-190">可<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="d7b6b-191">アソシエーション</span><span class="sxs-lookup"><span data-stu-id="d7b6b-191">Association</span></span><br /><br /> <span data-ttu-id="d7b6b-192">type</span><span class="sxs-lookup"><span data-stu-id="d7b6b-192">type</span></span>|<span data-ttu-id="d7b6b-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-194">スロー</span><span class="sxs-lookup"><span data-stu-id="d7b6b-194">Throw</span></span>|<span data-ttu-id="d7b6b-195">スロー</span><span class="sxs-lookup"><span data-stu-id="d7b6b-195">Throw</span></span>|<span data-ttu-id="d7b6b-196">スロー</span><span class="sxs-lookup"><span data-stu-id="d7b6b-196">Throw</span></span>|<span data-ttu-id="d7b6b-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="d7b6b-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="d7b6b-200"><sup>1</sup>次の例に示すように、指定されたエンティティ型インスタンスの参照は、暗黙的に比較されます。</span><span class="sxs-lookup"><span data-stu-id="d7b6b-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="d7b6b-201">エンティティ インスタンスは、明示的な参照に対して比較できません。</span><span class="sxs-lookup"><span data-stu-id="d7b6b-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="d7b6b-202">明示的な参照に対する比較を行った場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="d7b6b-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="d7b6b-203">たとえば、次のクエリを実行すると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="d7b6b-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="d7b6b-204"><sup>2</sup>複合型のプロパティは、ストアに送信される前にフラット化されるため、すべてのプロパティが比較可能である限り、比較可能になります。</span><span class="sxs-lookup"><span data-stu-id="d7b6b-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="d7b6b-205">「4」も参照してください<sup>。</sup></span><span class="sxs-lookup"><span data-stu-id="d7b6b-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="d7b6b-206"><sup>3</sup>Entity Framework ランタイムはサポートされていないケースを検出し、プロバイダー/ストアに関与せずに意味のある例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="d7b6b-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="d7b6b-207"><sup>4</sup>すべてのプロパティを比較しようとしました。</span><span class="sxs-lookup"><span data-stu-id="d7b6b-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="d7b6b-208">比較不能な型のプロパティ (text、ntext、image など) がある場合、サーバー例外がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="d7b6b-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="d7b6b-209"><sup>5</sup>参照の個々の要素がすべて比較されます (これには、エンティティセット名とエンティティ型のすべてのキープロパティが含まれます)。</span><span class="sxs-lookup"><span data-stu-id="d7b6b-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7b6b-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7b6b-210">See also</span></span>

- [<span data-ttu-id="d7b6b-211">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="d7b6b-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
