---
title: Entity SQL クイック リファレンス
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: 9ccfc461d394af8804c960ebf460e7fbfb025b64
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833874"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="52236-102">Entity SQL クイック リファレンス</span><span class="sxs-lookup"><span data-stu-id="52236-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="52236-103">このトピックでは、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] クエリのクイック リファレンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="52236-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="52236-104">このトピックのクエリは、AdventureWorks Sales model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="52236-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="52236-105">リテラル</span><span class="sxs-lookup"><span data-stu-id="52236-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="52236-106">String</span><span class="sxs-lookup"><span data-stu-id="52236-106">String</span></span>  
 <span data-ttu-id="52236-107">Unicode と非 Unicode の文字列リテラルがあります。</span><span class="sxs-lookup"><span data-stu-id="52236-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="52236-108">Unicode 文字列の先頭には N が付きます。たとえば、`N'hello'` です。</span><span class="sxs-lookup"><span data-stu-id="52236-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="52236-109">非 Unicode 文字列リテラルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="52236-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="52236-110">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-110">Output:</span></span>  
  
|<span data-ttu-id="52236-111">値</span><span class="sxs-lookup"><span data-stu-id="52236-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="52236-112">hello</span><span class="sxs-lookup"><span data-stu-id="52236-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="52236-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="52236-113">DateTime</span></span>  
 <span data-ttu-id="52236-114">DateTime リテラルでは、日付部分と時刻部分の両方が必須です。</span><span class="sxs-lookup"><span data-stu-id="52236-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="52236-115">既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="52236-115">There are no default values.</span></span>  
  
 <span data-ttu-id="52236-116">例:</span><span class="sxs-lookup"><span data-stu-id="52236-116">Example:</span></span>  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="52236-117">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-117">Output:</span></span>  
  
|<span data-ttu-id="52236-118">値</span><span class="sxs-lookup"><span data-stu-id="52236-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="52236-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="52236-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="52236-120">整数型</span><span class="sxs-lookup"><span data-stu-id="52236-120">Integer</span></span>  
 <span data-ttu-id="52236-121">整数リテラルには Int32 (123) 型、UInt32 (123U) 型、Int64 (123L) 型、および UInt64 (123UL) 型があります。</span><span class="sxs-lookup"><span data-stu-id="52236-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="52236-122">例:</span><span class="sxs-lookup"><span data-stu-id="52236-122">Example:</span></span>  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="52236-123">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-123">Output:</span></span>  
  
