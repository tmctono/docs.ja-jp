---
title: Entity SQL クイック リファレンス
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: b4e3eaf8abd82b63fa2663b47f878ecfa9584897
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207072"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="0c975-102">Entity SQL クイック リファレンス</span><span class="sxs-lookup"><span data-stu-id="0c975-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="0c975-103">このトピックでは、[!INCLUDE[esql](../../../../../../includes/esql-md.md)] クエリのクイック リファレンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0c975-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="0c975-104">このトピック内のクエリは、AdventureWorks Sales model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="0c975-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="0c975-105">リテラル</span><span class="sxs-lookup"><span data-stu-id="0c975-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="0c975-106">String</span><span class="sxs-lookup"><span data-stu-id="0c975-106">String</span></span>  
 <span data-ttu-id="0c975-107">Unicode と非 Unicode の文字列リテラルがあります。</span><span class="sxs-lookup"><span data-stu-id="0c975-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="0c975-108">Unicode 文字列の先頭 n. にはたとえば、`N'hello'`します。</span><span class="sxs-lookup"><span data-stu-id="0c975-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="0c975-109">非 Unicode 文字列リテラルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0c975-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="0c975-110">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-110">Output:</span></span>  
  
|<span data-ttu-id="0c975-111">[値]</span><span class="sxs-lookup"><span data-stu-id="0c975-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="0c975-112">hello</span><span class="sxs-lookup"><span data-stu-id="0c975-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="0c975-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="0c975-113">DateTime</span></span>  
 <span data-ttu-id="0c975-114">DateTime リテラルでは、日付部分と時刻部分の両方が必須です。</span><span class="sxs-lookup"><span data-stu-id="0c975-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="0c975-115">既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="0c975-115">There are no default values.</span></span>  
  
 <span data-ttu-id="0c975-116">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-116">Example:</span></span>  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="0c975-117">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-117">Output:</span></span>  
  
|<span data-ttu-id="0c975-118">[値]</span><span class="sxs-lookup"><span data-stu-id="0c975-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="0c975-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="0c975-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="0c975-120">整数型</span><span class="sxs-lookup"><span data-stu-id="0c975-120">Integer</span></span>  
 <span data-ttu-id="0c975-121">整数リテラルには Int32 (123) 型、UInt32 (123U) 型、Int64 (123L) 型、および UInt64 (123UL) 型があります。</span><span class="sxs-lookup"><span data-stu-id="0c975-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="0c975-122">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-122">Example:</span></span>  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="0c975-123">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-123">Output:</span></span>  
  
