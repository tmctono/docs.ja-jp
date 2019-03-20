---
title: '方法 : ディクショナリを使用してイベント インスタンスを格納する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 03/11/2019
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: f8522e499887398402f63c7788bbc6c6c4f57782
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2019
ms.locfileid: "57845276"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="1507c-102">方法 : ディクショナリを使用してイベント インスタンスを格納する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="1507c-102">How to: use a dictionary to store event instances (C# Programming Guide)</span></span>

<span data-ttu-id="1507c-103">`add` および `remove` カスタム イベント アクセサーの 1 つの用途は、各イベントにフィールドを割り当てることなく多数のイベントを公開することですが、代わりに、次の例に示すように、<xref:System.Collections.Generic.Dictionary%602> インスタンスを使用してイベント インスタンスを格納します。</span><span class="sxs-lookup"><span data-stu-id="1507c-103">One use for the `add` and `remove` custom event accessors is to expose many events without allocating a field for each event, but instead using a <xref:System.Collections.Generic.Dictionary%602> instance to store the event instances, as the example below demonstrates.</span></span> <span data-ttu-id="1507c-104">これが便利なのは、ある型に多数のイベントがあるが、ほとんどのイベントがサブスクライブされないことが予期される場合だけです。</span><span class="sxs-lookup"><span data-stu-id="1507c-104">This is only useful if a type has many events, but you expect that most of the events will not be subscribed to.</span></span>

[!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]

<span data-ttu-id="1507c-105">この実装は、C# 言語仕様の[デリゲートの追加と削除](~/_csharplang/spec/delegates.md#delegate-invocation)のための動作に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="1507c-105">This implementation conforms to the behavior for [adding and removing delegates](~/_csharplang/spec/delegates.md#delegate-invocation) in the C# language specification.</span></span>

<span data-ttu-id="1507c-106">[lock](../../language-reference/keywords/lock-statement.md) ステートメントは、イベント ハンドラーを使用してディクショナリに "*アクセスする*" ためにのみ使用されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1507c-106">Note that the [lock](../../language-reference/keywords/lock-statement.md) statement is used only to *access* the dictionary with event handlers.</span></span> <span data-ttu-id="1507c-107">デッドロックまたはロックの競合が発生する可能性があるため、`lock` ステートメントの本文でイベント ハンドラーを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="1507c-107">Don't invoke an event handler inside the body of the `lock` statement, as it could lead to deadlocks or lock contention.</span></span>

## <a name="see-also"></a><span data-ttu-id="1507c-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="1507c-108">See also</span></span>

- [<span data-ttu-id="1507c-109">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="1507c-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="1507c-110">イベント</span><span class="sxs-lookup"><span data-stu-id="1507c-110">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="1507c-111">デリゲート</span><span class="sxs-lookup"><span data-stu-id="1507c-111">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
