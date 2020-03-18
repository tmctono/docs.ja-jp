---
title: 入れ子になったグループの作成 (C# での LINQ)
description: C# で LINQ クエリ式に入れ子になったグループを作成する方法について説明します。
ms.date: 12/01/2016
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: 7d056c9e215ccc7ca24d621b64e2328bed79f22e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "61688619"
---
# <a name="create-a-nested-group"></a><span data-ttu-id="60327-103">入れ子になったグループの作成</span><span class="sxs-lookup"><span data-stu-id="60327-103">Create a nested group</span></span>

<span data-ttu-id="60327-104">LINQ クエリ式で入れ子になったグループを作成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="60327-104">The following example shows how to create nested groups in a LINQ query expression.</span></span> <span data-ttu-id="60327-105">学年レベルに基づいて作成した各グループを、さらに個人の名前に基づくグループに分割します。</span><span class="sxs-lookup"><span data-stu-id="60327-105">Each group that is created according to student year or grade level is then further subdivided into groups based on the individuals' names.</span></span>

## <a name="example"></a><span data-ttu-id="60327-106">例</span><span class="sxs-lookup"><span data-stu-id="60327-106">Example</span></span>

> [!NOTE]
> <span data-ttu-id="60327-107">この例には、「[オブジェクトのコレクションの照会](query-a-collection-of-objects.md)」のサンプル コードで定義されているオブジェクトへの参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="60327-107">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

[!code-csharp[csProgGuideLINQ#24](~/samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]

<span data-ttu-id="60327-108">入れ子になったグループの内部要素に対して反復処理を実行するために、入れ子になった `foreach` ループが 3 つ必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="60327-108">Note that three nested `foreach` loops are required to iterate over the inner elements of a nested group.</span></span>

## <a name="see-also"></a><span data-ttu-id="60327-109">参照</span><span class="sxs-lookup"><span data-stu-id="60327-109">See also</span></span>

- [<span data-ttu-id="60327-110">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="60327-110">Language Integrated Query (LINQ)</span></span>](index.md)
