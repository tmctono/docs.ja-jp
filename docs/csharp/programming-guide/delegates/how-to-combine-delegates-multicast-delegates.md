---
title: デリゲートを結合する方法 (マルチキャスト デリゲート) - C# プログラミング ガイド
description: デリゲートを結合してマルチキャスト デリゲートを作成する方法について説明します。 コード例を参照し、使用可能なその他のリソースを確認します。
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d23ea758c9da2c3399f5d98e81360cc250b428a1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302738"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a><span data-ttu-id="5455f-104">デリゲートを結合する方法 (マルチキャスト デリゲート) (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="5455f-104">How to combine delegates (Multicast Delegates) (C# Programming Guide)</span></span>
<span data-ttu-id="5455f-105">ここでは、マルチキャスト デリゲートを作成する例について説明します。</span><span class="sxs-lookup"><span data-stu-id="5455f-105">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="5455f-106">[デリゲート](../../language-reference/builtin-types/reference-types.md) オブジェクトの便利な性質の 1 つは、`+` 演算子を使用して、複数のオブジェクトを 1 つのデリゲート インスタンスに割り当てられることです。</span><span class="sxs-lookup"><span data-stu-id="5455f-106">A useful property of [delegate](../../language-reference/builtin-types/reference-types.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="5455f-107">マルチキャスト デリゲートには、割り当てられたデリゲートの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5455f-107">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="5455f-108">マルチキャスト デリゲートを呼び出すと、一覧内のデリゲートが順に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5455f-108">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="5455f-109">結合できるのは、同じ型のデリゲートのみです。</span><span class="sxs-lookup"><span data-stu-id="5455f-109">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="5455f-110">`-` 演算子を使用して、マルチキャスト デリゲートからコンポーネント デリゲートを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5455f-110">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5455f-111">例</span><span class="sxs-lookup"><span data-stu-id="5455f-111">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="5455f-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5455f-112">See also</span></span>

- <xref:System.MulticastDelegate>
- [<span data-ttu-id="5455f-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="5455f-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5455f-114">イベント</span><span class="sxs-lookup"><span data-stu-id="5455f-114">Events</span></span>](../events/index.md)
