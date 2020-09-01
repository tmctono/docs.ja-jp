---
description: クエリ キーワード - C# リファレンス
title: クエリ キーワード - C# リファレンス
ms.date: 07/20/2015
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
ms.openlocfilehash: 0beea8634d13222aa18f14d79fdbd95a35cc832e
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137137"
---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="30063-103">クエリ キーワード (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="30063-103">Query keywords (C# Reference)</span></span>

<span data-ttu-id="30063-104">このセクションでは、クエリ式で使用するコンテキスト キーワードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="30063-104">This section contains the contextual keywords used in query expressions.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="30063-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="30063-105">In this section</span></span>

|<span data-ttu-id="30063-106">句</span><span class="sxs-lookup"><span data-stu-id="30063-106">Clause</span></span>|<span data-ttu-id="30063-107">説明</span><span class="sxs-lookup"><span data-stu-id="30063-107">Description</span></span>|
|------------|-----------------|
|[<span data-ttu-id="30063-108">from</span><span class="sxs-lookup"><span data-stu-id="30063-108">from</span></span>](from-clause.md)|<span data-ttu-id="30063-109">データ ソースおよび範囲変数 (反復変数に類似) を指定します。</span><span class="sxs-lookup"><span data-stu-id="30063-109">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|
|[<span data-ttu-id="30063-110">where</span><span class="sxs-lookup"><span data-stu-id="30063-110">where</span></span>](where-clause.md)|<span data-ttu-id="30063-111">論理 AND 演算子 (`&&`) と論理 OR 演算子 (<code>&#124;&#124;</code>) で区切られた 1 つ以上のブール式に基づき、ソース要素をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="30063-111">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|
|[<span data-ttu-id="30063-112">select</span><span class="sxs-lookup"><span data-stu-id="30063-112">select</span></span>](select-clause.md)|<span data-ttu-id="30063-113">クエリ実行で返されるシーケンスに含まれる要素の型と形状を指定します。</span><span class="sxs-lookup"><span data-stu-id="30063-113">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|
|[<span data-ttu-id="30063-114">group</span><span class="sxs-lookup"><span data-stu-id="30063-114">group</span></span>](group-clause.md)|<span data-ttu-id="30063-115">指定したキー値に基づき、クエリ結果をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="30063-115">Groups query results according to a specified key value.</span></span>|
|[<span data-ttu-id="30063-116">into</span><span class="sxs-lookup"><span data-stu-id="30063-116">into</span></span>](into.md)|<span data-ttu-id="30063-117">join 句、group 句、または select 句の結果への参照として機能する識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="30063-117">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|
|[<span data-ttu-id="30063-118">orderby</span><span class="sxs-lookup"><span data-stu-id="30063-118">orderby</span></span>](orderby-clause.md)|<span data-ttu-id="30063-119">要素型の既定の比較子に基づき、クエリ結果を昇順または降順で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="30063-119">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|
|[<span data-ttu-id="30063-120">join</span><span class="sxs-lookup"><span data-stu-id="30063-120">join</span></span>](join-clause.md)|<span data-ttu-id="30063-121">指定した 2 つの一致基準の等価比較に基づき、2 つのデータ ソースを結合します。</span><span class="sxs-lookup"><span data-stu-id="30063-121">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|
|[<span data-ttu-id="30063-122">let</span><span class="sxs-lookup"><span data-stu-id="30063-122">let</span></span>](let-clause.md)|<span data-ttu-id="30063-123">範囲変数を使用して、クエリ式のサブ式の結果を格納します。</span><span class="sxs-lookup"><span data-stu-id="30063-123">Introduces a range variable to store sub-expression results in a query expression.</span></span>|
|[<span data-ttu-id="30063-124">in</span><span class="sxs-lookup"><span data-stu-id="30063-124">in</span></span>](in.md)|<span data-ttu-id="30063-125">[join](join-clause.md) 句のコンテキスト キーワードです。</span><span class="sxs-lookup"><span data-stu-id="30063-125">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="30063-126">on</span><span class="sxs-lookup"><span data-stu-id="30063-126">on</span></span>](on.md)|<span data-ttu-id="30063-127">[join](join-clause.md) 句のコンテキスト キーワードです。</span><span class="sxs-lookup"><span data-stu-id="30063-127">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="30063-128">equals</span><span class="sxs-lookup"><span data-stu-id="30063-128">equals</span></span>](equals.md)|<span data-ttu-id="30063-129">[join](join-clause.md) 句のコンテキスト キーワードです。</span><span class="sxs-lookup"><span data-stu-id="30063-129">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="30063-130">by</span><span class="sxs-lookup"><span data-stu-id="30063-130">by</span></span>](by.md)|<span data-ttu-id="30063-131">[group](group-clause.md) 句のコンテキスト キーワードです。</span><span class="sxs-lookup"><span data-stu-id="30063-131">Contextual keyword in a [group](group-clause.md) clause.</span></span>|
|[<span data-ttu-id="30063-132">ascending</span><span class="sxs-lookup"><span data-stu-id="30063-132">ascending</span></span>](ascending.md)|<span data-ttu-id="30063-133">[orderby](orderby-clause.md) 句のコンテキスト キーワードです。</span><span class="sxs-lookup"><span data-stu-id="30063-133">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|
|[<span data-ttu-id="30063-134">descending</span><span class="sxs-lookup"><span data-stu-id="30063-134">descending</span></span>](descending.md)|<span data-ttu-id="30063-135">[orderby](orderby-clause.md) 句のコンテキスト キーワードです。</span><span class="sxs-lookup"><span data-stu-id="30063-135">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|

## <a name="see-also"></a><span data-ttu-id="30063-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="30063-136">See also</span></span>

- [<span data-ttu-id="30063-137">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="30063-137">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="30063-138">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="30063-138">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="30063-139">C# での LINQ</span><span class="sxs-lookup"><span data-stu-id="30063-139">LINQ in C#</span></span>](../../linq/index.md)
