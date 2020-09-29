---
title: データのフィルター処理 (C#)
description: フィルター処理は、選択とも呼ばれ、条件に基づいて結果が限定されます。 フィルター処理を実行する C# での LINQ の標準クエリ演算子メソッドについて学習します。
ms.date: 07/20/2015
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
ms.openlocfilehash: 51bf9f930ba67ba07c7c0f357910d5e36014138d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186043"
---
# <a name="filtering-data-c"></a><span data-ttu-id="890a3-104">データのフィルター処理 (C#)</span><span class="sxs-lookup"><span data-stu-id="890a3-104">Filtering Data (C#)</span></span>

<span data-ttu-id="890a3-105">フィルター処理とは、特定の条件を満たす要素のみが含まれるように結果セットを限定する操作のことです。</span><span class="sxs-lookup"><span data-stu-id="890a3-105">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="890a3-106">選択とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="890a3-106">It is also known as selection.</span></span>  
  
 <span data-ttu-id="890a3-107">次の図は、文字のシーケンスをフィルター処理した結果を示したものです。</span><span class="sxs-lookup"><span data-stu-id="890a3-107">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="890a3-108">フィルター処理操作の述語では、文字が "A" でなければならないことが指定されています。</span><span class="sxs-lookup"><span data-stu-id="890a3-108">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 ![LINQ のフィルター操作を示す図。](./media/filtering-data/linq-filter-operation.png)  
  
 <span data-ttu-id="890a3-110">次のセクションでは、選択を実行する標準クエリ演算子メソッドの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="890a3-110">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="890a3-111">メソッド</span><span class="sxs-lookup"><span data-stu-id="890a3-111">Methods</span></span>  
  
|<span data-ttu-id="890a3-112">メソッド名</span><span class="sxs-lookup"><span data-stu-id="890a3-112">Method Name</span></span>|<span data-ttu-id="890a3-113">説明</span><span class="sxs-lookup"><span data-stu-id="890a3-113">Description</span></span>|<span data-ttu-id="890a3-114">C# のクエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="890a3-114">C# Query Expression Syntax</span></span>|<span data-ttu-id="890a3-115">説明</span><span class="sxs-lookup"><span data-stu-id="890a3-115">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="890a3-116">OfType</span><span class="sxs-lookup"><span data-stu-id="890a3-116">OfType</span></span>|<span data-ttu-id="890a3-117">指定した型にキャストできるかどうかにより、値を選択します。</span><span class="sxs-lookup"><span data-stu-id="890a3-117">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="890a3-118">該当なし。</span><span class="sxs-lookup"><span data-stu-id="890a3-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="890a3-119">Where</span><span class="sxs-lookup"><span data-stu-id="890a3-119">Where</span></span>|<span data-ttu-id="890a3-120">述語関数に基づいて値を選択します。</span><span class="sxs-lookup"><span data-stu-id="890a3-120">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="890a3-121">クエリ式の構文例</span><span class="sxs-lookup"><span data-stu-id="890a3-121">Query Expression Syntax Example</span></span>  

 <span data-ttu-id="890a3-122">次の例では、`where` 句を使って、配列から特定の長さを持つ文字列をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="890a3-122">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            where word.Length == 3  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="890a3-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="890a3-123">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="890a3-124">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="890a3-124">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="890a3-125">where 句</span><span class="sxs-lookup"><span data-stu-id="890a3-125">where clause</span></span>](../../../language-reference/keywords/where-clause.md)
- [<span data-ttu-id="890a3-126">実行時における述語フィルターの動的指定</span><span class="sxs-lookup"><span data-stu-id="890a3-126">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="890a3-127">リフレクションを使用してアセンブリのメタデータにクエリを実行する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="890a3-127">How to query an assembly's metadata with Reflection (LINQ) (C#)</span></span>](./how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="890a3-128">指定された属性または名前のファイルを照会する方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="890a3-128">How to query for files with a specified attribute or name (C#)</span></span>](./how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="890a3-129">任意のワードまたはフィールドを基準にテキスト データの並べ替えまたはフィルター処理を実行する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="890a3-129">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
