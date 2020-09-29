---
title: 比較セマンティクス (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 9a36fcc4476c25d64fed670e857f339fb20043d8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197834"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="4aac6-102">比較セマンティクス (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4aac6-102">Comparison Semantics (Entity SQL)</span></span>

<span data-ttu-id="4aac6-103">次のいずれかの [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 演算子を実行すると、型インスタンスの比較が行われます。</span><span class="sxs-lookup"><span data-stu-id="4aac6-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="4aac6-104">明示的な比較</span><span class="sxs-lookup"><span data-stu-id="4aac6-104">Explicit comparison</span></span>  

 <span data-ttu-id="4aac6-105">等価演算</span><span class="sxs-lookup"><span data-stu-id="4aac6-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="4aac6-106">!=</span><span class="sxs-lookup"><span data-stu-id="4aac6-106">!=</span></span>  
  
 <span data-ttu-id="4aac6-107">順序付け操作</span><span class="sxs-lookup"><span data-stu-id="4aac6-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="4aac6-108">NULL 値が許容される操作</span><span class="sxs-lookup"><span data-stu-id="4aac6-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="4aac6-109">IS_NULL</span><span class="sxs-lookup"><span data-stu-id="4aac6-109">IS NULL</span></span>  
  
- <span data-ttu-id="4aac6-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="4aac6-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="4aac6-111">明示的な区別</span><span class="sxs-lookup"><span data-stu-id="4aac6-111">Explicit distinction</span></span>  

 <span data-ttu-id="4aac6-112">等価区別</span><span class="sxs-lookup"><span data-stu-id="4aac6-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="4aac6-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="4aac6-113">DISTINCT</span></span>  
  
- <span data-ttu-id="4aac6-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="4aac6-114">GROUP BY</span></span>  
  
 <span data-ttu-id="4aac6-115">順序付け区別</span><span class="sxs-lookup"><span data-stu-id="4aac6-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="4aac6-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="4aac6-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="4aac6-117">暗黙的な区別</span><span class="sxs-lookup"><span data-stu-id="4aac6-117">Implicit distinction</span></span>  

 <span data-ttu-id="4aac6-118">設定操作および述語 (等価)</span><span class="sxs-lookup"><span data-stu-id="4aac6-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="4aac6-119">UNION</span><span class="sxs-lookup"><span data-stu-id="4aac6-119">UNION</span></span>  
  
- <span data-ttu-id="4aac6-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="4aac6-120">INTERSECT</span></span>  
  
- <span data-ttu-id="4aac6-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="4aac6-121">EXCEPT</span></span>  
  
- <span data-ttu-id="4aac6-122">SET</span><span class="sxs-lookup"><span data-stu-id="4aac6-122">SET</span></span>  
  
- <span data-ttu-id="4aac6-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="4aac6-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="4aac6-124">項目述語 (等価)</span><span class="sxs-lookup"><span data-stu-id="4aac6-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="4aac6-125">IN</span><span class="sxs-lookup"><span data-stu-id="4aac6-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="4aac6-126">サポートされている組み合わせ</span><span class="sxs-lookup"><span data-stu-id="4aac6-126">Supported Combinations</span></span>  

 <span data-ttu-id="4aac6-127">次の表は、各種類の型の比較演算子のサポートされているすべての組み合わせを示します。</span><span class="sxs-lookup"><span data-stu-id="4aac6-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="4aac6-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="4aac6-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="4aac6-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="4aac6-129">**!=**</span></span>|<span data-ttu-id="4aac6-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="4aac6-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="4aac6-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="4aac6-131">**DISTINCT**</span></span>|<span data-ttu-id="4aac6-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="4aac6-132">**UNION**</span></span><br /><br /> <span data-ttu-id="4aac6-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="4aac6-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="4aac6-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="4aac6-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="4aac6-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="4aac6-135">**SET**</span></span><br /><br /> <span data-ttu-id="4aac6-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="4aac6-136">**OVERLAPS**</span></span>|<span data-ttu-id="4aac6-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="4aac6-137">**IN**</span></span>|<span data-ttu-id="4aac6-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="4aac6-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="4aac6-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="4aac6-139">**>   >=**</span></span>|<span data-ttu-id="4aac6-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="4aac6-140">**ORDER BY**</span></span>|<span data-ttu-id="4aac6-141">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="4aac6-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="4aac6-142">**IS NOT NULL**</span><span class="sxs-lookup"><span data-stu-id="4aac6-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="4aac6-143">エンティティ型</span><span class="sxs-lookup"><span data-stu-id="4aac6-143">Entity type</span></span>|<span data-ttu-id="4aac6-144">参照<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="4aac6-145">すべてのプロパティ<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="4aac6-146">すべてのプロパティ<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="4aac6-147">すべてのプロパティ<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="4aac6-148">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-149">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-150">参照<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="4aac6-151">複合型</span><span class="sxs-lookup"><span data-stu-id="4aac6-151">Complex type</span></span>|<span data-ttu-id="4aac6-152">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-153">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-154">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-155">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-156">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-157">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-158">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="4aac6-159">行</span><span class="sxs-lookup"><span data-stu-id="4aac6-159">Row</span></span>|<span data-ttu-id="4aac6-160">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="4aac6-161">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="4aac6-162">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="4aac6-163">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-164">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-165">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="4aac6-166">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="4aac6-167">プリミティブ型</span><span class="sxs-lookup"><span data-stu-id="4aac6-167">Primitive type</span></span>|<span data-ttu-id="4aac6-168">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="4aac6-168">Provider-specific</span></span>|<span data-ttu-id="4aac6-169">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="4aac6-169">Provider-specific</span></span>|<span data-ttu-id="4aac6-170">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="4aac6-170">Provider-specific</span></span>|<span data-ttu-id="4aac6-171">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="4aac6-171">Provider-specific</span></span>|<span data-ttu-id="4aac6-172">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="4aac6-172">Provider-specific</span></span>|<span data-ttu-id="4aac6-173">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="4aac6-173">Provider-specific</span></span>|<span data-ttu-id="4aac6-174">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="4aac6-174">Provider-specific</span></span>|  
|<span data-ttu-id="4aac6-175">マルチセット</span><span class="sxs-lookup"><span data-stu-id="4aac6-175">Multiset</span></span>|<span data-ttu-id="4aac6-176">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-177">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-178">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-179">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-180">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-181">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-182">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="4aac6-183">参照</span><span class="sxs-lookup"><span data-stu-id="4aac6-183">Ref</span></span>|<span data-ttu-id="4aac6-184">○<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="4aac6-185">○<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="4aac6-186">○<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="4aac6-187">○<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="4aac6-188">Throw</span><span class="sxs-lookup"><span data-stu-id="4aac6-188">Throw</span></span>|<span data-ttu-id="4aac6-189">Throw</span><span class="sxs-lookup"><span data-stu-id="4aac6-189">Throw</span></span>|<span data-ttu-id="4aac6-190">○<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="4aac6-191">関連付け</span><span class="sxs-lookup"><span data-stu-id="4aac6-191">Association</span></span><br /><br /> <span data-ttu-id="4aac6-192">型</span><span class="sxs-lookup"><span data-stu-id="4aac6-192">type</span></span>|<span data-ttu-id="4aac6-193">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-194">Throw</span><span class="sxs-lookup"><span data-stu-id="4aac6-194">Throw</span></span>|<span data-ttu-id="4aac6-195">Throw</span><span class="sxs-lookup"><span data-stu-id="4aac6-195">Throw</span></span>|<span data-ttu-id="4aac6-196">Throw</span><span class="sxs-lookup"><span data-stu-id="4aac6-196">Throw</span></span>|<span data-ttu-id="4aac6-197">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-198">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="4aac6-199">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="4aac6-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="4aac6-200"><sup>1</sup> 次の例に示すように、エンティティ型インスタンスの参照は暗黙的に比較されます。</span><span class="sxs-lookup"><span data-stu-id="4aac6-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="4aac6-201">エンティティ インスタンスは、明示的な参照に対して比較できません。</span><span class="sxs-lookup"><span data-stu-id="4aac6-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="4aac6-202">明示的な参照に対する比較を行った場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4aac6-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="4aac6-203">たとえば、次のクエリを実行すると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4aac6-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="4aac6-204"><sup>2</sup> 複合型のプロパティは、ストアに送信される前にフラット化されるので、比較が可能になります (すべてのプロパティが比較可能である場合)。</span><span class="sxs-lookup"><span data-stu-id="4aac6-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="4aac6-205"><sup>4</sup> も参照してください。</span><span class="sxs-lookup"><span data-stu-id="4aac6-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="4aac6-206"><sup>3</sup> Entity Framework ランタイムでは、サポートされていないケースが検出され、プロバイダー/ストアは呼び出されずに、意味のある例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4aac6-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="4aac6-207"><sup>4</sup> すべてのプロパティの比較が試行されます。</span><span class="sxs-lookup"><span data-stu-id="4aac6-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="4aac6-208">比較不能な型のプロパティ (text、ntext、image など) がある場合、サーバー例外がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="4aac6-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="4aac6-209"><sup>5</sup> 参照のすべての個々の要素 (エンティティ セット名およびエンティティ型のすべてのキー プロパティを含む) が比較されます。</span><span class="sxs-lookup"><span data-stu-id="4aac6-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aac6-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="4aac6-210">See also</span></span>

- [<span data-ttu-id="4aac6-211">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="4aac6-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