|<span data-ttu-id="52236-124">値</span><span class="sxs-lookup"><span data-stu-id="52236-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="52236-125">1</span><span class="sxs-lookup"><span data-stu-id="52236-125">1</span></span>|  
|<span data-ttu-id="52236-126">2</span><span class="sxs-lookup"><span data-stu-id="52236-126">2</span></span>|  
|<span data-ttu-id="52236-127">3</span><span class="sxs-lookup"><span data-stu-id="52236-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="52236-128">その他</span><span class="sxs-lookup"><span data-stu-id="52236-128">Other</span></span>  
 <span data-ttu-id="52236-129">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] でサポートされているその他のリテラルは、Guid、Binary、Float/Double、Decimal、および `null` です。</span><span class="sxs-lookup"><span data-stu-id="52236-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="52236-130">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] の NULL リテラルは、概念モデルのその他すべての型と互換性があると見なされます。</span><span class="sxs-lookup"><span data-stu-id="52236-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="52236-131">型コンストラクター</span><span class="sxs-lookup"><span data-stu-id="52236-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="52236-132">ROW</span><span class="sxs-lookup"><span data-stu-id="52236-132">ROW</span></span>  
 <span data-ttu-id="52236-133">[行](row-entity-sql.md)は、次のように構造的に型指定された匿名の (レコード) 値を構築します。 `ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="52236-133">[ROW](row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="52236-134">例:</span><span class="sxs-lookup"><span data-stu-id="52236-134">Example:</span></span>  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 <span data-ttu-id="52236-135">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-135">Output:</span></span>  
  
|<span data-ttu-id="52236-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="52236-136">ProductID</span></span>|<span data-ttu-id="52236-137">名前</span><span class="sxs-lookup"><span data-stu-id="52236-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="52236-138">1</span><span class="sxs-lookup"><span data-stu-id="52236-138">1</span></span>|<span data-ttu-id="52236-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="52236-139">Adjustable Race</span></span>|  
|<span data-ttu-id="52236-140">879</span><span class="sxs-lookup"><span data-stu-id="52236-140">879</span></span>|<span data-ttu-id="52236-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="52236-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="52236-142">712</span><span class="sxs-lookup"><span data-stu-id="52236-142">712</span></span>|<span data-ttu-id="52236-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="52236-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="52236-144">[...]</span><span class="sxs-lookup"><span data-stu-id="52236-144">...</span></span>|<span data-ttu-id="52236-145">[...]</span><span class="sxs-lookup"><span data-stu-id="52236-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="52236-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="52236-146">MULTISET</span></span>  
 <span data-ttu-id="52236-147">[マルチセット](multiset-entity-sql.md)は、次のようなコレクションを構築します。</span><span class="sxs-lookup"><span data-stu-id="52236-147">[MULTISET](multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="52236-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="52236-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="52236-149">例:</span><span class="sxs-lookup"><span data-stu-id="52236-149">Example:</span></span>  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="52236-150">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-150">Output:</span></span>  
  
|<span data-ttu-id="52236-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="52236-151">ProductID</span></span>|<span data-ttu-id="52236-152">名前</span><span class="sxs-lookup"><span data-stu-id="52236-152">Name</span></span>|<span data-ttu-id="52236-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="52236-153">ProductNumber</span></span>|<span data-ttu-id="52236-154">…</span><span class="sxs-lookup"><span data-stu-id="52236-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="52236-155">842</span><span class="sxs-lookup"><span data-stu-id="52236-155">842</span></span>|<span data-ttu-id="52236-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="52236-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="52236-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="52236-157">PA-T100</span></span>|<span data-ttu-id="52236-158">…</span><span class="sxs-lookup"><span data-stu-id="52236-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="52236-159">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="52236-159">Object</span></span>  
 <span data-ttu-id="52236-160">[名前付きの型コンストラクター](named-type-constructor-entity-sql.md) (名前付き) ユーザー定義オブジェクト (`person("abc", 12)` など) を構築します。</span><span class="sxs-lookup"><span data-stu-id="52236-160">[Named Type Constructor](named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="52236-161">例:</span><span class="sxs-lookup"><span data-stu-id="52236-161">Example:</span></span>  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="52236-162">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-162">Output:</span></span>  
  
|<span data-ttu-id="52236-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="52236-163">SalesOrderDetailID</span></span>|<span data-ttu-id="52236-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="52236-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="52236-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="52236-165">OrderQty</span></span>|<span data-ttu-id="52236-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="52236-166">ProductID</span></span>|<span data-ttu-id="52236-167">[...]</span><span class="sxs-lookup"><span data-stu-id="52236-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="52236-168">1</span><span class="sxs-lookup"><span data-stu-id="52236-168">1</span></span>|<span data-ttu-id="52236-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="52236-169">4911-403C-98</span></span>|<span data-ttu-id="52236-170">1</span><span class="sxs-lookup"><span data-stu-id="52236-170">1</span></span>|<span data-ttu-id="52236-171">776</span><span class="sxs-lookup"><span data-stu-id="52236-171">776</span></span>|<span data-ttu-id="52236-172">[...]</span><span class="sxs-lookup"><span data-stu-id="52236-172">...</span></span>|  
|<span data-ttu-id="52236-173">2</span><span class="sxs-lookup"><span data-stu-id="52236-173">2</span></span>|<span data-ttu-id="52236-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="52236-174">4911-403C-98</span></span>|<span data-ttu-id="52236-175">3</span><span class="sxs-lookup"><span data-stu-id="52236-175">3</span></span>|<span data-ttu-id="52236-176">777</span><span class="sxs-lookup"><span data-stu-id="52236-176">777</span></span>|<span data-ttu-id="52236-177">[...]</span><span class="sxs-lookup"><span data-stu-id="52236-177">...</span></span>|  
|<span data-ttu-id="52236-178">...</span><span class="sxs-lookup"><span data-stu-id="52236-178">...</span></span>|<span data-ttu-id="52236-179">...</span><span class="sxs-lookup"><span data-stu-id="52236-179">...</span></span>|<span data-ttu-id="52236-180">...</span><span class="sxs-lookup"><span data-stu-id="52236-180">...</span></span>|<span data-ttu-id="52236-181">...</span><span class="sxs-lookup"><span data-stu-id="52236-181">...</span></span>|<span data-ttu-id="52236-182">[...]</span><span class="sxs-lookup"><span data-stu-id="52236-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="52236-183">リファレンス</span><span class="sxs-lookup"><span data-stu-id="52236-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="52236-184">REF</span><span class="sxs-lookup"><span data-stu-id="52236-184">REF</span></span>  
 <span data-ttu-id="52236-185">[REF](ref-entity-sql.md)は、エンティティ型のインスタンスへの参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="52236-185">[REF](ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="52236-186">たとえば、次のクエリは、Orders エンティティ セットの各 Order エンティティへの参照を返します。</span><span class="sxs-lookup"><span data-stu-id="52236-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="52236-187">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-187">Output:</span></span>  
  
|<span data-ttu-id="52236-188">値</span><span class="sxs-lookup"><span data-stu-id="52236-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="52236-189">1</span><span class="sxs-lookup"><span data-stu-id="52236-189">1</span></span>|  
|<span data-ttu-id="52236-190">2</span><span class="sxs-lookup"><span data-stu-id="52236-190">2</span></span>|  
|<span data-ttu-id="52236-191">3</span><span class="sxs-lookup"><span data-stu-id="52236-191">3</span></span>|  
|<span data-ttu-id="52236-192">[...]</span><span class="sxs-lookup"><span data-stu-id="52236-192">...</span></span>|  
  
 <span data-ttu-id="52236-193">次の例では、プロパティ抽出演算子 (.) を使用して、エンティティのプロパティにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="52236-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="52236-194">プロパティ抽出演算子を使用すると、参照は自動的に逆参照されます。</span><span class="sxs-lookup"><span data-stu-id="52236-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="52236-195">例:</span><span class="sxs-lookup"><span data-stu-id="52236-195">Example:</span></span>  
  
```sql  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="52236-196">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-196">Output:</span></span>  
  
