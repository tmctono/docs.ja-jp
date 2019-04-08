---
title: 比較セマンティクス (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 6b4c4177ebd6c45e00a1ac7774e40a43e0c14a74
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083336"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="81710-102">比較セマンティクス (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="81710-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="81710-103">次のいずれかの [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 演算子を実行すると、型インスタンスの比較が行われます。</span><span class="sxs-lookup"><span data-stu-id="81710-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="81710-104">明示的な比較</span><span class="sxs-lookup"><span data-stu-id="81710-104">Explicit comparison</span></span>  
 <span data-ttu-id="81710-105">等価演算</span><span class="sxs-lookup"><span data-stu-id="81710-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="81710-106">!=</span><span class="sxs-lookup"><span data-stu-id="81710-106">!=</span></span>  
  
 <span data-ttu-id="81710-107">順序付け操作</span><span class="sxs-lookup"><span data-stu-id="81710-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 <span data-ttu-id="81710-108">NULL 値が許容される操作</span><span class="sxs-lookup"><span data-stu-id="81710-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="81710-109">IS_NULL</span><span class="sxs-lookup"><span data-stu-id="81710-109">IS NULL</span></span>  
  
-   <span data-ttu-id="81710-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="81710-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="81710-111">明示的な区別</span><span class="sxs-lookup"><span data-stu-id="81710-111">Explicit distinction</span></span>  
 <span data-ttu-id="81710-112">等価区別</span><span class="sxs-lookup"><span data-stu-id="81710-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="81710-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="81710-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="81710-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="81710-114">GROUP BY</span></span>  
  
 <span data-ttu-id="81710-115">順序付け区別</span><span class="sxs-lookup"><span data-stu-id="81710-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="81710-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="81710-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="81710-117">暗黙的な区別</span><span class="sxs-lookup"><span data-stu-id="81710-117">Implicit distinction</span></span>  
 <span data-ttu-id="81710-118">設定操作および述語 (等価)</span><span class="sxs-lookup"><span data-stu-id="81710-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="81710-119">UNION</span><span class="sxs-lookup"><span data-stu-id="81710-119">UNION</span></span>  
  
-   <span data-ttu-id="81710-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="81710-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="81710-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="81710-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="81710-122">SET</span><span class="sxs-lookup"><span data-stu-id="81710-122">SET</span></span>  
  
-   <span data-ttu-id="81710-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="81710-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="81710-124">項目述語 (等価)</span><span class="sxs-lookup"><span data-stu-id="81710-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="81710-125">IN</span><span class="sxs-lookup"><span data-stu-id="81710-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="81710-126">サポートされている組み合わせ</span><span class="sxs-lookup"><span data-stu-id="81710-126">Supported Combinations</span></span>  
 <span data-ttu-id="81710-127">次の表は、各種類の型の比較演算子のサポートされているすべての組み合わせを示します。</span><span class="sxs-lookup"><span data-stu-id="81710-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|**<span data-ttu-id="81710-128">型</span><span class="sxs-lookup"><span data-stu-id="81710-128">Type</span></span>**|**=**<br /><br /> **<span data-ttu-id="81710-129">!=</span><span class="sxs-lookup"><span data-stu-id="81710-129">!=</span></span>**|**<span data-ttu-id="81710-130">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="81710-130">GROUP BY</span></span>**<br /><br /> **<span data-ttu-id="81710-131">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="81710-131">DISTINCT</span></span>**|**<span data-ttu-id="81710-132">UNION</span><span class="sxs-lookup"><span data-stu-id="81710-132">UNION</span></span>**<br /><br /> **<span data-ttu-id="81710-133">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="81710-133">INTERSECT</span></span>**<br /><br /> **<span data-ttu-id="81710-134">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="81710-134">EXCEPT</span></span>**<br /><br /> **<span data-ttu-id="81710-135">SET</span><span class="sxs-lookup"><span data-stu-id="81710-135">SET</span></span>**<br /><br /> **<span data-ttu-id="81710-136">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="81710-136">OVERLAPS</span></span>**|**<span data-ttu-id="81710-137">IN</span><span class="sxs-lookup"><span data-stu-id="81710-137">IN</span></span>**|**<span data-ttu-id="81710-138"><   <=</span><span class="sxs-lookup"><span data-stu-id="81710-138"><   <=</span></span>**<br /><br /> **<span data-ttu-id="81710-139">>   >=</span><span class="sxs-lookup"><span data-stu-id="81710-139">>   >=</span></span>**|**<span data-ttu-id="81710-140">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="81710-140">ORDER BY</span></span>**|**<span data-ttu-id="81710-141">IS_NULL</span><span class="sxs-lookup"><span data-stu-id="81710-141">IS NULL</span></span>**<br /><br /> **<span data-ttu-id="81710-142">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="81710-142">IS NOT NULL</span></span>**|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="81710-143">エンティティ型</span><span class="sxs-lookup"><span data-stu-id="81710-143">Entity type</span></span>|<span data-ttu-id="81710-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="81710-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="81710-145">すべてのプロパティ<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="81710-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="81710-146">すべてのプロパティ<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="81710-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="81710-147">すべてのプロパティ<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="81710-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="81710-148">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-149">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="81710-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="81710-151">複合型</span><span class="sxs-lookup"><span data-stu-id="81710-151">Complex type</span></span>|<span data-ttu-id="81710-152">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-153">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-154">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-155">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-156">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-157">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-158">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="81710-159">行</span><span class="sxs-lookup"><span data-stu-id="81710-159">Row</span></span>|<span data-ttu-id="81710-160">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="81710-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="81710-161">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="81710-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="81710-162">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="81710-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="81710-163">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-164">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-165">すべてのプロパティ<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="81710-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="81710-166">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="81710-167">プリミティブ型</span><span class="sxs-lookup"><span data-stu-id="81710-167">Primitive type</span></span>|<span data-ttu-id="81710-168">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="81710-168">Provider-specific</span></span>|<span data-ttu-id="81710-169">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="81710-169">Provider-specific</span></span>|<span data-ttu-id="81710-170">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="81710-170">Provider-specific</span></span>|<span data-ttu-id="81710-171">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="81710-171">Provider-specific</span></span>|<span data-ttu-id="81710-172">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="81710-172">Provider-specific</span></span>|<span data-ttu-id="81710-173">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="81710-173">Provider-specific</span></span>|<span data-ttu-id="81710-174">プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="81710-174">Provider-specific</span></span>|  
|<span data-ttu-id="81710-175">マルチセット</span><span class="sxs-lookup"><span data-stu-id="81710-175">Multiset</span></span>|<span data-ttu-id="81710-176">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-177">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-178">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-179">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-180">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-181">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-182">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="81710-183">参照</span><span class="sxs-lookup"><span data-stu-id="81710-183">Ref</span></span>|<span data-ttu-id="81710-184">[はい]<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="81710-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="81710-185">[はい]<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="81710-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="81710-186">[はい]<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="81710-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="81710-187">[はい]<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="81710-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="81710-188">Throw</span><span class="sxs-lookup"><span data-stu-id="81710-188">Throw</span></span>|<span data-ttu-id="81710-189">Throw</span><span class="sxs-lookup"><span data-stu-id="81710-189">Throw</span></span>|<span data-ttu-id="81710-190">[はい]<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="81710-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="81710-191">関連付け</span><span class="sxs-lookup"><span data-stu-id="81710-191">Association</span></span><br /><br /> <span data-ttu-id="81710-192">種類</span><span class="sxs-lookup"><span data-stu-id="81710-192">type</span></span>|<span data-ttu-id="81710-193">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-194">Throw</span><span class="sxs-lookup"><span data-stu-id="81710-194">Throw</span></span>|<span data-ttu-id="81710-195">Throw</span><span class="sxs-lookup"><span data-stu-id="81710-195">Throw</span></span>|<span data-ttu-id="81710-196">Throw</span><span class="sxs-lookup"><span data-stu-id="81710-196">Throw</span></span>|<span data-ttu-id="81710-197">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-198">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="81710-199">スロー<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="81710-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="81710-200"><sup>1</sup>特定のエンティティ型のインスタンスの参照は、暗黙的に比較すると、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="81710-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="81710-201">エンティティ インスタンスは、明示的な参照に対して比較できません。</span><span class="sxs-lookup"><span data-stu-id="81710-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="81710-202">明示的な参照に対する比較を行った場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="81710-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="81710-203">たとえば、次のクエリを実行すると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="81710-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="81710-204"><sup>2</sup>複合型のプロパティが比較可能な (ただし、すべてのプロパティが比較可能な) になるように、ストアに送信される前にフラット化します。</span><span class="sxs-lookup"><span data-stu-id="81710-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="81710-205">参照してください<sup>4。</sup></span><span class="sxs-lookup"><span data-stu-id="81710-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="81710-206"><sup>3</sup>Entity Framework ランタイムがサポートされていないケースを検出し、プロバイダー/ストアは呼び出されず、意味のある例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="81710-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="81710-207"><sup>4</sup>すべてのプロパティを比較ましょう。</span><span class="sxs-lookup"><span data-stu-id="81710-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="81710-208">比較不能な型のプロパティ (text、ntext、image など) がある場合、サーバー例外がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="81710-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="81710-209"><sup>5</sup>参照のすべての個々 の要素を比較 (エンティティ セットの名前と、エンティティ型のすべてのキー プロパティを含む)。</span><span class="sxs-lookup"><span data-stu-id="81710-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81710-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="81710-210">See also</span></span>

- [<span data-ttu-id="81710-211">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="81710-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
