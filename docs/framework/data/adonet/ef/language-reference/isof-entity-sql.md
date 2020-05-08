---
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: c4c4cbf74cb17cf43e79c42ff42d1e68122fd534
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319714"
---
# <a name="isof-entity-sql"></a><span data-ttu-id="91ddd-102">ISOF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="91ddd-102">ISOF (Entity SQL)</span></span>
<span data-ttu-id="91ddd-103">式の型が指定の型であるか、またはそのサブタイプであるかを判断します。</span><span class="sxs-lookup"><span data-stu-id="91ddd-103">Determines whether the type of an expression is of the specified type or one of its subtypes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91ddd-104">構文</span><span class="sxs-lookup"><span data-stu-id="91ddd-104">Syntax</span></span>  
  
```sql  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="91ddd-105">引数</span><span class="sxs-lookup"><span data-stu-id="91ddd-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="91ddd-106">型を判断するための任意の有効なクエリ式。</span><span class="sxs-lookup"><span data-stu-id="91ddd-106">Any valid query expression to determine the type of.</span></span>  
  
 <span data-ttu-id="91ddd-107">NOT</span><span class="sxs-lookup"><span data-stu-id="91ddd-107">NOT</span></span>  
 <span data-ttu-id="91ddd-108">IS OF の EDM.Boolean の結果を否定します。</span><span class="sxs-lookup"><span data-stu-id="91ddd-108">Negates the EDM.Boolean result of IS OF.</span></span>  
  
 <span data-ttu-id="91ddd-109">ONLY</span><span class="sxs-lookup"><span data-stu-id="91ddd-109">ONLY</span></span>  
 <span data-ttu-id="91ddd-110">`true` が `expression` 型であり、そのサブタイプでない場合に限り、IS OF が `type` を返すことを指定します。</span><span class="sxs-lookup"><span data-stu-id="91ddd-110">Specifies that IS OF returns `true` only if `expression` is of type `type` and not any of one its subtypes.</span></span>  
  
 `type`  
 <span data-ttu-id="91ddd-111">`expression` を判定するための型。</span><span class="sxs-lookup"><span data-stu-id="91ddd-111">The type to test `expression` against.</span></span> <span data-ttu-id="91ddd-112">型は名前空間で修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91ddd-112">The type must be namespace-qualified.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91ddd-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="91ddd-113">Return Value</span></span>  
 <span data-ttu-id="91ddd-114">`true` が型 T で、T が基本データ型または `expression` の派生型である場合は、`type` となります。`expression` が実行時に null である場合は null となり、それ以外の場合は `false` となります。</span><span class="sxs-lookup"><span data-stu-id="91ddd-114">`true` if `expression` is of type T and T is either a base type, or a derived type of `type`; null if `expression` is null at runtime; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91ddd-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="91ddd-115">Remarks</span></span>  
 <span data-ttu-id="91ddd-116">式 `expression IS NOT OF (type)` および `expression IS NOT OF (ONLY type)` は、構文的にはそれぞれ `NOT (expression IS OF (type))` および `NOT (expression IS OF (ONLY type))` に相当します。</span><span class="sxs-lookup"><span data-stu-id="91ddd-116">The expressions `expression IS NOT OF (type)` and `expression IS NOT OF (ONLY type)` are syntactically equivalent to `NOT (expression IS OF (type))` and `NOT (expression IS OF (ONLY type))`, respectively.</span></span>  
  
 <span data-ttu-id="91ddd-117">次の表に、いくつかの通常およびコーナー パターンにおける `IS OF` 演算子の動作を示します。</span><span class="sxs-lookup"><span data-stu-id="91ddd-117">The following table shows the behavior of `IS OF` operator over some typical- and corner patterns.</span></span> <span data-ttu-id="91ddd-118">すべての例外はクライアント側にスローされてから、プロバイダーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="91ddd-118">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="91ddd-119">パターン</span><span class="sxs-lookup"><span data-stu-id="91ddd-119">Pattern</span></span>|<span data-ttu-id="91ddd-120">動作</span><span class="sxs-lookup"><span data-stu-id="91ddd-120">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="91ddd-121">null IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="91ddd-121">null IS OF (EntityType)</span></span>|<span data-ttu-id="91ddd-122">スロー</span><span class="sxs-lookup"><span data-stu-id="91ddd-122">Throws</span></span>|  
|<span data-ttu-id="91ddd-123">null IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="91ddd-123">null IS OF (ComplexType)</span></span>|<span data-ttu-id="91ddd-124">スロー</span><span class="sxs-lookup"><span data-stu-id="91ddd-124">Throws</span></span>|  
|<span data-ttu-id="91ddd-125">null IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="91ddd-125">null IS OF (RowType)</span></span>|<span data-ttu-id="91ddd-126">スロー</span><span class="sxs-lookup"><span data-stu-id="91ddd-126">Throws</span></span>|  
|<span data-ttu-id="91ddd-127">TREAT (null AS EntityType) IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="91ddd-127">TREAT (null AS EntityType) IS OF (EntityType)</span></span>|<span data-ttu-id="91ddd-128">DBNull を返します。</span><span class="sxs-lookup"><span data-stu-id="91ddd-128">Returns DBNull</span></span>|  
|<span data-ttu-id="91ddd-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="91ddd-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span></span>|<span data-ttu-id="91ddd-130">スロー</span><span class="sxs-lookup"><span data-stu-id="91ddd-130">Throws</span></span>|  
|<span data-ttu-id="91ddd-131">TREAT (null AS RowType) IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="91ddd-131">TREAT (null AS RowType) IS OF (RowType)</span></span>|<span data-ttu-id="91ddd-132">スロー</span><span class="sxs-lookup"><span data-stu-id="91ddd-132">Throws</span></span>|  
|<span data-ttu-id="91ddd-133">EntityType IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="91ddd-133">EntityType IS OF (EntityType)</span></span>|<span data-ttu-id="91ddd-134">true または false を返します。</span><span class="sxs-lookup"><span data-stu-id="91ddd-134">Returns true/false</span></span>|  
|<span data-ttu-id="91ddd-135">ComplexType IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="91ddd-135">ComplexType IS OF (ComplexType)</span></span>|<span data-ttu-id="91ddd-136">スロー</span><span class="sxs-lookup"><span data-stu-id="91ddd-136">Throws</span></span>|  
|<span data-ttu-id="91ddd-137">RowType IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="91ddd-137">RowType IS OF (RowType)</span></span>|<span data-ttu-id="91ddd-138">スロー</span><span class="sxs-lookup"><span data-stu-id="91ddd-138">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="91ddd-139">例</span><span class="sxs-lookup"><span data-stu-id="91ddd-139">Example</span></span>  
 <span data-ttu-id="91ddd-140">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] の次のクエリでは、IS OF 演算子を使用してクエリ式の型を判定し、次に TREAT 演算子を使用して Course 型のオブジェクトを OnsiteCourse 型のオブジェクトのコレクションに変換します。</span><span class="sxs-lookup"><span data-stu-id="91ddd-140">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS OF operator to determine the type of a query expression, and then uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="91ddd-141">このクエリは、 [School モデル](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100))に基づいています。</span><span class="sxs-lookup"><span data-stu-id="91ddd-141">The query is based on the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 <span data-ttu-id="91ddd-142">[!code-sql[DP EntityServices Concepts#TREAT_ISOF]~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#treat_isof)]</span><span class="sxs-lookup"><span data-stu-id="91ddd-142">[!code-sql[DP EntityServices Concepts#TREAT_ISOF]~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#treat_isof)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91ddd-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="91ddd-143">See also</span></span>

- [<span data-ttu-id="91ddd-144">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="91ddd-144">Entity SQL Reference</span></span>](entity-sql-reference.md)
