---
title: Entity SQL クイック リファレンス
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: 7ec3b6fc184b4f169d6f6489bda0ec8fa4abb4f5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148141"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="75bc1-102">Entity SQL クイック リファレンス</span><span class="sxs-lookup"><span data-stu-id="75bc1-102">Entity SQL Quick Reference</span></span>

<span data-ttu-id="75bc1-103">このトピックでは、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] クエリのクイック リファレンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="75bc1-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="75bc1-104">このトピックのクエリでは、AdventureWorks Sales Model が使用されています。</span><span class="sxs-lookup"><span data-stu-id="75bc1-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="75bc1-105">リテラル</span><span class="sxs-lookup"><span data-stu-id="75bc1-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="75bc1-106">String</span><span class="sxs-lookup"><span data-stu-id="75bc1-106">String</span></span>  

 <span data-ttu-id="75bc1-107">Unicode と非 Unicode の文字列リテラルがあります。</span><span class="sxs-lookup"><span data-stu-id="75bc1-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="75bc1-108">Unicode 文字列は先頭に N が付きます。たとえば、`N'hello'` のようになります。</span><span class="sxs-lookup"><span data-stu-id="75bc1-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="75bc1-109">非 Unicode 文字列リテラルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="75bc1-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="75bc1-110">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-110">Output:</span></span>  
  
|<span data-ttu-id="75bc1-111">[値]</span><span class="sxs-lookup"><span data-stu-id="75bc1-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="75bc1-112">hello</span><span class="sxs-lookup"><span data-stu-id="75bc1-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="75bc1-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="75bc1-113">DateTime</span></span>  

 <span data-ttu-id="75bc1-114">DateTime リテラルでは、日付部分と時刻部分の両方が必須です。</span><span class="sxs-lookup"><span data-stu-id="75bc1-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="75bc1-115">既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="75bc1-115">There are no default values.</span></span>  
  
 <span data-ttu-id="75bc1-116">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-116">Example:</span></span>  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="75bc1-117">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-117">Output:</span></span>  
  
|<span data-ttu-id="75bc1-118">[値]</span><span class="sxs-lookup"><span data-stu-id="75bc1-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="75bc1-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="75bc1-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="75bc1-120">整数型</span><span class="sxs-lookup"><span data-stu-id="75bc1-120">Integer</span></span>  

 <span data-ttu-id="75bc1-121">整数リテラルには Int32 (123) 型、UInt32 (123U) 型、Int64 (123L) 型、および UInt64 (123UL) 型があります。</span><span class="sxs-lookup"><span data-stu-id="75bc1-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="75bc1-122">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-122">Example:</span></span>  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="75bc1-123">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-123">Output:</span></span>  
  
|<span data-ttu-id="75bc1-124">[値]</span><span class="sxs-lookup"><span data-stu-id="75bc1-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="75bc1-125">1</span><span class="sxs-lookup"><span data-stu-id="75bc1-125">1</span></span>|  
|<span data-ttu-id="75bc1-126">2</span><span class="sxs-lookup"><span data-stu-id="75bc1-126">2</span></span>|  
|<span data-ttu-id="75bc1-127">3</span><span class="sxs-lookup"><span data-stu-id="75bc1-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="75bc1-128">その他</span><span class="sxs-lookup"><span data-stu-id="75bc1-128">Other</span></span>  

 <span data-ttu-id="75bc1-129">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] でサポートされているその他のリテラルは、Guid、Binary、Float/Double、Decimal、および `null` です。</span><span class="sxs-lookup"><span data-stu-id="75bc1-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="75bc1-130">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] の NULL リテラルは、概念モデルのその他すべての型と互換性があると見なされます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="75bc1-131">型コンストラクター</span><span class="sxs-lookup"><span data-stu-id="75bc1-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="75bc1-132">ROW</span><span class="sxs-lookup"><span data-stu-id="75bc1-132">ROW</span></span>  

 <span data-ttu-id="75bc1-133">[ROW](row-entity-sql.md) では、`ROW(1 AS myNumber, ‘Name’ AS myName).` のように、構造的に型付けされた匿名のレコード値が作成されます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-133">[ROW](row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="75bc1-134">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-134">Example:</span></span>  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 <span data-ttu-id="75bc1-135">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-135">Output:</span></span>  
  
