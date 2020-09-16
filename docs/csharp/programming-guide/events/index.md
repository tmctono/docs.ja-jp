---
title: イベント - C# プログラミング ガイド
description: イベントについて説明します。 クラスやオブジェクトは、何か重要なことが起こった場合に、イベントを使用して他のクラスまたはオブジェクトに通知を送ります。
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 86ded81de4b9191c50b993c08b0e87712ff69020
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545494"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="6e204-104">イベント (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="6e204-104">Events (C# Programming Guide)</span></span>
<span data-ttu-id="6e204-105">[クラス](../../language-reference/keywords/class.md) やオブジェクトは、何か重要なことが起こった場合に、イベントを使用して他のクラスまたはオブジェクトに通知を送ります。</span><span class="sxs-lookup"><span data-stu-id="6e204-105">Events enable a [class](../../language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="6e204-106">イベントを送信する ( *発生させる*) クラスを *パブリッシャー* 、イベントを受信する ( *処理する*) クラスを *サブスクライバー*と呼びます。</span><span class="sxs-lookup"><span data-stu-id="6e204-106">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
<span data-ttu-id="6e204-107">一般的な C# Windows フォームまたは Web アプリケーションでは、ボタンやリスト ボックスなどのコントロールによって発生したイベントを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="6e204-107">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="6e204-108">Visual C# 統合開発環境 (IDE) を使用して、コントロールによって発行されるイベントを参照し、処理するイベントを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6e204-108">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="6e204-109">IDE は、空のイベント ハンドラー メソッドとイベントを定期受信するためのコードを自動的に追加する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="6e204-109">The IDE provides an easy way to automatically add an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="6e204-110">詳細については、「[イベントのサブスクリプションとサブスクリプション解除を行う方法](./how-to-subscribe-to-and-unsubscribe-from-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e204-110">For more information, see [How to subscribe to and unsubscribe from events](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>
  
## <a name="events-overview"></a><span data-ttu-id="6e204-111">イベントの概要</span><span class="sxs-lookup"><span data-stu-id="6e204-111">Events Overview</span></span>  
 <span data-ttu-id="6e204-112">イベントには次のようなプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="6e204-112">Events have the following properties:</span></span>  
  
- <span data-ttu-id="6e204-113">パブリッシャーがイベントが発生するタイミングを判断し、サブスクライバーがイベントに対応して実行するアクションを決定します。</span><span class="sxs-lookup"><span data-stu-id="6e204-113">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
- <span data-ttu-id="6e204-114">イベントには複数のサブスクライバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e204-114">An event can have multiple subscribers.</span></span> <span data-ttu-id="6e204-115">サブスクライバーは、複数のパブリッシャーからの複数のイベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="6e204-115">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
- <span data-ttu-id="6e204-116">サブスクライバーがないイベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="6e204-116">Events that have no subscribers are never raised.</span></span>  
  
- <span data-ttu-id="6e204-117">イベントは一般的に、グラフィカル ユーザー インターフェイスでのボタンのクリックやメニューの選択などのユーザーの操作を知らせるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e204-117">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
- <span data-ttu-id="6e204-118">イベントに複数のサブスクライバーがある場合は、イベントが発生したときに複数のイベント ハンドラーが同時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6e204-118">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="6e204-119">イベントを非同期に呼び出すには、[同期メソッドの非同期呼び出し](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e204-119">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
- <span data-ttu-id="6e204-120">.NET クラス ライブラリでは、イベントは <xref:System.EventHandler> デリゲートおよび <xref:System.EventArgs> 基底クラスに基づきます。</span><span class="sxs-lookup"><span data-stu-id="6e204-120">In the .NET class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6e204-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e204-121">Related Sections</span></span>  
 <span data-ttu-id="6e204-122">詳細については次を参照してください:</span><span class="sxs-lookup"><span data-stu-id="6e204-122">For more information, see:</span></span>  
  
- [<span data-ttu-id="6e204-123">イベントのサブスクリプションとサブスクリプション解除を行う方法</span><span class="sxs-lookup"><span data-stu-id="6e204-123">How to subscribe to and unsubscribe from events</span></span>](./how-to-subscribe-to-and-unsubscribe-from-events.md)

- [<span data-ttu-id="6e204-124">.NET ガイドラインに準拠したイベントを発行する方法</span><span class="sxs-lookup"><span data-stu-id="6e204-124">How to publish events that conform to .NET Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)

- [<span data-ttu-id="6e204-125">派生クラスから基本クラス イベントを発生させる方法</span><span class="sxs-lookup"><span data-stu-id="6e204-125">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)

- [<span data-ttu-id="6e204-126">インターフェイス イベントを実装する方法</span><span class="sxs-lookup"><span data-stu-id="6e204-126">How to implement interface events</span></span>](./how-to-implement-interface-events.md)

- [<span data-ttu-id="6e204-127">カスタム イベント アクセサーを実装する方法</span><span class="sxs-lookup"><span data-stu-id="6e204-127">How to implement custom event accessors</span></span>](./how-to-implement-custom-event-accessors.md)

## <a name="c-language-specification"></a><span data-ttu-id="6e204-128">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="6e204-128">C# Language Specification</span></span>  

<span data-ttu-id="6e204-129">詳細については、「[C# 言語の仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の「[イベント](~/_csharplang/spec/classes.md#events)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e204-129">For more information, see [Events](~/_csharplang/spec/classes.md#events) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="6e204-130">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="6e204-130">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="6e204-131">参考書籍の該当する章</span><span class="sxs-lookup"><span data-stu-id="6e204-131">Featured Book Chapters</span></span>  
 <span data-ttu-id="6e204-132">「[Delegates, Events, and Lambda Expressions (デリゲート、イベント、およびラムダ式)](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10))」(『[C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers (C# 3.0 クックブック (第 3 版): C# 3.0 プログラマ向けの 250 以上のソリューション)](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))』)</span><span class="sxs-lookup"><span data-stu-id="6e204-132">[Delegates, Events, and Lambda Expressions](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span></span>  
  
 <span data-ttu-id="6e204-133">「[デリゲートとイベント](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10))」(『[Learning C# 3.0: Master the fundamentals of C# 3.0 (C# 3.0 の学習: C# 3.0 の基礎を習得)](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))』)</span><span class="sxs-lookup"><span data-stu-id="6e204-133">[Delegates and Events](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) in [Learning C# 3.0: Master the fundamentals of C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e204-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e204-134">See also</span></span>

- <xref:System.EventHandler>
- [<span data-ttu-id="6e204-135">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="6e204-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6e204-136">デリゲート</span><span class="sxs-lookup"><span data-stu-id="6e204-136">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="6e204-137">Windows フォーム内でのイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="6e204-137">Creating Event Handlers in Windows Forms</span></span>](/dotnet/desktop/winforms/creating-event-handlers-in-windows-forms)
