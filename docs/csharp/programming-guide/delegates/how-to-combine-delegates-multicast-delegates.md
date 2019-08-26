---
title: '方法: デリゲートを結合する (マルチキャスト デリゲート) - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d9430021e6a9b438822f1a6dc201f64adf4fdb0f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69590665"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="f1378-102">方法: デリゲートを結合する (マルチキャスト デリゲート) (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="f1378-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="f1378-103">ここでは、マルチキャスト デリゲートを作成する例について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1378-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="f1378-104">[デリゲート](../../language-reference/keywords/delegate.md) オブジェクトの便利な性質の 1 つは、`+` 演算子を使用して、複数のオブジェクトを 1 つのデリゲート インスタンスに割り当てられることです。</span><span class="sxs-lookup"><span data-stu-id="f1378-104">A useful property of [delegate](../../language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="f1378-105">マルチキャスト デリゲートには、割り当てられたデリゲートの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1378-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="f1378-106">マルチキャスト デリゲートを呼び出すと、一覧内のデリゲートが順に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f1378-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="f1378-107">結合できるのは、同じ型のデリゲートのみです。</span><span class="sxs-lookup"><span data-stu-id="f1378-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="f1378-108">`-` 演算子を使用して、マルチキャスト デリゲートからコンポーネント デリゲートを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f1378-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1378-109">例</span><span class="sxs-lookup"><span data-stu-id="f1378-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="f1378-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1378-110">See also</span></span>

- <xref:System.MulticastDelegate>
- [<span data-ttu-id="f1378-111">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f1378-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f1378-112">イベント</span><span class="sxs-lookup"><span data-stu-id="f1378-112">Events</span></span>](../events/index.md)
