---
title: Entity SQL クイック リファレンス
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: fc7cf8f8f692f9dc4230569d5f575b6d5fad19fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150351"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="9df26-102">Entity SQL クイック リファレンス</span><span class="sxs-lookup"><span data-stu-id="9df26-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="9df26-103">このトピックでは、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] クエリのクイック リファレンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="9df26-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="9df26-104">このトピックのクエリでは、AdventureWorks Sales Model が使用されています。</span><span class="sxs-lookup"><span data-stu-id="9df26-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="9df26-105">リテラル</span><span class="sxs-lookup"><span data-stu-id="9df26-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="9df26-106">String</span><span class="sxs-lookup"><span data-stu-id="9df26-106">String</span></span>  
 <span data-ttu-id="9df26-107">Unicode と非 Unicode の文字列リテラルがあります。</span><span class="sxs-lookup"><span data-stu-id="9df26-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="9df26-108">Unicode 文字列は先頭に N が付きます。たとえば、`N'hello'` のようになります。</span><span class="sxs-lookup"><span data-stu-id="9df26-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="9df26-109">非 Unicode 文字列リテラルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9df26-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="9df26-110">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-110">Output:</span></span>  
  
|<span data-ttu-id="9df26-111">[値]</span><span class="sxs-lookup"><span data-stu-id="9df26-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="9df26-112">hello</span><span class="sxs-lookup"><span data-stu-id="9df26-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="9df26-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="9df26-113">DateTime</span></span>  
 <span data-ttu-id="9df26-114">DateTime リテラルでは、日付部分と時刻部分の両方が必須です。</span><span class="sxs-lookup"><span data-stu-id="9df26-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="9df26-115">既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="9df26-115">There are no default values.</span></span>  
  
 <span data-ttu-id="9df26-116">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-116">Example:</span></span>  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="9df26-117">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-117">Output:</span></span>  
  
|<span data-ttu-id="9df26-118">[値]</span><span class="sxs-lookup"><span data-stu-id="9df26-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="9df26-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="9df26-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="9df26-120">整数型</span><span class="sxs-lookup"><span data-stu-id="9df26-120">Integer</span></span>  
 <span data-ttu-id="9df26-121">整数リテラルには Int32 (123) 型、UInt32 (123U) 型、Int64 (123L) 型、および UInt64 (123UL) 型があります。</span><span class="sxs-lookup"><span data-stu-id="9df26-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="9df26-122">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-122">Example:</span></span>  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="9df26-123">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-123">Output:</span></span>  
  
