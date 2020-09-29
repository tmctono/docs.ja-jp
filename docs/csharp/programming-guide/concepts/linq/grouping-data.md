---
title: データのグループ化 (C#)
description: グループ化によって、属性を共有する要素のグループにデータが格納されます。 データ要素をグループ化する C# での LINQ の標準クエリ演算子メソッドについて学習します。
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: 584d50fc15dd8b4ce1cfdf4766f3bc8b8383eb12
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202566"
---
# <a name="grouping-data-c"></a><span data-ttu-id="66d78-104">データのグループ化 (C#)</span><span class="sxs-lookup"><span data-stu-id="66d78-104">Grouping Data (C#)</span></span>

<span data-ttu-id="66d78-105">グループ化とは、各グループの要素が共通の属性を持つようにデータをグループに分ける操作を指します。</span><span class="sxs-lookup"><span data-stu-id="66d78-105">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="66d78-106">次の図は、文字のシーケンスをグループ化した結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="66d78-106">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="66d78-107">各グループのキーは文字です。</span><span class="sxs-lookup"><span data-stu-id="66d78-107">The key for each group is the character.</span></span>  
  
 ![LINQ グループ化操作を示す図。](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="66d78-109">次のセクションでは、データ要素をグループ化する標準クエリ演算子メソッドの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="66d78-109">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="66d78-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="66d78-110">Methods</span></span>  
  
|<span data-ttu-id="66d78-111">メソッド名</span><span class="sxs-lookup"><span data-stu-id="66d78-111">Method Name</span></span>|<span data-ttu-id="66d78-112">説明</span><span class="sxs-lookup"><span data-stu-id="66d78-112">Description</span></span>|<span data-ttu-id="66d78-113">C# のクエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="66d78-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="66d78-114">説明</span><span class="sxs-lookup"><span data-stu-id="66d78-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="66d78-115">GroupBy</span><span class="sxs-lookup"><span data-stu-id="66d78-115">GroupBy</span></span>|<span data-ttu-id="66d78-116">共通の属性を共有する要素をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="66d78-116">Groups elements that share a common attribute.</span></span> <span data-ttu-id="66d78-117">各グループは <xref:System.Linq.IGrouping%602> オブジェクトによって表されます。</span><span class="sxs-lookup"><span data-stu-id="66d78-117">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="66d78-118">\- または -</span><span class="sxs-lookup"><span data-stu-id="66d78-118">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="66d78-119">ToLookup</span><span class="sxs-lookup"><span data-stu-id="66d78-119">ToLookup</span></span>|<span data-ttu-id="66d78-120">キー セレクター関数に基づいて、<xref:System.Linq.Lookup%602> (一対多の辞書) に要素を挿入します。</span><span class="sxs-lookup"><span data-stu-id="66d78-120">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="66d78-121">該当なし。</span><span class="sxs-lookup"><span data-stu-id="66d78-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="66d78-122">クエリ式の構文例</span><span class="sxs-lookup"><span data-stu-id="66d78-122">Query Expression Syntax Example</span></span>  

 <span data-ttu-id="66d78-123">次のコード例では、`group by` 句を使用して、偶数か奇数かによってリスト内の整数をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="66d78-123">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="66d78-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="66d78-124">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="66d78-125">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="66d78-125">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="66d78-126">group 句</span><span class="sxs-lookup"><span data-stu-id="66d78-126">group clause</span></span>](../../../language-reference/keywords/group-clause.md)
- [<span data-ttu-id="66d78-127">入れ子になったグループの作成</span><span class="sxs-lookup"><span data-stu-id="66d78-127">Create a nested group</span></span>](../../../linq/create-a-nested-group.md)
- [<span data-ttu-id="66d78-128">拡張子別にファイルをグループ化する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="66d78-128">How to group files by extension (LINQ) (C#)</span></span>](./how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="66d78-129">クエリ結果のグループ化</span><span class="sxs-lookup"><span data-stu-id="66d78-129">Group query results</span></span>](../../../linq/group-query-results.md)
- [<span data-ttu-id="66d78-130">グループ化操作でのサブクエリの実行</span><span class="sxs-lookup"><span data-stu-id="66d78-130">Perform a subquery on a grouping operation</span></span>](../../../linq/perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="66d78-131">グループを使用して 1 つのファイルを複数のファイルに分割する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="66d78-131">How to split a file into many files by using groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
