---
title: カスタム イベント アクセサーを実装する方法 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
ms.openlocfilehash: 34e816799f472e8945962e334b9a90b2582e0393
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705354"
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a><span data-ttu-id="f0a40-102">カスタム イベント アクセサーを実装する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="f0a40-102">How to implement custom event accessors (C# Programming Guide)</span></span>
<span data-ttu-id="f0a40-103">イベントは、宣言元のクラス内でしか呼び出せない特殊なマルチキャスト デリゲートです。</span><span class="sxs-lookup"><span data-stu-id="f0a40-103">An event is a special kind of multicast delegate that can only be invoked from within the class that  it is declared in.</span></span> <span data-ttu-id="f0a40-104">クライアント コードは、イベント発生時に呼び出されるメソッドへの参照を提供することにより、イベントにサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="f0a40-104">Client code subscribes to the event by providing a reference to a method that should be invoked when the event is fired.</span></span> <span data-ttu-id="f0a40-105">これらのメソッドは、イベント アクセサーを使用してデリゲートの呼び出しリストに追加されます。イベント アクセサーはプロパティ アクセサーに似ていますが、イベント アクセサーには `add` および `remove` という名前が付いている点が異なります。</span><span class="sxs-lookup"><span data-stu-id="f0a40-105">These methods are added to the delegate's invocation list through event accessors, which resemble property accessors, except that event accessors are named `add` and `remove`.</span></span> <span data-ttu-id="f0a40-106">ほとんどの場合、カスタム イベント アクセサーを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f0a40-106">In most cases, you do not have to supply custom event accessors.</span></span> <span data-ttu-id="f0a40-107">コードでカスタム イベント アクセサーを指定していない場合は、コンパイラによって自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f0a40-107">When no custom event accessors are supplied in your code, the compiler will add them automatically.</span></span> <span data-ttu-id="f0a40-108">ただし、カスタム動作の指定が必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="f0a40-108">However, in some cases you may have to provide custom behavior.</span></span> <span data-ttu-id="f0a40-109">「[インターフェイス イベントを実装する方法](./how-to-implement-interface-events.md)」トピックは、そのような場合の一例を示しています。</span><span class="sxs-lookup"><span data-stu-id="f0a40-109">One such case is shown in the topic [How to implement interface events](./how-to-implement-interface-events.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="f0a40-110">例</span><span class="sxs-lookup"><span data-stu-id="f0a40-110">Example</span></span>  
 <span data-ttu-id="f0a40-111">次の例は、カスタム イベント アクセサーの add と remove を実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f0a40-111">The following example shows how to implement custom add and remove event accessors.</span></span> <span data-ttu-id="f0a40-112">アクセサー内で任意のコードに置き換えることができますが、新しいイベント ハンドラー メソッドを追加または削除する前に、イベントをロックすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f0a40-112">Although you can substitute any code inside the accessors, we recommend that you lock the event before you add or remove a new event handler method.</span></span>  
  
[!code-csharp[IDrawingObject.OnDraw](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a><span data-ttu-id="f0a40-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0a40-113">See also</span></span>

- [<span data-ttu-id="f0a40-114">イベント</span><span class="sxs-lookup"><span data-stu-id="f0a40-114">Events</span></span>](./index.md)
- [<span data-ttu-id="f0a40-115">event</span><span class="sxs-lookup"><span data-stu-id="f0a40-115">event</span></span>](../../language-reference/keywords/event.md)
