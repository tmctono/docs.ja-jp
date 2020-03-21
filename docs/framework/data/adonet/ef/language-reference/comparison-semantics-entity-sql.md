---
title: 比較セマンティクス (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 57d81d4b581df76a4382ad5e1d72fe8250b10d43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150455"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="5dd64-102">比較セマンティクス (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5dd64-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="5dd64-103">次のいずれかの [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 演算子を実行すると、型インスタンスの比較が行われます。</span><span class="sxs-lookup"><span data-stu-id="5dd64-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="5dd64-104">明示的な比較</span><span class="sxs-lookup"><span data-stu-id="5dd64-104">Explicit comparison</span></span>  
 <span data-ttu-id="5dd64-105">等価演算</span><span class="sxs-lookup"><span data-stu-id="5dd64-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="5dd64-106">!=</span><span class="sxs-lookup"><span data-stu-id="5dd64-106">!=</span></span>  
  
 <span data-ttu-id="5dd64-107">順序付け操作</span><span class="sxs-lookup"><span data-stu-id="5dd64-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="5dd64-108">NULL 値が許容される操作</span><span class="sxs-lookup"><span data-stu-id="5dd64-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="5dd64-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="5dd64-109">IS NULL</span></span>  
  
- <span data-ttu-id="5dd64-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5dd64-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="5dd64-111">明示的な区別</span><span class="sxs-lookup"><span data-stu-id="5dd64-111">Explicit distinction</span></span>  
 <span data-ttu-id="5dd64-112">等価区別</span><span class="sxs-lookup"><span data-stu-id="5dd64-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="5dd64-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="5dd64-113">DISTINCT</span></span>  
  
- <span data-ttu-id="5dd64-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="5dd64-114">GROUP BY</span></span>  
  
 <span data-ttu-id="5dd64-115">順序付け区別</span><span class="sxs-lookup"><span data-stu-id="5dd64-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="5dd64-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="5dd64-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="5dd64-117">暗黙的な区別</span><span class="sxs-lookup"><span data-stu-id="5dd64-117">Implicit distinction</span></span>  
 <span data-ttu-id="5dd64-118">設定操作および述語 (等価)</span><span class="sxs-lookup"><span data-stu-id="5dd64-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="5dd64-119">UNION</span><span class="sxs-lookup"><span data-stu-id="5dd64-119">UNION</span></span>  
  
- <span data-ttu-id="5dd64-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="5dd64-120">INTERSECT</span></span>  
  
- <span data-ttu-id="5dd64-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="5dd64-121">EXCEPT</span></span>  
  
- <span data-ttu-id="5dd64-122">SET</span><span class="sxs-lookup"><span data-stu-id="5dd64-122">SET</span></span>  
  
- <span data-ttu-id="5dd64-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="5dd64-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="5dd64-124">項目述語 (等価)</span><span class="sxs-lookup"><span data-stu-id="5dd64-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="5dd64-125">IN</span><span class="sxs-lookup"><span data-stu-id="5dd64-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="5dd64-126">サポートされる組み合わせ</span><span class="sxs-lookup"><span data-stu-id="5dd64-126">Supported Combinations</span></span>  
 <span data-ttu-id="5dd64-127">次の表は、各種類の型の比較演算子のサポートされているすべての組み合わせを示します。</span><span class="sxs-lookup"><span data-stu-id="5dd64-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="5dd64-128">**種類**</span><span class="sxs-lookup"><span data-stu-id="5dd64-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="5dd64-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="5dd64-129">**!=**</span></span>|<span data-ttu-id="5dd64-130">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="5dd64-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="5dd64-131">**異なる**</span><span class="sxs-lookup"><span data-stu-id="5dd64-131">**DISTINCT**</span></span>|<span data-ttu-id="5dd64-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="5dd64-132">**UNION**</span></span><br /><br /> <span data-ttu-id="5dd64-133">**交差**</span><span class="sxs-lookup"><span data-stu-id="5dd64-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="5dd64-134">**除いて**</span><span class="sxs-lookup"><span data-stu-id="5dd64-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="5dd64-135">**設定**</span><span class="sxs-lookup"><span data-stu-id="5dd64-135">**SET**</span></span><br /><br /> <span data-ttu-id="5dd64-136">**重複**</span><span class="sxs-lookup"><span data-stu-id="5dd64-136">**OVERLAPS**</span></span>|<span data-ttu-id="5dd64-137">**インチ**</span><span class="sxs-lookup"><span data-stu-id="5dd64-137">**IN**</span></span>|<span data-ttu-id="5dd64-138">**<<=**</span><span class="sxs-lookup"><span data-stu-id="5dd64-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="5dd64-139">**>>=**</span><span class="sxs-lookup"><span data-stu-id="5dd64-139">**>   >=**</span></span>|<span data-ttu-id="5dd64-140">**注文方法**</span><span class="sxs-lookup"><span data-stu-id="5dd64-140">**ORDER BY**</span></span>|<span data-ttu-id="5dd64-141">**NULL です**</span><span class="sxs-lookup"><span data-stu-id="5dd64-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="5dd64-142">**NULL ではありません**</span><span class="sxs-lookup"><span data-stu-id="5dd64-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="5dd64-143">エンティティの種類</span><span class="sxs-lookup"><span data-stu-id="5dd64-143">Entity type</span></span>|<span data-ttu-id="5dd64-144">参照<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="5dd64-145">すべてのプロパティ<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="5dd64-146">すべてのプロパティ<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="5dd64-147">すべてのプロパティ<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="5dd64-148">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-149">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-150">参照<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="5dd64-151">複合型</span><span class="sxs-lookup"><span data-stu-id="5dd64-151">Complex type</span></span>|<span data-ttu-id="5dd64-152">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-153">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-154">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-155">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-156">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-157">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-158">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="5dd64-159">行</span><span class="sxs-lookup"><span data-stu-id="5dd64-159">Row</span></span>|<span data-ttu-id="5dd64-160">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="5dd64-161">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="5dd64-162">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="5dd64-163">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-164">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-165">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="5dd64-166">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="5dd64-167">プリミティブ型</span><span class="sxs-lookup"><span data-stu-id="5dd64-167">Primitive type</span></span>|<span data-ttu-id="5dd64-168">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="5dd64-168">Provider-specific</span></span>|<span data-ttu-id="5dd64-169">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="5dd64-169">Provider-specific</span></span>|<span data-ttu-id="5dd64-170">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="5dd64-170">Provider-specific</span></span>|<span data-ttu-id="5dd64-171">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="5dd64-171">Provider-specific</span></span>|<span data-ttu-id="5dd64-172">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="5dd64-172">Provider-specific</span></span>|<span data-ttu-id="5dd64-173">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="5dd64-173">Provider-specific</span></span>|<span data-ttu-id="5dd64-174">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="5dd64-174">Provider-specific</span></span>|  
|<span data-ttu-id="5dd64-175">マルチセット</span><span class="sxs-lookup"><span data-stu-id="5dd64-175">Multiset</span></span>|<span data-ttu-id="5dd64-176">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-177">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-178">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-179">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-180">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-181">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-182">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="5dd64-183">参照</span><span class="sxs-lookup"><span data-stu-id="5dd64-183">Ref</span></span>|<span data-ttu-id="5dd64-184">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="5dd64-185">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="5dd64-186">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="5dd64-187">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="5dd64-188">Throw</span><span class="sxs-lookup"><span data-stu-id="5dd64-188">Throw</span></span>|<span data-ttu-id="5dd64-189">Throw</span><span class="sxs-lookup"><span data-stu-id="5dd64-189">Throw</span></span>|<span data-ttu-id="5dd64-190">はい<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="5dd64-191">アソシエーション</span><span class="sxs-lookup"><span data-stu-id="5dd64-191">Association</span></span><br /><br /> <span data-ttu-id="5dd64-192">type</span><span class="sxs-lookup"><span data-stu-id="5dd64-192">type</span></span>|<span data-ttu-id="5dd64-193">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-194">Throw</span><span class="sxs-lookup"><span data-stu-id="5dd64-194">Throw</span></span>|<span data-ttu-id="5dd64-195">Throw</span><span class="sxs-lookup"><span data-stu-id="5dd64-195">Throw</span></span>|<span data-ttu-id="5dd64-196">Throw</span><span class="sxs-lookup"><span data-stu-id="5dd64-196">Throw</span></span>|<span data-ttu-id="5dd64-197">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-198">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="5dd64-199">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="5dd64-200"><sup>1</sup>次の例に示すように、指定されたエンティティ型インスタンスの参照は暗黙的に比較されます。</span><span class="sxs-lookup"><span data-stu-id="5dd64-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="5dd64-201">エンティティ インスタンスは、明示的な参照に対して比較できません。</span><span class="sxs-lookup"><span data-stu-id="5dd64-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="5dd64-202">明示的な参照に対する比較を行った場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5dd64-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="5dd64-203">たとえば、次のクエリを実行すると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5dd64-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="5dd64-204"><sup>2</sup>複合型のプロパティは、ストアに送信される前にフラット化されるため、(すべてのプロパティが同等である限り)、同等になります。</span><span class="sxs-lookup"><span data-stu-id="5dd64-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="5dd64-205">4 も参照してください<sup>。</sup></span><span class="sxs-lookup"><span data-stu-id="5dd64-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="5dd64-206"><sup>3</sup>Entity Framework ランタイムは、サポートされていないケースを検出し、プロバイダー/ストアを使用せずに意味のある例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="5dd64-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="5dd64-207"><sup>4</sup>すべてのプロパティを比較しようとしました。</span><span class="sxs-lookup"><span data-stu-id="5dd64-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="5dd64-208">比較不能な型のプロパティ (text、ntext、image など) がある場合、サーバー例外がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="5dd64-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="5dd64-209"><sup>5</sup>参照のすべての要素が比較されます (これには、エンティティ セット名とエンティティ型のすべてのキー プロパティが含まれます)。</span><span class="sxs-lookup"><span data-stu-id="5dd64-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dd64-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="5dd64-210">See also</span></span>

- [<span data-ttu-id="5dd64-211">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="5dd64-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