|<span data-ttu-id="9df26-124">[値]</span><span class="sxs-lookup"><span data-stu-id="9df26-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="9df26-125">1</span><span class="sxs-lookup"><span data-stu-id="9df26-125">1</span></span>|  
|<span data-ttu-id="9df26-126">2</span><span class="sxs-lookup"><span data-stu-id="9df26-126">2</span></span>|  
|<span data-ttu-id="9df26-127">3</span><span class="sxs-lookup"><span data-stu-id="9df26-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="9df26-128">その他</span><span class="sxs-lookup"><span data-stu-id="9df26-128">Other</span></span>  
 <span data-ttu-id="9df26-129">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] でサポートされているその他のリテラルは、Guid、Binary、Float/Double、Decimal、および `null` です。</span><span class="sxs-lookup"><span data-stu-id="9df26-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="9df26-130">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] の NULL リテラルは、概念モデルのその他すべての型と互換性があると見なされます。</span><span class="sxs-lookup"><span data-stu-id="9df26-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="9df26-131">型コンストラクター</span><span class="sxs-lookup"><span data-stu-id="9df26-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="9df26-132">ROW</span><span class="sxs-lookup"><span data-stu-id="9df26-132">ROW</span></span>  
 <span data-ttu-id="9df26-133">[ROW](row-entity-sql.md) では、`ROW(1 AS myNumber, ‘Name’ AS myName).` のように、構造的に型付けされた匿名のレコード値が作成されます。</span><span class="sxs-lookup"><span data-stu-id="9df26-133">[ROW](row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="9df26-134">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-134">Example:</span></span>  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 <span data-ttu-id="9df26-135">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-135">Output:</span></span>  
  
|<span data-ttu-id="9df26-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="9df26-136">ProductID</span></span>|<span data-ttu-id="9df26-137">名前</span><span class="sxs-lookup"><span data-stu-id="9df26-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="9df26-138">1</span><span class="sxs-lookup"><span data-stu-id="9df26-138">1</span></span>|<span data-ttu-id="9df26-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="9df26-139">Adjustable Race</span></span>|  
|<span data-ttu-id="9df26-140">879</span><span class="sxs-lookup"><span data-stu-id="9df26-140">879</span></span>|<span data-ttu-id="9df26-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="9df26-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="9df26-142">712</span><span class="sxs-lookup"><span data-stu-id="9df26-142">712</span></span>|<span data-ttu-id="9df26-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="9df26-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="9df26-144">...</span><span class="sxs-lookup"><span data-stu-id="9df26-144">...</span></span>|<span data-ttu-id="9df26-145">...</span><span class="sxs-lookup"><span data-stu-id="9df26-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="9df26-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="9df26-146">MULTISET</span></span>  
 <span data-ttu-id="9df26-147">[MULTISET](multiset-entity-sql.md) では、次のようなコレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9df26-147">[MULTISET](multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="9df26-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="9df26-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="9df26-149">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-149">Example:</span></span>  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="9df26-150">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-150">Output:</span></span>  
  
|<span data-ttu-id="9df26-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="9df26-151">ProductID</span></span>|<span data-ttu-id="9df26-152">名前</span><span class="sxs-lookup"><span data-stu-id="9df26-152">Name</span></span>|<span data-ttu-id="9df26-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="9df26-153">ProductNumber</span></span>|<span data-ttu-id="9df26-154">…</span><span class="sxs-lookup"><span data-stu-id="9df26-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="9df26-155">842</span><span class="sxs-lookup"><span data-stu-id="9df26-155">842</span></span>|<span data-ttu-id="9df26-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="9df26-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="9df26-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="9df26-157">PA-T100</span></span>|<span data-ttu-id="9df26-158">…</span><span class="sxs-lookup"><span data-stu-id="9df26-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="9df26-159">Object</span><span class="sxs-lookup"><span data-stu-id="9df26-159">Object</span></span>  
 <span data-ttu-id="9df26-160">[名前付きの型コンストラクター](named-type-constructor-entity-sql.md)では、`person("abc", 12)` のように、名前付きのユーザー定義オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9df26-160">[Named Type Constructor](named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="9df26-161">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-161">Example:</span></span>  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail
AS o  
```  
  
 <span data-ttu-id="9df26-162">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-162">Output:</span></span>  
  
|<span data-ttu-id="9df26-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="9df26-163">SalesOrderDetailID</span></span>|<span data-ttu-id="9df26-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="9df26-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="9df26-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="9df26-165">OrderQty</span></span>|<span data-ttu-id="9df26-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="9df26-166">ProductID</span></span>|<span data-ttu-id="9df26-167">...</span><span class="sxs-lookup"><span data-stu-id="9df26-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="9df26-168">1</span><span class="sxs-lookup"><span data-stu-id="9df26-168">1</span></span>|<span data-ttu-id="9df26-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="9df26-169">4911-403C-98</span></span>|<span data-ttu-id="9df26-170">1</span><span class="sxs-lookup"><span data-stu-id="9df26-170">1</span></span>|<span data-ttu-id="9df26-171">776</span><span class="sxs-lookup"><span data-stu-id="9df26-171">776</span></span>|<span data-ttu-id="9df26-172">...</span><span class="sxs-lookup"><span data-stu-id="9df26-172">...</span></span>|  
|<span data-ttu-id="9df26-173">2</span><span class="sxs-lookup"><span data-stu-id="9df26-173">2</span></span>|<span data-ttu-id="9df26-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="9df26-174">4911-403C-98</span></span>|<span data-ttu-id="9df26-175">3</span><span class="sxs-lookup"><span data-stu-id="9df26-175">3</span></span>|<span data-ttu-id="9df26-176">777</span><span class="sxs-lookup"><span data-stu-id="9df26-176">777</span></span>|<span data-ttu-id="9df26-177">...</span><span class="sxs-lookup"><span data-stu-id="9df26-177">...</span></span>|  
|<span data-ttu-id="9df26-178">...</span><span class="sxs-lookup"><span data-stu-id="9df26-178">...</span></span>|<span data-ttu-id="9df26-179">...</span><span class="sxs-lookup"><span data-stu-id="9df26-179">...</span></span>|<span data-ttu-id="9df26-180">...</span><span class="sxs-lookup"><span data-stu-id="9df26-180">...</span></span>|<span data-ttu-id="9df26-181">...</span><span class="sxs-lookup"><span data-stu-id="9df26-181">...</span></span>|<span data-ttu-id="9df26-182">...</span><span class="sxs-lookup"><span data-stu-id="9df26-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="9df26-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="9df26-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="9df26-184">REF</span><span class="sxs-lookup"><span data-stu-id="9df26-184">REF</span></span>  
 <span data-ttu-id="9df26-185">[REF](ref-entity-sql.md) では、エンティティ型のインスタンスへの参照が作成されます。</span><span class="sxs-lookup"><span data-stu-id="9df26-185">[REF](ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="9df26-186">たとえば、次のクエリは、Orders エンティティ セットの各 Order エンティティへの参照を返します。</span><span class="sxs-lookup"><span data-stu-id="9df26-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="9df26-187">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-187">Output:</span></span>  
  
|<span data-ttu-id="9df26-188">[値]</span><span class="sxs-lookup"><span data-stu-id="9df26-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="9df26-189">1</span><span class="sxs-lookup"><span data-stu-id="9df26-189">1</span></span>|  
|<span data-ttu-id="9df26-190">2</span><span class="sxs-lookup"><span data-stu-id="9df26-190">2</span></span>|  
|<span data-ttu-id="9df26-191">3</span><span class="sxs-lookup"><span data-stu-id="9df26-191">3</span></span>|  
|<span data-ttu-id="9df26-192">...</span><span class="sxs-lookup"><span data-stu-id="9df26-192">...</span></span>|  
  
 <span data-ttu-id="9df26-193">次の例では、プロパティ抽出演算子 (.) を使用して、エンティティのプロパティにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9df26-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="9df26-194">プロパティ抽出演算子を使用すると、参照は自動的に逆参照されます。</span><span class="sxs-lookup"><span data-stu-id="9df26-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="9df26-195">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-195">Example:</span></span>  
  
```sql  
SELECT VALUE REF(p).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="9df26-196">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-196">Output:</span></span>  
  
|<span data-ttu-id="9df26-197">[値]</span><span class="sxs-lookup"><span data-stu-id="9df26-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="9df26-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="9df26-198">Adjustable Race</span></span>|  
|<span data-ttu-id="9df26-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="9df26-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="9df26-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="9df26-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="9df26-201">...</span><span class="sxs-lookup"><span data-stu-id="9df26-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="9df26-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="9df26-202">DEREF</span></span>  
 <span data-ttu-id="9df26-203">[DEREF](deref-entity-sql.md) では、参照値が逆参照されて、その逆参照の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="9df26-203">[DEREF](deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="9df26-204">たとえば、次のクエリは、`SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2` のように、Orders エンティティ セットの各 Order について Order エンティティを生成します。</span><span class="sxs-lookup"><span data-stu-id="9df26-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="9df26-205">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-205">Example:</span></span>  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="9df26-206">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-206">Output:</span></span>  
  
|<span data-ttu-id="9df26-207">[値]</span><span class="sxs-lookup"><span data-stu-id="9df26-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="9df26-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="9df26-208">Adjustable Race</span></span>|  
|<span data-ttu-id="9df26-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="9df26-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="9df26-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="9df26-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="9df26-211">...</span><span class="sxs-lookup"><span data-stu-id="9df26-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="9df26-212">CREATEREF と KEY</span><span class="sxs-lookup"><span data-stu-id="9df26-212">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="9df26-213">[CREATEREF](createref-entity-sql.md) では、キーを渡す参照が作成されます。</span><span class="sxs-lookup"><span data-stu-id="9df26-213">[CREATEREF](createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="9df26-214">[KEY](key-entity-sql.md) では、型参照を持つ式のキー部分が抽出されます。</span><span class="sxs-lookup"><span data-stu-id="9df26-214">[KEY](key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="9df26-215">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-215">Example:</span></span>  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))
    FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="9df26-216">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-216">Output:</span></span>  
  