|<span data-ttu-id="75bc1-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="75bc1-136">ProductID</span></span>|<span data-ttu-id="75bc1-137">名前</span><span class="sxs-lookup"><span data-stu-id="75bc1-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="75bc1-138">1</span><span class="sxs-lookup"><span data-stu-id="75bc1-138">1</span></span>|<span data-ttu-id="75bc1-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="75bc1-139">Adjustable Race</span></span>|  
|<span data-ttu-id="75bc1-140">879</span><span class="sxs-lookup"><span data-stu-id="75bc1-140">879</span></span>|<span data-ttu-id="75bc1-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="75bc1-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="75bc1-142">712</span><span class="sxs-lookup"><span data-stu-id="75bc1-142">712</span></span>|<span data-ttu-id="75bc1-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="75bc1-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="75bc1-144">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-144">...</span></span>|<span data-ttu-id="75bc1-145">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="75bc1-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="75bc1-146">MULTISET</span></span>  

 <span data-ttu-id="75bc1-147">[MULTISET](multiset-entity-sql.md) では、次のようなコレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-147">[MULTISET](multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="75bc1-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="75bc1-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="75bc1-149">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-149">Example:</span></span>  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="75bc1-150">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-150">Output:</span></span>  
  
|<span data-ttu-id="75bc1-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="75bc1-151">ProductID</span></span>|<span data-ttu-id="75bc1-152">名前</span><span class="sxs-lookup"><span data-stu-id="75bc1-152">Name</span></span>|<span data-ttu-id="75bc1-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="75bc1-153">ProductNumber</span></span>|<span data-ttu-id="75bc1-154">…</span><span class="sxs-lookup"><span data-stu-id="75bc1-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="75bc1-155">842</span><span class="sxs-lookup"><span data-stu-id="75bc1-155">842</span></span>|<span data-ttu-id="75bc1-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="75bc1-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="75bc1-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="75bc1-157">PA-T100</span></span>|<span data-ttu-id="75bc1-158">…</span><span class="sxs-lookup"><span data-stu-id="75bc1-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="75bc1-159">Object</span><span class="sxs-lookup"><span data-stu-id="75bc1-159">Object</span></span>  

 <span data-ttu-id="75bc1-160">[名前付きの型コンストラクター](named-type-constructor-entity-sql.md)では、`person("abc", 12)` のように、名前付きのユーザー定義オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-160">[Named Type Constructor](named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="75bc1-161">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-161">Example:</span></span>  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail
AS o  
```  
  
 <span data-ttu-id="75bc1-162">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-162">Output:</span></span>  
  
|<span data-ttu-id="75bc1-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="75bc1-163">SalesOrderDetailID</span></span>|<span data-ttu-id="75bc1-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="75bc1-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="75bc1-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="75bc1-165">OrderQty</span></span>|<span data-ttu-id="75bc1-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="75bc1-166">ProductID</span></span>|<span data-ttu-id="75bc1-167">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="75bc1-168">1</span><span class="sxs-lookup"><span data-stu-id="75bc1-168">1</span></span>|<span data-ttu-id="75bc1-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="75bc1-169">4911-403C-98</span></span>|<span data-ttu-id="75bc1-170">1</span><span class="sxs-lookup"><span data-stu-id="75bc1-170">1</span></span>|<span data-ttu-id="75bc1-171">776</span><span class="sxs-lookup"><span data-stu-id="75bc1-171">776</span></span>|<span data-ttu-id="75bc1-172">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-172">...</span></span>|  
|<span data-ttu-id="75bc1-173">2</span><span class="sxs-lookup"><span data-stu-id="75bc1-173">2</span></span>|<span data-ttu-id="75bc1-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="75bc1-174">4911-403C-98</span></span>|<span data-ttu-id="75bc1-175">3</span><span class="sxs-lookup"><span data-stu-id="75bc1-175">3</span></span>|<span data-ttu-id="75bc1-176">777</span><span class="sxs-lookup"><span data-stu-id="75bc1-176">777</span></span>|<span data-ttu-id="75bc1-177">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-177">...</span></span>|  
|<span data-ttu-id="75bc1-178">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-178">...</span></span>|<span data-ttu-id="75bc1-179">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-179">...</span></span>|<span data-ttu-id="75bc1-180">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-180">...</span></span>|<span data-ttu-id="75bc1-181">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-181">...</span></span>|<span data-ttu-id="75bc1-182">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="75bc1-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="75bc1-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="75bc1-184">REF</span><span class="sxs-lookup"><span data-stu-id="75bc1-184">REF</span></span>  

 <span data-ttu-id="75bc1-185">[REF](ref-entity-sql.md) では、エンティティ型のインスタンスへの参照が作成されます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-185">[REF](ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="75bc1-186">たとえば、次のクエリは、Orders エンティティ セットの各 Order エンティティへの参照を返します。</span><span class="sxs-lookup"><span data-stu-id="75bc1-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="75bc1-187">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-187">Output:</span></span>  
  
|<span data-ttu-id="75bc1-188">[値]</span><span class="sxs-lookup"><span data-stu-id="75bc1-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="75bc1-189">1</span><span class="sxs-lookup"><span data-stu-id="75bc1-189">1</span></span>|  
|<span data-ttu-id="75bc1-190">2</span><span class="sxs-lookup"><span data-stu-id="75bc1-190">2</span></span>|  
|<span data-ttu-id="75bc1-191">3</span><span class="sxs-lookup"><span data-stu-id="75bc1-191">3</span></span>|  
|<span data-ttu-id="75bc1-192">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-192">...</span></span>|  
  
 <span data-ttu-id="75bc1-193">次の例では、プロパティ抽出演算子 (.) を使用して、エンティティのプロパティにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="75bc1-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="75bc1-194">プロパティ抽出演算子を使用すると、参照は自動的に逆参照されます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="75bc1-195">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-195">Example:</span></span>  
  
```sql  
SELECT VALUE REF(p).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="75bc1-196">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-196">Output:</span></span>  
  