|<span data-ttu-id="0c975-124">[値]</span><span class="sxs-lookup"><span data-stu-id="0c975-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="0c975-125">1</span><span class="sxs-lookup"><span data-stu-id="0c975-125">1</span></span>|  
|<span data-ttu-id="0c975-126">2</span><span class="sxs-lookup"><span data-stu-id="0c975-126">2</span></span>|  
|<span data-ttu-id="0c975-127">3</span><span class="sxs-lookup"><span data-stu-id="0c975-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="0c975-128">その他</span><span class="sxs-lookup"><span data-stu-id="0c975-128">Other</span></span>  
 <span data-ttu-id="0c975-129">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] でサポートされているその他のリテラルは、Guid、Binary、Float/Double、Decimal、および `null` です。</span><span class="sxs-lookup"><span data-stu-id="0c975-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="0c975-130">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] の NULL リテラルは、概念モデルのその他すべての型と互換性があると見なされます。</span><span class="sxs-lookup"><span data-stu-id="0c975-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="0c975-131">型コンストラクター</span><span class="sxs-lookup"><span data-stu-id="0c975-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="0c975-132">ROW</span><span class="sxs-lookup"><span data-stu-id="0c975-132">ROW</span></span>  
 <span data-ttu-id="0c975-133">[行](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md)としての匿名の構造的に型指定された (レコード) 値を作成します。</span><span class="sxs-lookup"><span data-stu-id="0c975-133">[ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in:</span></span> `ROW(1 AS myNumber, ‘Name’ AS myName).`  
  
 <span data-ttu-id="0c975-134">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-134">Example:</span></span>  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 <span data-ttu-id="0c975-135">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-135">Output:</span></span>  
  
|<span data-ttu-id="0c975-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="0c975-136">ProductID</span></span>|<span data-ttu-id="0c975-137">名前</span><span class="sxs-lookup"><span data-stu-id="0c975-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="0c975-138">1</span><span class="sxs-lookup"><span data-stu-id="0c975-138">1</span></span>|<span data-ttu-id="0c975-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="0c975-139">Adjustable Race</span></span>|  
|<span data-ttu-id="0c975-140">879</span><span class="sxs-lookup"><span data-stu-id="0c975-140">879</span></span>|<span data-ttu-id="0c975-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="0c975-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="0c975-142">712</span><span class="sxs-lookup"><span data-stu-id="0c975-142">712</span></span>|<span data-ttu-id="0c975-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="0c975-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="0c975-144">...</span><span class="sxs-lookup"><span data-stu-id="0c975-144">...</span></span>|<span data-ttu-id="0c975-145">...</span><span class="sxs-lookup"><span data-stu-id="0c975-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="0c975-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="0c975-146">MULTISET</span></span>  
 <span data-ttu-id="0c975-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md)など、コレクションを構築します。</span><span class="sxs-lookup"><span data-stu-id="0c975-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 `MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`  
  
 <span data-ttu-id="0c975-148">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-148">Example:</span></span>  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="0c975-149">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-149">Output:</span></span>  
  
|<span data-ttu-id="0c975-150">ProductID</span><span class="sxs-lookup"><span data-stu-id="0c975-150">ProductID</span></span>|<span data-ttu-id="0c975-151">名前</span><span class="sxs-lookup"><span data-stu-id="0c975-151">Name</span></span>|<span data-ttu-id="0c975-152">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="0c975-152">ProductNumber</span></span>|<span data-ttu-id="0c975-153">…</span><span class="sxs-lookup"><span data-stu-id="0c975-153">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="0c975-154">842</span><span class="sxs-lookup"><span data-stu-id="0c975-154">842</span></span>|<span data-ttu-id="0c975-155">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="0c975-155">Touring-Panniers, Large</span></span>|<span data-ttu-id="0c975-156">PA-T100</span><span class="sxs-lookup"><span data-stu-id="0c975-156">PA-T100</span></span>|<span data-ttu-id="0c975-157">…</span><span class="sxs-lookup"><span data-stu-id="0c975-157">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="0c975-158">Object</span><span class="sxs-lookup"><span data-stu-id="0c975-158">Object</span></span>  
 <span data-ttu-id="0c975-159">[という名前の型コンス トラクター](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md)など、ユーザー定義の (名前付き) のオブジェクトを構築します`person("abc", 12)`します。</span><span class="sxs-lookup"><span data-stu-id="0c975-159">[Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="0c975-160">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-160">Example:</span></span>  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="0c975-161">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-161">Output:</span></span>  
  
|<span data-ttu-id="0c975-162">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="0c975-162">SalesOrderDetailID</span></span>|<span data-ttu-id="0c975-163">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="0c975-163">CarrierTrackingNumber</span></span>|<span data-ttu-id="0c975-164">OrderQty</span><span class="sxs-lookup"><span data-stu-id="0c975-164">OrderQty</span></span>|<span data-ttu-id="0c975-165">ProductID</span><span class="sxs-lookup"><span data-stu-id="0c975-165">ProductID</span></span>|<span data-ttu-id="0c975-166">...</span><span class="sxs-lookup"><span data-stu-id="0c975-166">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="0c975-167">1</span><span class="sxs-lookup"><span data-stu-id="0c975-167">1</span></span>|<span data-ttu-id="0c975-168">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="0c975-168">4911-403C-98</span></span>|<span data-ttu-id="0c975-169">1</span><span class="sxs-lookup"><span data-stu-id="0c975-169">1</span></span>|<span data-ttu-id="0c975-170">776</span><span class="sxs-lookup"><span data-stu-id="0c975-170">776</span></span>|<span data-ttu-id="0c975-171">...</span><span class="sxs-lookup"><span data-stu-id="0c975-171">...</span></span>|  
|<span data-ttu-id="0c975-172">2</span><span class="sxs-lookup"><span data-stu-id="0c975-172">2</span></span>|<span data-ttu-id="0c975-173">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="0c975-173">4911-403C-98</span></span>|<span data-ttu-id="0c975-174">3</span><span class="sxs-lookup"><span data-stu-id="0c975-174">3</span></span>|<span data-ttu-id="0c975-175">777</span><span class="sxs-lookup"><span data-stu-id="0c975-175">777</span></span>|<span data-ttu-id="0c975-176">...</span><span class="sxs-lookup"><span data-stu-id="0c975-176">...</span></span>|  
|<span data-ttu-id="0c975-177">...</span><span class="sxs-lookup"><span data-stu-id="0c975-177">...</span></span>|<span data-ttu-id="0c975-178">...</span><span class="sxs-lookup"><span data-stu-id="0c975-178">...</span></span>|<span data-ttu-id="0c975-179">...</span><span class="sxs-lookup"><span data-stu-id="0c975-179">...</span></span>|<span data-ttu-id="0c975-180">...</span><span class="sxs-lookup"><span data-stu-id="0c975-180">...</span></span>|<span data-ttu-id="0c975-181">...</span><span class="sxs-lookup"><span data-stu-id="0c975-181">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="0c975-182">参照</span><span class="sxs-lookup"><span data-stu-id="0c975-182">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="0c975-183">REF</span><span class="sxs-lookup"><span data-stu-id="0c975-183">REF</span></span>  
 <span data-ttu-id="0c975-184">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)エンティティ型のインスタンスへの参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="0c975-184">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="0c975-185">たとえば、次のクエリは、Orders エンティティ セットの各 Order エンティティへの参照を返します。</span><span class="sxs-lookup"><span data-stu-id="0c975-185">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="0c975-186">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-186">Output:</span></span>  
  
|<span data-ttu-id="0c975-187">[値]</span><span class="sxs-lookup"><span data-stu-id="0c975-187">Value</span></span>|  
|-----------|  
|<span data-ttu-id="0c975-188">1</span><span class="sxs-lookup"><span data-stu-id="0c975-188">1</span></span>|  
|<span data-ttu-id="0c975-189">2</span><span class="sxs-lookup"><span data-stu-id="0c975-189">2</span></span>|  
|<span data-ttu-id="0c975-190">3</span><span class="sxs-lookup"><span data-stu-id="0c975-190">3</span></span>|  
|<span data-ttu-id="0c975-191">...</span><span class="sxs-lookup"><span data-stu-id="0c975-191">...</span></span>|  
  
 <span data-ttu-id="0c975-192">次の例では、プロパティ抽出演算子 (.) を使用して、エンティティのプロパティにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="0c975-192">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="0c975-193">プロパティ抽出演算子を使用すると、参照は自動的に逆参照されます。</span><span class="sxs-lookup"><span data-stu-id="0c975-193">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="0c975-194">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-194">Example:</span></span>  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="0c975-195">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-195">Output:</span></span>  
  
|<span data-ttu-id="0c975-196">[値]</span><span class="sxs-lookup"><span data-stu-id="0c975-196">Value</span></span>|  
|-----------|  
|<span data-ttu-id="0c975-197">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="0c975-197">Adjustable Race</span></span>|  
|<span data-ttu-id="0c975-198">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="0c975-198">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="0c975-199">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="0c975-199">AWC Logo Cap</span></span>|  
|<span data-ttu-id="0c975-200">...</span><span class="sxs-lookup"><span data-stu-id="0c975-200">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="0c975-201">DEREF</span><span class="sxs-lookup"><span data-stu-id="0c975-201">DEREF</span></span>  
 <span data-ttu-id="0c975-202">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)参照値とその結果が逆参照を生成を逆参照します。</span><span class="sxs-lookup"><span data-stu-id="0c975-202">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="0c975-203">たとえば、次のクエリは、`SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2` のように、Orders エンティティ セットの各 Order について Order エンティティを生成します。</span><span class="sxs-lookup"><span data-stu-id="0c975-203">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="0c975-204">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-204">Example:</span></span>  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="0c975-205">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-205">Output:</span></span>  
  
