---
title: イベント - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 183f53a579bdd9f70deb16ca9157c377fa3aff3f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "75712313"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="ed5b1-102">イベント (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="ed5b1-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="ed5b1-103">[クラス](../../language-reference/keywords/class.md) やオブジェクトは、何か重要なことが起こった場合に、イベントを使用して他のクラスまたはオブジェクトに通知を送ります。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-103">Events enable a [class](../../language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="ed5b1-104">イベントを送信する ( *発生させる*) クラスを *パブリッシャー* 、イベントを受信する ( *処理する*) クラスを *サブスクライバー*と呼びます。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
<span data-ttu-id="ed5b1-105">一般的な C# Windows フォームまたは Web アプリケーションでは、ボタンやリスト ボックスなどのコントロールによって発生したイベントを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="ed5b1-106">Visual C# 統合開発環境 (IDE) を使用して、コントロールによって発行されるイベントを参照し、処理するイベントを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-106">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="ed5b1-107">IDE は、空のイベント ハンドラー メソッドとイベントを定期受信するためのコードを自動的に追加する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-107">The IDE provides an easy way to automatically add an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="ed5b1-108">詳細については、「[イベントのサブスクリプションとサブスクリプション解除を行う方法](./how-to-subscribe-to-and-unsubscribe-from-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-108">For more information, see [How to subscribe to and unsubscribe from events](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>
  
## <a name="events-overview"></a><span data-ttu-id="ed5b1-109">イベントの概要</span><span class="sxs-lookup"><span data-stu-id="ed5b1-109">Events Overview</span></span>  
 <span data-ttu-id="ed5b1-110">イベントには次のようなプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-110">Events have the following properties:</span></span>  
  
- <span data-ttu-id="ed5b1-111">パブリッシャーがイベントが発生するタイミングを判断し、サブスクライバーがイベントに対応して実行するアクションを決定します。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
- <span data-ttu-id="ed5b1-112">イベントには複数のサブスクライバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="ed5b1-113">サブスクライバーは、複数のパブリッシャーからの複数のイベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
- <span data-ttu-id="ed5b1-114">サブスクライバーがないイベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-114">Events that have no subscribers are never raised.</span></span>  
  
- <span data-ttu-id="ed5b1-115">イベントは一般的に、グラフィカル ユーザー インターフェイスでのボタンのクリックやメニューの選択などのユーザーの操作を知らせるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
- <span data-ttu-id="ed5b1-116">イベントに複数のサブスクライバーがある場合は、イベントが発生したときに複数のイベント ハンドラーが同時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="ed5b1-117">イベントを非同期に呼び出すには、[同期メソッドの非同期呼び出し](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
- <span data-ttu-id="ed5b1-118">.NET Framework クラス ライブラリ以内で、イベントは、<xref:System.EventHandler> デリゲートおよび <xref:System.EventArgs> 基底クラスを基にしています。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-118">In the .NET Framework class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ed5b1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed5b1-119">Related Sections</span></span>  
 <span data-ttu-id="ed5b1-120">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="ed5b1-120">For more information, see:</span></span>  
  
- [<span data-ttu-id="ed5b1-121">イベントのサブスクリプションとサブスクリプション解除を行う方法</span><span class="sxs-lookup"><span data-stu-id="ed5b1-121">How to subscribe to and unsubscribe from events</span></span>](./how-to-subscribe-to-and-unsubscribe-from-events.md)

- [<span data-ttu-id="ed5b1-122">.NET Framework ガイドラインに準拠したイベントを発行する方法</span><span class="sxs-lookup"><span data-stu-id="ed5b1-122">How to publish events that conform to .NET Framework Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)

- [<span data-ttu-id="ed5b1-123">派生クラスから基本クラス イベントを発生させる方法</span><span class="sxs-lookup"><span data-stu-id="ed5b1-123">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)

- [<span data-ttu-id="ed5b1-124">インターフェイス イベントを実装する方法</span><span class="sxs-lookup"><span data-stu-id="ed5b1-124">How to implement interface events</span></span>](./how-to-implement-interface-events.md)

- [<span data-ttu-id="ed5b1-125">カスタム イベント アクセサーを実装する方法</span><span class="sxs-lookup"><span data-stu-id="ed5b1-125">How to implement custom event accessors</span></span>](./how-to-implement-custom-event-accessors.md)

## <a name="c-language-specification"></a><span data-ttu-id="ed5b1-126">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="ed5b1-126">C# Language Specification</span></span>  

<span data-ttu-id="ed5b1-127">詳細については、「[C# 言語の仕様](~/_csharplang/spec/classes.md#events)」の「[イベント](/dotnet/csharp/language-reference/language-specification/introduction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-127">For more information, see [Events](~/_csharplang/spec/classes.md#events) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="ed5b1-128">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="ed5b1-128">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="ed5b1-129">参考書籍の該当する章</span><span class="sxs-lookup"><span data-stu-id="ed5b1-129">Featured Book Chapters</span></span>  
 <span data-ttu-id="ed5b1-130">『 [Delegates, Events, and Lambda Expressions (デリゲート、イベント、およびラムダ式) (C# 3.0 クックブック (第 3 版): C# 3.0 プログラマ向けの 250 以上のソリューション)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) 』の「 [Delegates, Events, and Lambda Expressions (デリゲート、イベント、およびラムダ式)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29) 」</span><span class="sxs-lookup"><span data-stu-id="ed5b1-130">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
 <span data-ttu-id="ed5b1-131">「[Learn」の「g C# 3.0: Master the Fundamentals of C# 3.0 (C# 3.0 の学習: C# 3.0 の基礎を習得)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) 」の「 [Learn」の「g C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)」</span><span class="sxs-lookup"><span data-stu-id="ed5b1-131">[Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed5b1-132">参照</span><span class="sxs-lookup"><span data-stu-id="ed5b1-132">See also</span></span>

- <xref:System.EventHandler>
- [<span data-ttu-id="ed5b1-133">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="ed5b1-133">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ed5b1-134">デリゲート</span><span class="sxs-lookup"><span data-stu-id="ed5b1-134">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="ed5b1-135">Windows フォーム内のイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="ed5b1-135">Creating Event Handlers in Windows Forms</span></span>](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