|<span data-ttu-id="9df26-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="9df26-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="9df26-218">980</span><span class="sxs-lookup"><span data-stu-id="9df26-218">980</span></span>|  
|<span data-ttu-id="9df26-219">365</span><span class="sxs-lookup"><span data-stu-id="9df26-219">365</span></span>|  
|<span data-ttu-id="9df26-220">771</span><span class="sxs-lookup"><span data-stu-id="9df26-220">771</span></span>|  
|<span data-ttu-id="9df26-221">...</span><span class="sxs-lookup"><span data-stu-id="9df26-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="9df26-222">関数</span><span class="sxs-lookup"><span data-stu-id="9df26-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="9df26-223">正規</span><span class="sxs-lookup"><span data-stu-id="9df26-223">Canonical</span></span>  
 <span data-ttu-id="9df26-224">[正規関数](canonical-functions.md)の名前空間は Edm で、`Edm.Length("string")` のように使用されます。</span><span class="sxs-lookup"><span data-stu-id="9df26-224">The namespace for [canonical functions](canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="9df26-225">正規関数と同じ名前の関数を含んでいる別の名前空間がインポートされない限り、名前空間を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9df26-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="9df26-226">2 つの名前空間に同じ関数が存在する場合は、完全な名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9df26-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="9df26-227">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-227">Example:</span></span>  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="9df26-228">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-228">Output:</span></span>  
  
|<span data-ttu-id="9df26-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="9df26-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="9df26-230">6</span><span class="sxs-lookup"><span data-stu-id="9df26-230">6</span></span>|  
|<span data-ttu-id="9df26-231">6</span><span class="sxs-lookup"><span data-stu-id="9df26-231">6</span></span>|  
|<span data-ttu-id="9df26-232">5</span><span class="sxs-lookup"><span data-stu-id="9df26-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="9df26-233">Microsoft プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="9df26-233">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="9df26-234">[Microsoft プロバイダー固有の関数](../sqlclient-for-ef-functions.md)は、`SqlServer` 名前空間にあります。</span><span class="sxs-lookup"><span data-stu-id="9df26-234">[Microsoft provider-specific functions](../sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="9df26-235">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-235">Example:</span></span>  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="9df26-236">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-236">Output:</span></span>  
  
|<span data-ttu-id="9df26-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="9df26-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="9df26-238">27</span><span class="sxs-lookup"><span data-stu-id="9df26-238">27</span></span>|  
|<span data-ttu-id="9df26-239">27</span><span class="sxs-lookup"><span data-stu-id="9df26-239">27</span></span>|  
|<span data-ttu-id="9df26-240">26</span><span class="sxs-lookup"><span data-stu-id="9df26-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="9df26-241">名前空間</span><span class="sxs-lookup"><span data-stu-id="9df26-241">Namespaces</span></span>  
 <span data-ttu-id="9df26-242">[USING](using-entity-sql.md) では、クエリ式で使用する名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="9df26-242">[USING](using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="9df26-243">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-243">Example:</span></span>  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="9df26-244">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-244">Output:</span></span>  
  
|<span data-ttu-id="9df26-245">[値]</span><span class="sxs-lookup"><span data-stu-id="9df26-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="9df26-246">aa</span><span class="sxs-lookup"><span data-stu-id="9df26-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="9df26-247">ページング</span><span class="sxs-lookup"><span data-stu-id="9df26-247">Paging</span></span>  
 <span data-ttu-id="9df26-248">ページングは、[ORDER BY](order-by-entity-sql.md) 句に対して [SKIP](skip-entity-sql.md) および [LIMIT](limit-entity-sql.md) サブ句を宣言することによって表すことができます。</span><span class="sxs-lookup"><span data-stu-id="9df26-248">Paging can be expressed by declaring a [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses to the [ORDER BY](order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="9df26-249">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-249">Example:</span></span>  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="9df26-250">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-250">Output:</span></span>  
  
|<span data-ttu-id="9df26-251">ID</span><span class="sxs-lookup"><span data-stu-id="9df26-251">ID</span></span>|<span data-ttu-id="9df26-252">名前</span><span class="sxs-lookup"><span data-stu-id="9df26-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="9df26-253">10</span><span class="sxs-lookup"><span data-stu-id="9df26-253">10</span></span>|<span data-ttu-id="9df26-254">Adina</span><span class="sxs-lookup"><span data-stu-id="9df26-254">Adina</span></span>|  
|<span data-ttu-id="9df26-255">11</span><span class="sxs-lookup"><span data-stu-id="9df26-255">11</span></span>|<span data-ttu-id="9df26-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="9df26-256">Agcaoili</span></span>|  
|<span data-ttu-id="9df26-257">12</span><span class="sxs-lookup"><span data-stu-id="9df26-257">12</span></span>|<span data-ttu-id="9df26-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="9df26-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="9df26-259">グループ化</span><span class="sxs-lookup"><span data-stu-id="9df26-259">Grouping</span></span>  
 <span data-ttu-id="9df26-260">[GROUPING BY](group-by-entity-sql.md) では、クエリ ([SELECT](select-entity-sql.md)) 式によって返されるオブジェクトをグループ化するよう指定します。</span><span class="sxs-lookup"><span data-stu-id="9df26-260">[GROUPING BY](group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="9df26-261">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-261">Example:</span></span>  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="9df26-262">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-262">Output:</span></span>  
  
|<span data-ttu-id="9df26-263">name</span><span class="sxs-lookup"><span data-stu-id="9df26-263">name</span></span>|  
|----------|  
|<span data-ttu-id="9df26-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="9df26-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="9df26-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="9df26-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="9df26-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="9df26-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="9df26-267">...</span><span class="sxs-lookup"><span data-stu-id="9df26-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="9df26-268">ナビゲーション</span><span class="sxs-lookup"><span data-stu-id="9df26-268">Navigation</span></span>  
 <span data-ttu-id="9df26-269">リレーションシップ ナビゲーション操作を使用すると、開始側のエンティティと終了側のエンティティ間のリレーションシップをナビゲートできます。</span><span class="sxs-lookup"><span data-stu-id="9df26-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="9df26-270">[NAVIGATE](navigate-entity-sql.md) では、\<名前空間>.\<リレーションシップ型名> として修飾されるリレーションシップ型が取得されます。</span><span class="sxs-lookup"><span data-stu-id="9df26-270">[NAVIGATE](navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="9df26-271">終了側のカーディナリティが 1 の場合、Ref\<T> が返されます。</span><span class="sxs-lookup"><span data-stu-id="9df26-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="9df26-272">終了側のカーディナリティが n の場合、Collection<Ref\<T>> が返されます。</span><span class="sxs-lookup"><span data-stu-id="9df26-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="9df26-273">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-273">Example:</span></span>  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="9df26-274">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-274">Output:</span></span>  
  
|<span data-ttu-id="9df26-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="9df26-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="9df26-276">1</span><span class="sxs-lookup"><span data-stu-id="9df26-276">1</span></span>|  
|<span data-ttu-id="9df26-277">2</span><span class="sxs-lookup"><span data-stu-id="9df26-277">2</span></span>|  
|<span data-ttu-id="9df26-278">3</span><span class="sxs-lookup"><span data-stu-id="9df26-278">3</span></span>|  
|<span data-ttu-id="9df26-279">...</span><span class="sxs-lookup"><span data-stu-id="9df26-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="9df26-280">SELECT VALUE AND SELECT</span><span class="sxs-lookup"><span data-stu-id="9df26-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="9df26-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="9df26-281">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="9df26-282">には、暗黙の行の構築をスキップする SELECT VALUE 句が用意されています。</span><span class="sxs-lookup"><span data-stu-id="9df26-282">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="9df26-283">SELECT VALUE 句には 1 つの項目のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9df26-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="9df26-284">このような句を使用した場合、SELECT 句内の項目には row ラッパーは構築されず、`SELECT VALUE a` などの目的の構造を持つコレクションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9df26-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="9df26-285">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-285">Example:</span></span>  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="9df26-286">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-286">Output:</span></span>  
  
|<span data-ttu-id="9df26-287">名前</span><span class="sxs-lookup"><span data-stu-id="9df26-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="9df26-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="9df26-288">Adjustable Race</span></span>|  
|<span data-ttu-id="9df26-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="9df26-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="9df26-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="9df26-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="9df26-291">...</span><span class="sxs-lookup"><span data-stu-id="9df26-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="9df26-292">SELECT</span><span class="sxs-lookup"><span data-stu-id="9df26-292">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="9df26-293">には、任意の行を構築するための行コンストラクターも用意されています。</span><span class="sxs-lookup"><span data-stu-id="9df26-293">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="9df26-294">SELECT は、投影内の 1 つまたは複数の要素、および `SELECT a, b, c` などのフィールドを持つデータ レコードの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="9df26-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="9df26-295">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-295">Example:</span></span>  
  
 <span data-ttu-id="9df26-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="9df26-297">名前</span><span class="sxs-lookup"><span data-stu-id="9df26-297">Name</span></span>|<span data-ttu-id="9df26-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="9df26-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="9df26-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="9df26-299">Adjustable Race</span></span>|<span data-ttu-id="9df26-300">1</span><span class="sxs-lookup"><span data-stu-id="9df26-300">1</span></span>|  
|<span data-ttu-id="9df26-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="9df26-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="9df26-302">879</span><span class="sxs-lookup"><span data-stu-id="9df26-302">879</span></span>|  
|<span data-ttu-id="9df26-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="9df26-303">AWC Logo Cap</span></span>|<span data-ttu-id="9df26-304">712</span><span class="sxs-lookup"><span data-stu-id="9df26-304">712</span></span>|  
|<span data-ttu-id="9df26-305">...</span><span class="sxs-lookup"><span data-stu-id="9df26-305">...</span></span>|<span data-ttu-id="9df26-306">...</span><span class="sxs-lookup"><span data-stu-id="9df26-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="9df26-307">CASE 式</span><span class="sxs-lookup"><span data-stu-id="9df26-307">CASE EXPRESSION</span></span>  
 <span data-ttu-id="9df26-308">[CASE 式](case-entity-sql.md)では、一連のブール式が評価されて結果が判定されます。</span><span class="sxs-lookup"><span data-stu-id="9df26-308">The [case expression](case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="9df26-309">例:</span><span class="sxs-lookup"><span data-stu-id="9df26-309">Example:</span></span>  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="9df26-310">Output:</span><span class="sxs-lookup"><span data-stu-id="9df26-310">Output:</span></span>  
  
|<span data-ttu-id="9df26-311">[値]</span><span class="sxs-lookup"><span data-stu-id="9df26-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="9df26-312">true</span><span class="sxs-lookup"><span data-stu-id="9df26-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9df26-313">関連項目</span><span class="sxs-lookup"><span data-stu-id="9df26-313">See also</span></span>

- [<span data-ttu-id="9df26-314">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="9df26-314">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="9df26-315">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="9df26-315">Entity SQL Overview</span></span>](entity-sql-overview.md)