|<span data-ttu-id="0c975-206">[値]</span><span class="sxs-lookup"><span data-stu-id="0c975-206">Value</span></span>|  
|-----------|  
|<span data-ttu-id="0c975-207">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="0c975-207">Adjustable Race</span></span>|  
|<span data-ttu-id="0c975-208">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="0c975-208">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="0c975-209">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="0c975-209">AWC Logo Cap</span></span>|  
|<span data-ttu-id="0c975-210">...</span><span class="sxs-lookup"><span data-stu-id="0c975-210">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="0c975-211">CREATEREF と KEY</span><span class="sxs-lookup"><span data-stu-id="0c975-211">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="0c975-212">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)キーを渡す参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="0c975-212">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="0c975-213">[キー](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)型参照を持つ式のキー部分を抽出します。</span><span class="sxs-lookup"><span data-stu-id="0c975-213">[KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="0c975-214">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-214">Example:</span></span>  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="0c975-215">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-215">Output:</span></span>  
  
|<span data-ttu-id="0c975-216">ProductID</span><span class="sxs-lookup"><span data-stu-id="0c975-216">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="0c975-217">980</span><span class="sxs-lookup"><span data-stu-id="0c975-217">980</span></span>|  
|<span data-ttu-id="0c975-218">365</span><span class="sxs-lookup"><span data-stu-id="0c975-218">365</span></span>|  
|<span data-ttu-id="0c975-219">771</span><span class="sxs-lookup"><span data-stu-id="0c975-219">771</span></span>|  
|<span data-ttu-id="0c975-220">...</span><span class="sxs-lookup"><span data-stu-id="0c975-220">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="0c975-221">関数</span><span class="sxs-lookup"><span data-stu-id="0c975-221">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="0c975-222">正規</span><span class="sxs-lookup"><span data-stu-id="0c975-222">Canonical</span></span>  
 <span data-ttu-id="0c975-223">名前空間を[正規関数](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)としてでは、Edm では、`Edm.Length("string")`します。</span><span class="sxs-lookup"><span data-stu-id="0c975-223">The namespace for [canonical functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="0c975-224">正規関数と同じ名前の関数を含んでいる別の名前空間がインポートされない限り、名前空間を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0c975-224">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="0c975-225">2 つの名前空間に同じ関数が存在する場合は、完全な名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c975-225">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="0c975-226">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-226">Example:</span></span>  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="0c975-227">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-227">Output:</span></span>  
  
|<span data-ttu-id="0c975-228">NameLen</span><span class="sxs-lookup"><span data-stu-id="0c975-228">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="0c975-229">6</span><span class="sxs-lookup"><span data-stu-id="0c975-229">6</span></span>|  
|<span data-ttu-id="0c975-230">6</span><span class="sxs-lookup"><span data-stu-id="0c975-230">6</span></span>|  
|<span data-ttu-id="0c975-231">5</span><span class="sxs-lookup"><span data-stu-id="0c975-231">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="0c975-232">Microsoft プロバイダー固有</span><span class="sxs-lookup"><span data-stu-id="0c975-232">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="0c975-233">[Microsoft プロバイダー固有の関数](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)では、`SqlServer`名前空間。</span><span class="sxs-lookup"><span data-stu-id="0c975-233">[Microsoft provider-specific functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="0c975-234">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-234">Example:</span></span>  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="0c975-235">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-235">Output:</span></span>  
  
|<span data-ttu-id="0c975-236">EmailLen</span><span class="sxs-lookup"><span data-stu-id="0c975-236">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="0c975-237">27</span><span class="sxs-lookup"><span data-stu-id="0c975-237">27</span></span>|  
|<span data-ttu-id="0c975-238">27</span><span class="sxs-lookup"><span data-stu-id="0c975-238">27</span></span>|  
|<span data-ttu-id="0c975-239">26</span><span class="sxs-lookup"><span data-stu-id="0c975-239">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="0c975-240">名前空間</span><span class="sxs-lookup"><span data-stu-id="0c975-240">Namespaces</span></span>  
 <span data-ttu-id="0c975-241">[使用して](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md)クエリ式で使用される名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="0c975-241">[USING](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="0c975-242">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-242">Example:</span></span>  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="0c975-243">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-243">Output:</span></span>  
  
|<span data-ttu-id="0c975-244">[値]</span><span class="sxs-lookup"><span data-stu-id="0c975-244">Value</span></span>|  
|-----------|  
|<span data-ttu-id="0c975-245">aa</span><span class="sxs-lookup"><span data-stu-id="0c975-245">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="0c975-246">ページング</span><span class="sxs-lookup"><span data-stu-id="0c975-246">Paging</span></span>  
 <span data-ttu-id="0c975-247">ページングを宣言することで表すことができます、[スキップ](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)と[制限](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)サブ句を[ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)句。</span><span class="sxs-lookup"><span data-stu-id="0c975-247">Paging can be expressed by declaring a [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses to the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="0c975-248">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-248">Example:</span></span>  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="0c975-249">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-249">Output:</span></span>  
  
|<span data-ttu-id="0c975-250">ID</span><span class="sxs-lookup"><span data-stu-id="0c975-250">ID</span></span>|<span data-ttu-id="0c975-251">名前</span><span class="sxs-lookup"><span data-stu-id="0c975-251">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="0c975-252">10</span><span class="sxs-lookup"><span data-stu-id="0c975-252">10</span></span>|<span data-ttu-id="0c975-253">Adina</span><span class="sxs-lookup"><span data-stu-id="0c975-253">Adina</span></span>|  
|<span data-ttu-id="0c975-254">11</span><span class="sxs-lookup"><span data-stu-id="0c975-254">11</span></span>|<span data-ttu-id="0c975-255">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="0c975-255">Agcaoili</span></span>|  
|<span data-ttu-id="0c975-256">12</span><span class="sxs-lookup"><span data-stu-id="0c975-256">12</span></span>|<span data-ttu-id="0c975-257">Aguilar</span><span class="sxs-lookup"><span data-stu-id="0c975-257">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="0c975-258">グループ化</span><span class="sxs-lookup"><span data-stu-id="0c975-258">Grouping</span></span>  
 <span data-ttu-id="0c975-259">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md)クエリによって返されるオブジェクトにグループを指定します ([選択](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) 式を配置するのには。</span><span class="sxs-lookup"><span data-stu-id="0c975-259">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="0c975-260">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-260">Example:</span></span>  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="0c975-261">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-261">Output:</span></span>  
  
|<span data-ttu-id="0c975-262">name</span><span class="sxs-lookup"><span data-stu-id="0c975-262">name</span></span>|  
|----------|  
|<span data-ttu-id="0c975-263">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="0c975-263">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="0c975-264">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="0c975-264">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="0c975-265">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="0c975-265">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="0c975-266">...</span><span class="sxs-lookup"><span data-stu-id="0c975-266">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="0c975-267">ナビゲーション</span><span class="sxs-lookup"><span data-stu-id="0c975-267">Navigation</span></span>  
 <span data-ttu-id="0c975-268">リレーションシップ ナビゲーション操作を使用すると、開始側のエンティティと終了側のエンティティ間のリレーションシップをナビゲートできます。</span><span class="sxs-lookup"><span data-stu-id="0c975-268">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="0c975-269">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)として修飾されるリレーションシップ型では\<名前空間 >.\<リレーションシップ型の名前 >。</span><span class="sxs-lookup"><span data-stu-id="0c975-269">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="0c975-270">移動 Ref を返します\<T > 場合のカーディナリティ、終了するは 1 です。</span><span class="sxs-lookup"><span data-stu-id="0c975-270">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="0c975-271">場合のカーディナリティの終了が n、コレクション < Ref\<T >> が返されます。</span><span class="sxs-lookup"><span data-stu-id="0c975-271">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="0c975-272">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-272">Example:</span></span>  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="0c975-273">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-273">Output:</span></span>  
  
|<span data-ttu-id="0c975-274">AddressID</span><span class="sxs-lookup"><span data-stu-id="0c975-274">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="0c975-275">1</span><span class="sxs-lookup"><span data-stu-id="0c975-275">1</span></span>|  
|<span data-ttu-id="0c975-276">2</span><span class="sxs-lookup"><span data-stu-id="0c975-276">2</span></span>|  
|<span data-ttu-id="0c975-277">3</span><span class="sxs-lookup"><span data-stu-id="0c975-277">3</span></span>|  
|<span data-ttu-id="0c975-278">...</span><span class="sxs-lookup"><span data-stu-id="0c975-278">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="0c975-279">SELECT VALUE AND SELECT</span><span class="sxs-lookup"><span data-stu-id="0c975-279">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="0c975-280">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="0c975-280">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="0c975-281">暗黙の行の構築をスキップする SELECT VALUE 句を提供します。</span><span class="sxs-lookup"><span data-stu-id="0c975-281">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="0c975-282">SELECT VALUE 句には 1 つの項目のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c975-282">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="0c975-283">場合、このような句を使用して、SELECT 句内の項目に row ラッパーは構築されず、および、必要な構造のコレクションの作成例:`SELECT VALUE a`します。</span><span class="sxs-lookup"><span data-stu-id="0c975-283">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="0c975-284">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-284">Example:</span></span>  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="0c975-285">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-285">Output:</span></span>  
  
|<span data-ttu-id="0c975-286">名前</span><span class="sxs-lookup"><span data-stu-id="0c975-286">Name</span></span>|  
|----------|  
|<span data-ttu-id="0c975-287">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="0c975-287">Adjustable Race</span></span>|  
|<span data-ttu-id="0c975-288">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="0c975-288">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="0c975-289">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="0c975-289">AWC Logo Cap</span></span>|  
|<span data-ttu-id="0c975-290">...</span><span class="sxs-lookup"><span data-stu-id="0c975-290">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="0c975-291">SELECT</span><span class="sxs-lookup"><span data-stu-id="0c975-291">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="0c975-292">また、任意の行を構築する行コンス トラクターを提供します。</span><span class="sxs-lookup"><span data-stu-id="0c975-292">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="0c975-293">SELECT は、投影内の 1 つまたは複数の要素、および `SELECT a, b, c` などのフィールドを持つデータ レコードの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="0c975-293">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="0c975-294">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-294">Example:</span></span>  
  
 <span data-ttu-id="0c975-295">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-295">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="0c975-296">名前</span><span class="sxs-lookup"><span data-stu-id="0c975-296">Name</span></span>|<span data-ttu-id="0c975-297">ProductID</span><span class="sxs-lookup"><span data-stu-id="0c975-297">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="0c975-298">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="0c975-298">Adjustable Race</span></span>|<span data-ttu-id="0c975-299">1</span><span class="sxs-lookup"><span data-stu-id="0c975-299">1</span></span>|  
|<span data-ttu-id="0c975-300">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="0c975-300">All-Purpose Bike Stand</span></span>|<span data-ttu-id="0c975-301">879</span><span class="sxs-lookup"><span data-stu-id="0c975-301">879</span></span>|  
|<span data-ttu-id="0c975-302">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="0c975-302">AWC Logo Cap</span></span>|<span data-ttu-id="0c975-303">712</span><span class="sxs-lookup"><span data-stu-id="0c975-303">712</span></span>|  
|<span data-ttu-id="0c975-304">...</span><span class="sxs-lookup"><span data-stu-id="0c975-304">...</span></span>|<span data-ttu-id="0c975-305">...</span><span class="sxs-lookup"><span data-stu-id="0c975-305">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="0c975-306">CASE 式</span><span class="sxs-lookup"><span data-stu-id="0c975-306">CASE EXPRESSION</span></span>  
 <span data-ttu-id="0c975-307">[Case 式](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)一連の結果を決定するブール式を評価します。</span><span class="sxs-lookup"><span data-stu-id="0c975-307">The [case expression](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="0c975-308">例:</span><span class="sxs-lookup"><span data-stu-id="0c975-308">Example:</span></span>  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="0c975-309">Output:</span><span class="sxs-lookup"><span data-stu-id="0c975-309">Output:</span></span>  
  
|<span data-ttu-id="0c975-310">[値]</span><span class="sxs-lookup"><span data-stu-id="0c975-310">Value</span></span>|  
|-----------|  
|<span data-ttu-id="0c975-311">true</span><span class="sxs-lookup"><span data-stu-id="0c975-311">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c975-312">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c975-312">See also</span></span>

- [<span data-ttu-id="0c975-313">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="0c975-313">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="0c975-314">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="0c975-314">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