|<span data-ttu-id="75bc1-197">[値]</span><span class="sxs-lookup"><span data-stu-id="75bc1-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="75bc1-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="75bc1-198">Adjustable Race</span></span>|  
|<span data-ttu-id="75bc1-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="75bc1-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="75bc1-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="75bc1-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="75bc1-201">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="75bc1-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="75bc1-202">DEREF</span></span>  

 <span data-ttu-id="75bc1-203">[DEREF](deref-entity-sql.md) では、参照値が逆参照されて、その逆参照の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-203">[DEREF](deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="75bc1-204">たとえば、次のクエリは、`SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2` のように、Orders エンティティ セットの各 Order について Order エンティティを生成します。</span><span class="sxs-lookup"><span data-stu-id="75bc1-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="75bc1-205">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-205">Example:</span></span>  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="75bc1-206">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-206">Output:</span></span>  
  
|<span data-ttu-id="75bc1-207">[値]</span><span class="sxs-lookup"><span data-stu-id="75bc1-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="75bc1-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="75bc1-208">Adjustable Race</span></span>|  
|<span data-ttu-id="75bc1-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="75bc1-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="75bc1-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="75bc1-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="75bc1-211">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="75bc1-212">CREATEREF と KEY</span><span class="sxs-lookup"><span data-stu-id="75bc1-212">CREATEREF AND KEY</span></span>  

 <span data-ttu-id="75bc1-213">[CREATEREF](createref-entity-sql.md) では、キーを渡す参照が作成されます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-213">[CREATEREF](createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="75bc1-214">[KEY](key-entity-sql.md) では、型参照を持つ式のキー部分が抽出されます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-214">[KEY](key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="75bc1-215">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-215">Example:</span></span>  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))
    FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="75bc1-216">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-216">Output:</span></span>  
  
|<span data-ttu-id="75bc1-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="75bc1-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="75bc1-218">980</span><span class="sxs-lookup"><span data-stu-id="75bc1-218">980</span></span>|  
|<span data-ttu-id="75bc1-219">365</span><span class="sxs-lookup"><span data-stu-id="75bc1-219">365</span></span>|  
|<span data-ttu-id="75bc1-220">771</span><span class="sxs-lookup"><span data-stu-id="75bc1-220">771</span></span>|  
|<span data-ttu-id="75bc1-221">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="75bc1-222">関数</span><span class="sxs-lookup"><span data-stu-id="75bc1-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="75bc1-223">正規</span><span class="sxs-lookup"><span data-stu-id="75bc1-223">Canonical</span></span>  

 <span data-ttu-id="75bc1-224">[正規関数](canonical-functions.md)の名前空間は Edm で、`Edm.Length("string")` のように使用されます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-224">The namespace for [canonical functions](canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="75bc1-225">正規関数と同じ名前の関数を含んでいる別の名前空間がインポートされない限り、名前空間を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="75bc1-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="75bc1-226">2 つの名前空間に同じ関数が存在する場合は、完全な名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75bc1-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="75bc1-227">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-227">Example:</span></span>  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="75bc1-228">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-228">Output:</span></span>  
  
|<span data-ttu-id="75bc1-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="75bc1-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="75bc1-230">6</span><span class="sxs-lookup"><span data-stu-id="75bc1-230">6</span></span>|  
|<span data-ttu-id="75bc1-231">6</span><span class="sxs-lookup"><span data-stu-id="75bc1-231">6</span></span>|  
|<span data-ttu-id="75bc1-232">5</span><span class="sxs-lookup"><span data-stu-id="75bc1-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="75bc1-233">Microsoft プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="75bc1-233">Microsoft Provider-Specific</span></span>  

 <span data-ttu-id="75bc1-234">[Microsoft プロバイダー固有の関数](../sqlclient-for-ef-functions.md)は、`SqlServer` 名前空間にあります。</span><span class="sxs-lookup"><span data-stu-id="75bc1-234">[Microsoft provider-specific functions](../sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="75bc1-235">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-235">Example:</span></span>  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="75bc1-236">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-236">Output:</span></span>  
  
|<span data-ttu-id="75bc1-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="75bc1-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="75bc1-238">27</span><span class="sxs-lookup"><span data-stu-id="75bc1-238">27</span></span>|  
|<span data-ttu-id="75bc1-239">27</span><span class="sxs-lookup"><span data-stu-id="75bc1-239">27</span></span>|  
|<span data-ttu-id="75bc1-240">26</span><span class="sxs-lookup"><span data-stu-id="75bc1-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="75bc1-241">名前空間</span><span class="sxs-lookup"><span data-stu-id="75bc1-241">Namespaces</span></span>  

 <span data-ttu-id="75bc1-242">[USING](using-entity-sql.md) では、クエリ式で使用する名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="75bc1-242">[USING](using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="75bc1-243">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-243">Example:</span></span>  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="75bc1-244">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-244">Output:</span></span>  
  
|<span data-ttu-id="75bc1-245">[値]</span><span class="sxs-lookup"><span data-stu-id="75bc1-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="75bc1-246">aa</span><span class="sxs-lookup"><span data-stu-id="75bc1-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="75bc1-247">ページング</span><span class="sxs-lookup"><span data-stu-id="75bc1-247">Paging</span></span>  

 <span data-ttu-id="75bc1-248">ページングは、[ORDER BY](order-by-entity-sql.md) 句に対して [SKIP](skip-entity-sql.md) および [LIMIT](limit-entity-sql.md) サブ句を宣言することによって表すことができます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-248">Paging can be expressed by declaring a [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses to the [ORDER BY](order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="75bc1-249">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-249">Example:</span></span>  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="75bc1-250">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-250">Output:</span></span>  
  
|<span data-ttu-id="75bc1-251">ID</span><span class="sxs-lookup"><span data-stu-id="75bc1-251">ID</span></span>|<span data-ttu-id="75bc1-252">名前</span><span class="sxs-lookup"><span data-stu-id="75bc1-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="75bc1-253">10</span><span class="sxs-lookup"><span data-stu-id="75bc1-253">10</span></span>|<span data-ttu-id="75bc1-254">Adina</span><span class="sxs-lookup"><span data-stu-id="75bc1-254">Adina</span></span>|  
|<span data-ttu-id="75bc1-255">11</span><span class="sxs-lookup"><span data-stu-id="75bc1-255">11</span></span>|<span data-ttu-id="75bc1-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="75bc1-256">Agcaoili</span></span>|  
|<span data-ttu-id="75bc1-257">12</span><span class="sxs-lookup"><span data-stu-id="75bc1-257">12</span></span>|<span data-ttu-id="75bc1-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="75bc1-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="75bc1-259">グループ化</span><span class="sxs-lookup"><span data-stu-id="75bc1-259">Grouping</span></span>  

 <span data-ttu-id="75bc1-260">[GROUPING BY](group-by-entity-sql.md) では、クエリ ([SELECT](select-entity-sql.md)) 式によって返されるオブジェクトをグループ化するよう指定します。</span><span class="sxs-lookup"><span data-stu-id="75bc1-260">[GROUPING BY](group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="75bc1-261">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-261">Example:</span></span>  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="75bc1-262">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-262">Output:</span></span>  
  
|<span data-ttu-id="75bc1-263">name</span><span class="sxs-lookup"><span data-stu-id="75bc1-263">name</span></span>|  
|----------|  
|<span data-ttu-id="75bc1-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="75bc1-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="75bc1-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="75bc1-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="75bc1-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="75bc1-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="75bc1-267">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="75bc1-268">ナビゲーション</span><span class="sxs-lookup"><span data-stu-id="75bc1-268">Navigation</span></span>  

 <span data-ttu-id="75bc1-269">リレーションシップ ナビゲーション操作を使用すると、開始側のエンティティと終了側のエンティティ間のリレーションシップをナビゲートできます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="75bc1-270">[NAVIGATE](navigate-entity-sql.md) は、\<namespace>.\<relationship type name> のように修飾されたリレーションシップ型を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="75bc1-270">[NAVIGATE](navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="75bc1-271">終了側のカーディナリティが 1 の場合、NAVIGATE から Ref\<T> が返されます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="75bc1-272">終了側のカーディナリティが n の場合、Collection<Ref\<T>> が返されます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="75bc1-273">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-273">Example:</span></span>  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="75bc1-274">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-274">Output:</span></span>  
  
|<span data-ttu-id="75bc1-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="75bc1-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="75bc1-276">1</span><span class="sxs-lookup"><span data-stu-id="75bc1-276">1</span></span>|  
|<span data-ttu-id="75bc1-277">2</span><span class="sxs-lookup"><span data-stu-id="75bc1-277">2</span></span>|  
|<span data-ttu-id="75bc1-278">3</span><span class="sxs-lookup"><span data-stu-id="75bc1-278">3</span></span>|  
|<span data-ttu-id="75bc1-279">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="75bc1-280">SELECT VALUE AND SELECT</span><span class="sxs-lookup"><span data-stu-id="75bc1-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="75bc1-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="75bc1-281">SELECT VALUE</span></span>  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="75bc1-282">には、暗黙の行の構築をスキップする SELECT VALUE 句が用意されています。</span><span class="sxs-lookup"><span data-stu-id="75bc1-282">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="75bc1-283">SELECT VALUE 句には 1 つの項目のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="75bc1-284">このような句を使用した場合、SELECT 句内の項目には row ラッパーは構築されず、`SELECT VALUE a` などの目的の構造を持つコレクションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="75bc1-285">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-285">Example:</span></span>  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="75bc1-286">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-286">Output:</span></span>  
  
|<span data-ttu-id="75bc1-287">名前</span><span class="sxs-lookup"><span data-stu-id="75bc1-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="75bc1-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="75bc1-288">Adjustable Race</span></span>|  
|<span data-ttu-id="75bc1-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="75bc1-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="75bc1-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="75bc1-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="75bc1-291">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="75bc1-292">SELECT</span><span class="sxs-lookup"><span data-stu-id="75bc1-292">SELECT</span></span>  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="75bc1-293">には、任意の行を構築するための行コンストラクターも用意されています。</span><span class="sxs-lookup"><span data-stu-id="75bc1-293">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="75bc1-294">SELECT は、投影内の 1 つまたは複数の要素、および `SELECT a, b, c` などのフィールドを持つデータ レコードの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="75bc1-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="75bc1-295">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-295">Example:</span></span>  
  
 <span data-ttu-id="75bc1-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="75bc1-297">名前</span><span class="sxs-lookup"><span data-stu-id="75bc1-297">Name</span></span>|<span data-ttu-id="75bc1-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="75bc1-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="75bc1-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="75bc1-299">Adjustable Race</span></span>|<span data-ttu-id="75bc1-300">1</span><span class="sxs-lookup"><span data-stu-id="75bc1-300">1</span></span>|  
|<span data-ttu-id="75bc1-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="75bc1-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="75bc1-302">879</span><span class="sxs-lookup"><span data-stu-id="75bc1-302">879</span></span>|  
|<span data-ttu-id="75bc1-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="75bc1-303">AWC Logo Cap</span></span>|<span data-ttu-id="75bc1-304">712</span><span class="sxs-lookup"><span data-stu-id="75bc1-304">712</span></span>|  
|<span data-ttu-id="75bc1-305">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-305">...</span></span>|<span data-ttu-id="75bc1-306">...</span><span class="sxs-lookup"><span data-stu-id="75bc1-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="75bc1-307">CASE 式</span><span class="sxs-lookup"><span data-stu-id="75bc1-307">CASE EXPRESSION</span></span>  

 <span data-ttu-id="75bc1-308">[CASE 式](case-entity-sql.md)では、一連のブール式が評価されて結果が判定されます。</span><span class="sxs-lookup"><span data-stu-id="75bc1-308">The [case expression](case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="75bc1-309">例:</span><span class="sxs-lookup"><span data-stu-id="75bc1-309">Example:</span></span>  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="75bc1-310">Output:</span><span class="sxs-lookup"><span data-stu-id="75bc1-310">Output:</span></span>  
  
|<span data-ttu-id="75bc1-311">[値]</span><span class="sxs-lookup"><span data-stu-id="75bc1-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="75bc1-312">true</span><span class="sxs-lookup"><span data-stu-id="75bc1-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75bc1-313">関連項目</span><span class="sxs-lookup"><span data-stu-id="75bc1-313">See also</span></span>

- [<span data-ttu-id="75bc1-314">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="75bc1-314">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="75bc1-315">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="75bc1-315">Entity SQL Overview</span></span>](entity-sql-overview.md)