|<span data-ttu-id="52236-197">値</span><span class="sxs-lookup"><span data-stu-id="52236-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="52236-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="52236-198">Adjustable Race</span></span>|  
|<span data-ttu-id="52236-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="52236-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="52236-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="52236-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="52236-201">[...]</span><span class="sxs-lookup"><span data-stu-id="52236-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="52236-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="52236-202">DEREF</span></span>  
 <span data-ttu-id="52236-203">[DEREF](deref-entity-sql.md)は参照値を逆参照し、その逆参照の結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="52236-203">[DEREF](deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="52236-204">たとえば、次のクエリは、`SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2` のように、Orders エンティティ セットの各 Order について Order エンティティを生成します。</span><span class="sxs-lookup"><span data-stu-id="52236-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="52236-205">例:</span><span class="sxs-lookup"><span data-stu-id="52236-205">Example:</span></span>  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="52236-206">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-206">Output:</span></span>  
  
|<span data-ttu-id="52236-207">値</span><span class="sxs-lookup"><span data-stu-id="52236-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="52236-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="52236-208">Adjustable Race</span></span>|  
|<span data-ttu-id="52236-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="52236-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="52236-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="52236-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="52236-211">[...]</span><span class="sxs-lookup"><span data-stu-id="52236-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="52236-212">CREATEREF と KEY</span><span class="sxs-lookup"><span data-stu-id="52236-212">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="52236-213">[CREATEREF](createref-entity-sql.md)は、キーを渡す参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="52236-213">[CREATEREF](createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="52236-214">[Key](key-entity-sql.md)は、型参照を持つ式のキー部分を抽出します。</span><span class="sxs-lookup"><span data-stu-id="52236-214">[KEY](key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="52236-215">例:</span><span class="sxs-lookup"><span data-stu-id="52236-215">Example:</span></span>  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="52236-216">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-216">Output:</span></span>  
  
|<span data-ttu-id="52236-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="52236-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="52236-218">980</span><span class="sxs-lookup"><span data-stu-id="52236-218">980</span></span>|  
|<span data-ttu-id="52236-219">365</span><span class="sxs-lookup"><span data-stu-id="52236-219">365</span></span>|  
|<span data-ttu-id="52236-220">771</span><span class="sxs-lookup"><span data-stu-id="52236-220">771</span></span>|  
|<span data-ttu-id="52236-221">[...]</span><span class="sxs-lookup"><span data-stu-id="52236-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="52236-222">関数</span><span class="sxs-lookup"><span data-stu-id="52236-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="52236-223">正規</span><span class="sxs-lookup"><span data-stu-id="52236-223">Canonical</span></span>  
 <span data-ttu-id="52236-224">[正規関数](canonical-functions.md)の名前空間は、`Edm.Length("string")` のように Edm です。</span><span class="sxs-lookup"><span data-stu-id="52236-224">The namespace for [canonical functions](canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="52236-225">正規関数と同じ名前の関数を含んでいる別の名前空間がインポートされない限り、名前空間を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="52236-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="52236-226">2 つの名前空間に同じ関数が存在する場合は、完全な名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52236-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="52236-227">例:</span><span class="sxs-lookup"><span data-stu-id="52236-227">Example:</span></span>  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="52236-228">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-228">Output:</span></span>  
  
|<span data-ttu-id="52236-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="52236-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="52236-230">6</span><span class="sxs-lookup"><span data-stu-id="52236-230">6</span></span>|  
|<span data-ttu-id="52236-231">6</span><span class="sxs-lookup"><span data-stu-id="52236-231">6</span></span>|  
|<span data-ttu-id="52236-232">5</span><span class="sxs-lookup"><span data-stu-id="52236-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="52236-233">Microsoft プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="52236-233">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="52236-234">[Microsoft プロバイダー固有の関数](../sqlclient-for-ef-functions.md)は、@no__t 1 つの名前空間にあります。</span><span class="sxs-lookup"><span data-stu-id="52236-234">[Microsoft provider-specific functions](../sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="52236-235">例:</span><span class="sxs-lookup"><span data-stu-id="52236-235">Example:</span></span>  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="52236-236">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-236">Output:</span></span>  
  
|<span data-ttu-id="52236-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="52236-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="52236-238">27</span><span class="sxs-lookup"><span data-stu-id="52236-238">27</span></span>|  
|<span data-ttu-id="52236-239">27</span><span class="sxs-lookup"><span data-stu-id="52236-239">27</span></span>|  
|<span data-ttu-id="52236-240">26</span><span class="sxs-lookup"><span data-stu-id="52236-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="52236-241">名前空間</span><span class="sxs-lookup"><span data-stu-id="52236-241">Namespaces</span></span>  
 <span data-ttu-id="52236-242">[を使用して](using-entity-sql.md)、クエリ式で使用される名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="52236-242">[USING](using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="52236-243">例:</span><span class="sxs-lookup"><span data-stu-id="52236-243">Example:</span></span>  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="52236-244">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-244">Output:</span></span>  
  
|<span data-ttu-id="52236-245">値</span><span class="sxs-lookup"><span data-stu-id="52236-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="52236-246">aa</span><span class="sxs-lookup"><span data-stu-id="52236-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="52236-247">ページング</span><span class="sxs-lookup"><span data-stu-id="52236-247">Paging</span></span>  
 <span data-ttu-id="52236-248">ページングは、 [SKIP](skip-entity-sql.md)および[LIMIT](limit-entity-sql.md)サブ句を[ORDER by](order-by-entity-sql.md)句に宣言することによって表現できます。</span><span class="sxs-lookup"><span data-stu-id="52236-248">Paging can be expressed by declaring a [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses to the [ORDER BY](order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="52236-249">例:</span><span class="sxs-lookup"><span data-stu-id="52236-249">Example:</span></span>  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="52236-250">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-250">Output:</span></span>  
  
|<span data-ttu-id="52236-251">ID</span><span class="sxs-lookup"><span data-stu-id="52236-251">ID</span></span>|<span data-ttu-id="52236-252">名前</span><span class="sxs-lookup"><span data-stu-id="52236-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="52236-253">10</span><span class="sxs-lookup"><span data-stu-id="52236-253">10</span></span>|<span data-ttu-id="52236-254">Adina</span><span class="sxs-lookup"><span data-stu-id="52236-254">Adina</span></span>|  
|<span data-ttu-id="52236-255">11</span><span class="sxs-lookup"><span data-stu-id="52236-255">11</span></span>|<span data-ttu-id="52236-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="52236-256">Agcaoili</span></span>|  
|<span data-ttu-id="52236-257">12</span><span class="sxs-lookup"><span data-stu-id="52236-257">12</span></span>|<span data-ttu-id="52236-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="52236-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="52236-259">グループ化</span><span class="sxs-lookup"><span data-stu-id="52236-259">Grouping</span></span>  
 <span data-ttu-id="52236-260">[[GROUPING BY](group-by-entity-sql.md)は、クエリ ([SELECT](select-entity-sql.md)) 式によって返されるオブジェクトのグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="52236-260">[GROUPING BY](group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="52236-261">例:</span><span class="sxs-lookup"><span data-stu-id="52236-261">Example:</span></span>  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="52236-262">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-262">Output:</span></span>  
  
|<span data-ttu-id="52236-263">NAME</span><span class="sxs-lookup"><span data-stu-id="52236-263">name</span></span>|  
|----------|  
|<span data-ttu-id="52236-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="52236-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="52236-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="52236-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="52236-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="52236-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="52236-267">[...]</span><span class="sxs-lookup"><span data-stu-id="52236-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="52236-268">ナビゲーション</span><span class="sxs-lookup"><span data-stu-id="52236-268">Navigation</span></span>  
 <span data-ttu-id="52236-269">リレーションシップ ナビゲーション操作を使用すると、開始側のエンティティと終了側のエンティティ間のリレーションシップをナビゲートできます。</span><span class="sxs-lookup"><span data-stu-id="52236-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="52236-270">[NAVIGATE](navigate-entity-sql.md)は、\<namespace > として修飾されたリレーションシップの種類を取得します。 \<relationship 型名 >。</span><span class="sxs-lookup"><span data-stu-id="52236-270">[NAVIGATE](navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="52236-271">To end のカーディナリティが1の場合、Navigate は Ref @ no__t-0T > を返します。</span><span class="sxs-lookup"><span data-stu-id="52236-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="52236-272">終点のカーディナリティが n の場合、コレクション < Ref @ no__t-0T > > が返されます。</span><span class="sxs-lookup"><span data-stu-id="52236-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="52236-273">例:</span><span class="sxs-lookup"><span data-stu-id="52236-273">Example:</span></span>  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="52236-274">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-274">Output:</span></span>  
  
|<span data-ttu-id="52236-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="52236-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="52236-276">1</span><span class="sxs-lookup"><span data-stu-id="52236-276">1</span></span>|  
|<span data-ttu-id="52236-277">2</span><span class="sxs-lookup"><span data-stu-id="52236-277">2</span></span>|  
|<span data-ttu-id="52236-278">3</span><span class="sxs-lookup"><span data-stu-id="52236-278">3</span></span>|  
|<span data-ttu-id="52236-279">[...]</span><span class="sxs-lookup"><span data-stu-id="52236-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="52236-280">SELECT VALUE AND SELECT</span><span class="sxs-lookup"><span data-stu-id="52236-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="52236-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="52236-281">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="52236-282">には、暗黙の行の構築をスキップする SELECT VALUE 句が用意されています。</span><span class="sxs-lookup"><span data-stu-id="52236-282">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="52236-283">SELECT VALUE 句には 1 つの項目のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="52236-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="52236-284">このような句を使用すると、SELECT 句の項目の周囲に行ラッパーは構築されず、たとえば `SELECT VALUE a` のように、目的の図形のコレクションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="52236-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="52236-285">例:</span><span class="sxs-lookup"><span data-stu-id="52236-285">Example:</span></span>  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="52236-286">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-286">Output:</span></span>  
  
|<span data-ttu-id="52236-287">名前</span><span class="sxs-lookup"><span data-stu-id="52236-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="52236-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="52236-288">Adjustable Race</span></span>|  
|<span data-ttu-id="52236-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="52236-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="52236-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="52236-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="52236-291">[...]</span><span class="sxs-lookup"><span data-stu-id="52236-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="52236-292">SELECT</span><span class="sxs-lookup"><span data-stu-id="52236-292">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="52236-293">には、任意の行を構築するための行コンストラクターも用意されています。</span><span class="sxs-lookup"><span data-stu-id="52236-293">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="52236-294">SELECT は、投影内の 1 つまたは複数の要素、および `SELECT a, b, c` などのフィールドを持つデータ レコードの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="52236-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="52236-295">例:</span><span class="sxs-lookup"><span data-stu-id="52236-295">Example:</span></span>  
  
 <span data-ttu-id="52236-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="52236-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="52236-297">名前</span><span class="sxs-lookup"><span data-stu-id="52236-297">Name</span></span>|<span data-ttu-id="52236-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="52236-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="52236-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="52236-299">Adjustable Race</span></span>|<span data-ttu-id="52236-300">1</span><span class="sxs-lookup"><span data-stu-id="52236-300">1</span></span>|  
|<span data-ttu-id="52236-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="52236-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="52236-302">879</span><span class="sxs-lookup"><span data-stu-id="52236-302">879</span></span>|  
|<span data-ttu-id="52236-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="52236-303">AWC Logo Cap</span></span>|<span data-ttu-id="52236-304">712</span><span class="sxs-lookup"><span data-stu-id="52236-304">712</span></span>|  
|<span data-ttu-id="52236-305">[...]</span><span class="sxs-lookup"><span data-stu-id="52236-305">...</span></span>|<span data-ttu-id="52236-306">[...]</span><span class="sxs-lookup"><span data-stu-id="52236-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="52236-307">CASE 式</span><span class="sxs-lookup"><span data-stu-id="52236-307">CASE EXPRESSION</span></span>  
 <span data-ttu-id="52236-308">[Case 式](case-entity-sql.md)は、一連のブール式を評価して結果を決定します。</span><span class="sxs-lookup"><span data-stu-id="52236-308">The [case expression](case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="52236-309">例:</span><span class="sxs-lookup"><span data-stu-id="52236-309">Example:</span></span>  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="52236-310">Output:</span><span class="sxs-lookup"><span data-stu-id="52236-310">Output:</span></span>  
  
|<span data-ttu-id="52236-311">値</span><span class="sxs-lookup"><span data-stu-id="52236-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="52236-312">true</span><span class="sxs-lookup"><span data-stu-id="52236-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52236-313">関連項目</span><span class="sxs-lookup"><span data-stu-id="52236-313">See also</span></span>

- [<span data-ttu-id="52236-314">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="52236-314">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="52236-315">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="52236-315">Entity SQL Overview</span></span>](entity-sql-overview.md)
