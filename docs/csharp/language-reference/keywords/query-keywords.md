---
title: クエリ キーワード - C# リファレンス
ms.date: 07/20/2015
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
ms.openlocfilehash: 01134eda540c5141afbd11b2c89ff779da495a9a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173524"
---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="434f4-102">クエリ キーワード (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="434f4-102">Query keywords (C# Reference)</span></span>

<span data-ttu-id="434f4-103">このセクションでは、クエリ式で使用するコンテキスト キーワードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="434f4-103">This section contains the contextual keywords used in query expressions.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="434f4-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="434f4-104">In this section</span></span>

|<span data-ttu-id="434f4-105">句</span><span class="sxs-lookup"><span data-stu-id="434f4-105">Clause</span></span>|<span data-ttu-id="434f4-106">[説明]</span><span class="sxs-lookup"><span data-stu-id="434f4-106">Description</span></span>|
|------------|-----------------|
|[<span data-ttu-id="434f4-107">from</span><span class="sxs-lookup"><span data-stu-id="434f4-107">from</span></span>](from-clause.md)|<span data-ttu-id="434f4-108">データ ソースおよび範囲変数 (反復変数に類似) を指定します。</span><span class="sxs-lookup"><span data-stu-id="434f4-108">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|
|[<span data-ttu-id="434f4-109">where</span><span class="sxs-lookup"><span data-stu-id="434f4-109">where</span></span>](where-clause.md)|<span data-ttu-id="434f4-110">論理 AND 演算子 (`&&`) と論理 OR 演算子 (<code>&#124;&#124;</code>) で区切られた 1 つ以上のブール式に基づき、ソース要素をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="434f4-110">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|
|[<span data-ttu-id="434f4-111">select</span><span class="sxs-lookup"><span data-stu-id="434f4-111">select</span></span>](select-clause.md)|<span data-ttu-id="434f4-112">クエリ実行で返されるシーケンスに含まれる要素の型と形状を指定します。</span><span class="sxs-lookup"><span data-stu-id="434f4-112">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|
|[<span data-ttu-id="434f4-113">グループ</span><span class="sxs-lookup"><span data-stu-id="434f4-113">group</span></span>](group-clause.md)|<span data-ttu-id="434f4-114">指定したキー値に基づき、クエリ結果をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="434f4-114">Groups query results according to a specified key value.</span></span>|
|[<span data-ttu-id="434f4-115">into</span><span class="sxs-lookup"><span data-stu-id="434f4-115">into</span></span>](into.md)|<span data-ttu-id="434f4-116">join 句、group 句、または select 句の結果への参照として機能する識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="434f4-116">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|
|[<span data-ttu-id="434f4-117">orderby</span><span class="sxs-lookup"><span data-stu-id="434f4-117">orderby</span></span>](orderby-clause.md)|<span data-ttu-id="434f4-118">要素型の既定の比較子に基づき、クエリ結果を昇順または降順で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="434f4-118">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|
|[<span data-ttu-id="434f4-119">join</span><span class="sxs-lookup"><span data-stu-id="434f4-119">join</span></span>](join-clause.md)|<span data-ttu-id="434f4-120">指定した 2 つの一致基準の等価比較に基づき、2 つのデータ ソースを結合します。</span><span class="sxs-lookup"><span data-stu-id="434f4-120">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|
|[<span data-ttu-id="434f4-121">let</span><span class="sxs-lookup"><span data-stu-id="434f4-121">let</span></span>](let-clause.md)|<span data-ttu-id="434f4-122">範囲変数を使用して、クエリ式のサブ式の結果を格納します。</span><span class="sxs-lookup"><span data-stu-id="434f4-122">Introduces a range variable to store sub-expression results in a query expression.</span></span>|
|[<span data-ttu-id="434f4-123">in</span><span class="sxs-lookup"><span data-stu-id="434f4-123">in</span></span>](in.md)|<span data-ttu-id="434f4-124">[join](join-clause.md) 句のコンテキスト キーワードです。</span><span class="sxs-lookup"><span data-stu-id="434f4-124">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="434f4-125">on</span><span class="sxs-lookup"><span data-stu-id="434f4-125">on</span></span>](on.md)|<span data-ttu-id="434f4-126">[join](join-clause.md) 句のコンテキスト キーワードです。</span><span class="sxs-lookup"><span data-stu-id="434f4-126">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="434f4-127">equals</span><span class="sxs-lookup"><span data-stu-id="434f4-127">equals</span></span>](equals.md)|<span data-ttu-id="434f4-128">[join](join-clause.md) 句のコンテキスト キーワードです。</span><span class="sxs-lookup"><span data-stu-id="434f4-128">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="434f4-129">by</span><span class="sxs-lookup"><span data-stu-id="434f4-129">by</span></span>](by.md)|<span data-ttu-id="434f4-130">[group](group-clause.md) 句のコンテキスト キーワードです。</span><span class="sxs-lookup"><span data-stu-id="434f4-130">Contextual keyword in a [group](group-clause.md) clause.</span></span>|
|[<span data-ttu-id="434f4-131">ascending</span><span class="sxs-lookup"><span data-stu-id="434f4-131">ascending</span></span>](ascending.md)|<span data-ttu-id="434f4-132">[orderby](orderby-clause.md) 句のコンテキスト キーワードです。</span><span class="sxs-lookup"><span data-stu-id="434f4-132">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|
|[<span data-ttu-id="434f4-133">descending</span><span class="sxs-lookup"><span data-stu-id="434f4-133">descending</span></span>](descending.md)|<span data-ttu-id="434f4-134">[orderby](orderby-clause.md) 句のコンテキスト キーワードです。</span><span class="sxs-lookup"><span data-stu-id="434f4-134">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|

## <a name="see-also"></a><span data-ttu-id="434f4-135">参照</span><span class="sxs-lookup"><span data-stu-id="434f4-135">See also</span></span>

- [<span data-ttu-id="434f4-136">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="434f4-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="434f4-137">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="434f4-137">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="434f4-138">C# での LINQ</span><span class="sxs-lookup"><span data-stu-id="434f4-138">LINQ in C#</span></span>](../../linq/index.md)
