---
title: カスタム イベント アクセサーを実装する方法 - C# プログラミング ガイド
description: カスタム イベント アクセサーを実装する方法について説明します。 コード例を参照し、使用可能なその他のリソースを確認します。
ms.date: 07/20/2015
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
ms.openlocfilehash: 4094aa1fedbceb68790b484608b3ea0ebc1e5cf6
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302140"
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a><span data-ttu-id="4035a-104">カスタム イベント アクセサーを実装する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="4035a-104">How to implement custom event accessors (C# Programming Guide)</span></span>
<span data-ttu-id="4035a-105">イベントは、宣言元のクラス内でしか呼び出せない特殊なマルチキャスト デリゲートです。</span><span class="sxs-lookup"><span data-stu-id="4035a-105">An event is a special kind of multicast delegate that can only be invoked from within the class that  it is declared in.</span></span> <span data-ttu-id="4035a-106">クライアント コードは、イベント発生時に呼び出されるメソッドへの参照を提供することにより、イベントにサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="4035a-106">Client code subscribes to the event by providing a reference to a method that should be invoked when the event is fired.</span></span> <span data-ttu-id="4035a-107">これらのメソッドは、イベント アクセサーを使用してデリゲートの呼び出しリストに追加されます。イベント アクセサーはプロパティ アクセサーに似ていますが、イベント アクセサーには `add` および `remove` という名前が付いている点が異なります。</span><span class="sxs-lookup"><span data-stu-id="4035a-107">These methods are added to the delegate's invocation list through event accessors, which resemble property accessors, except that event accessors are named `add` and `remove`.</span></span> <span data-ttu-id="4035a-108">ほとんどの場合、カスタム イベント アクセサーを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4035a-108">In most cases, you do not have to supply custom event accessors.</span></span> <span data-ttu-id="4035a-109">コードでカスタム イベント アクセサーを指定していない場合は、コンパイラによって自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="4035a-109">When no custom event accessors are supplied in your code, the compiler will add them automatically.</span></span> <span data-ttu-id="4035a-110">ただし、カスタム動作の指定が必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="4035a-110">However, in some cases you may have to provide custom behavior.</span></span> <span data-ttu-id="4035a-111">「[インターフェイス イベントを実装する方法](./how-to-implement-interface-events.md)」トピックは、そのような場合の一例を示しています。</span><span class="sxs-lookup"><span data-stu-id="4035a-111">One such case is shown in the topic [How to implement interface events](./how-to-implement-interface-events.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="4035a-112">例</span><span class="sxs-lookup"><span data-stu-id="4035a-112">Example</span></span>  
 <span data-ttu-id="4035a-113">次の例は、カスタム イベント アクセサーの add と remove を実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4035a-113">The following example shows how to implement custom add and remove event accessors.</span></span> <span data-ttu-id="4035a-114">アクセサー内で任意のコードに置き換えることができますが、新しいイベント ハンドラー メソッドを追加または削除する前に、イベントをロックすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4035a-114">Although you can substitute any code inside the accessors, we recommend that you lock the event before you add or remove a new event handler method.</span></span>  
  
[!code-csharp[IDrawingObject.OnDraw](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a><span data-ttu-id="4035a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4035a-115">See also</span></span>

- [<span data-ttu-id="4035a-116">イベント</span><span class="sxs-lookup"><span data-stu-id="4035a-116">Events</span></span>](./index.md)
- [<span data-ttu-id="4035a-117">event</span><span class="sxs-lookup"><span data-stu-id="4035a-117">event</span></span>](../../language-reference/keywords/event.md)
