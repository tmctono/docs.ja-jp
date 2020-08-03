---
title: データのグループ化 (C#)
description: グループ化によって、属性を共有する要素のグループにデータが格納されます。 データ要素をグループ化する C# での LINQ の標準クエリ演算子メソッドについて学習します。
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: 5e1bca1d360b0f44a081cf2770118a0551629b5b
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103687"
---
# <a name="grouping-data-c"></a><span data-ttu-id="cc739-104">データのグループ化 (C#)</span><span class="sxs-lookup"><span data-stu-id="cc739-104">Grouping Data (C#)</span></span>
<span data-ttu-id="cc739-105">グループ化とは、各グループの要素が共通の属性を持つようにデータをグループに分ける操作を指します。</span><span class="sxs-lookup"><span data-stu-id="cc739-105">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="cc739-106">次の図は、文字のシーケンスをグループ化した結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="cc739-106">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="cc739-107">各グループのキーは文字です。</span><span class="sxs-lookup"><span data-stu-id="cc739-107">The key for each group is the character.</span></span>  
  
 ![LINQ グループ化操作を示す図。](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="cc739-109">次のセクションでは、データ要素をグループ化する標準クエリ演算子メソッドの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="cc739-109">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cc739-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="cc739-110">Methods</span></span>  
  
|<span data-ttu-id="cc739-111">メソッド名</span><span class="sxs-lookup"><span data-stu-id="cc739-111">Method Name</span></span>|<span data-ttu-id="cc739-112">説明</span><span class="sxs-lookup"><span data-stu-id="cc739-112">Description</span></span>|<span data-ttu-id="cc739-113">C# のクエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="cc739-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="cc739-114">説明</span><span class="sxs-lookup"><span data-stu-id="cc739-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="cc739-115">GroupBy</span><span class="sxs-lookup"><span data-stu-id="cc739-115">GroupBy</span></span>|<span data-ttu-id="cc739-116">共通の属性を共有する要素をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="cc739-116">Groups elements that share a common attribute.</span></span> <span data-ttu-id="cc739-117">各グループは <xref:System.Linq.IGrouping%602> オブジェクトによって表されます。</span><span class="sxs-lookup"><span data-stu-id="cc739-117">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="cc739-118">\- または -</span><span class="sxs-lookup"><span data-stu-id="cc739-118">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="cc739-119">ToLookup</span><span class="sxs-lookup"><span data-stu-id="cc739-119">ToLookup</span></span>|<span data-ttu-id="cc739-120">キー セレクター関数に基づいて、<xref:System.Linq.Lookup%602> (一対多の辞書) に要素を挿入します。</span><span class="sxs-lookup"><span data-stu-id="cc739-120">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="cc739-121">該当なし。</span><span class="sxs-lookup"><span data-stu-id="cc739-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="cc739-122">クエリ式の構文例</span><span class="sxs-lookup"><span data-stu-id="cc739-122">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="cc739-123">次のコード例では、`group by` 句を使用して、偶数か奇数かによってリスト内の整数をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="cc739-123">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc739-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc739-124">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="cc739-125">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="cc739-125">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="cc739-126">group 句</span><span class="sxs-lookup"><span data-stu-id="cc739-126">group clause</span></span>](../../../language-reference/keywords/group-clause.md)
- [<span data-ttu-id="cc739-127">入れ子になったグループの作成</span><span class="sxs-lookup"><span data-stu-id="cc739-127">Create a nested group</span></span>](../../../linq/create-a-nested-group.md)
- [<span data-ttu-id="cc739-128">拡張子別にファイルをグループ化する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="cc739-128">How to group files by extension (LINQ) (C#)</span></span>](./how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="cc739-129">クエリ結果のグループ化</span><span class="sxs-lookup"><span data-stu-id="cc739-129">Group query results</span></span>](../../../linq/group-query-results.md)
- [<span data-ttu-id="cc739-130">グループ化操作でのサブクエリの実行</span><span class="sxs-lookup"><span data-stu-id="cc739-130">Perform a subquery on a grouping operation</span></span>](../../../linq/perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="cc739-131">グループを使用して 1 つのファイルを複数のファイルに分割する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="cc739-131">How to split a file into many files by using groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
