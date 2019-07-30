---
title: '方法: イベント サブスクリプションとサブスクリプションの解除 - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- event handlers [C#], creating
- Code Editor, event handlers
- events [C#], creating using the IDE
ms.assetid: 6319f39f-282c-4173-8a62-6c4657cf51cd
ms.openlocfilehash: 777eb3be5cbefe0a136bf49f826ad67685a8456d
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401076"
---
# <a name="how-to-subscribe-to-and-unsubscribe-from-events-c-programming-guide"></a><span data-ttu-id="9335d-102">方法: イベント サブスクリプションとサブスクリプションの解除 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="9335d-102">How to: Subscribe to and Unsubscribe from Events (C# Programming Guide)</span></span>
<span data-ttu-id="9335d-103">別のクラスによってパブリッシュされるイベントが発生したときに呼び出されるカスタム コードを作成するときは、そのイベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="9335d-103">You subscribe to an event that is published by another class when you want to write custom code that is called when that event is raised.</span></span> <span data-ttu-id="9335d-104">たとえば、ユーザーがボタンをクリックしたらアプリケーションで何かを行うには、ボタンの `click` イベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="9335d-104">For example, you might subscribe to a button's `click` event in order to make your application do something useful when the user clicks the button.</span></span>  
  
### <a name="to-subscribe-to-events-by-using-the-visual-studio-ide"></a><span data-ttu-id="9335d-105">Visual Studio IDE を使ってイベントをサブスクライブするには</span><span class="sxs-lookup"><span data-stu-id="9335d-105">To subscribe to events by using the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="9335d-106">**デザイン** ビューに **[プロパティ]** ウィンドウが表示されない場合は、イベント ハンドラーを作成するフォームまたはコントロールを右クリックして、 **[プロパティ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9335d-106">If you cannot see the **Properties** window, in **Design** view, right-click the form or control for which you want to create an event handler, and select **Properties**.</span></span>  
  
2. <span data-ttu-id="9335d-107">**[プロパティ]** ウィンドウの **[イベント]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9335d-107">On top of the **Properties** window, click the **Events** icon.</span></span>  
  
3. <span data-ttu-id="9335d-108">作成するイベントをダブルクリックします (`Load` イベントなど)。</span><span class="sxs-lookup"><span data-stu-id="9335d-108">Double-click the event that you want to create, for example the `Load` event.</span></span>  
  
     <span data-ttu-id="9335d-109">Visual C# によって空のイベント ハンドラー メソッドを作成され、コードに追加されます。</span><span class="sxs-lookup"><span data-stu-id="9335d-109">Visual C# creates an empty event handler method and adds it to your code.</span></span> <span data-ttu-id="9335d-110">または、**コード** ビューを使って手動でコードを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="9335d-110">Alternatively you can add the code manually in **Code** view.</span></span> <span data-ttu-id="9335d-111">たとえば、次のコード行では、`Form` クラスで `Load` イベントが発生すると呼び出されるイベント ハンドラー メソッドを宣言しています。</span><span class="sxs-lookup"><span data-stu-id="9335d-111">For example, the following lines of code declare an event handler method that will be called when the `Form` class raises the `Load` event.</span></span>  
  
     [!code-csharp[csProgGuideEvents#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#11)]  
  
     <span data-ttu-id="9335d-112">イベントをサブスクライブするために必要なコード行も、プロジェクトの Form1.Designer.cs ファイルの `InitializeComponent` メソッドに自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="9335d-112">The line of code that is required to subscribe to the event is also automatically generated in the `InitializeComponent` method in the Form1.Designer.cs file in your project.</span></span> <span data-ttu-id="9335d-113">次のようなコードです。</span><span class="sxs-lookup"><span data-stu-id="9335d-113">It resembles this:</span></span>  
  
    ```csharp
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
### <a name="to-subscribe-to-events-programmatically"></a><span data-ttu-id="9335d-114">プログラムでイベントをサブスクライブするには</span><span class="sxs-lookup"><span data-stu-id="9335d-114">To subscribe to events programmatically</span></span>  
  
1. <span data-ttu-id="9335d-115">シグネチャがイベントのデリゲート シグネチャと一致するイベント ハンドラー メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="9335d-115">Define an event handler method whose signature matches the delegate signature for the event.</span></span> <span data-ttu-id="9335d-116">たとえば、イベントが <xref:System.EventHandler> デリゲート型に基づいている場合は、次のコードがメソッド スタブを表します。</span><span class="sxs-lookup"><span data-stu-id="9335d-116">For example, if the event is based on the <xref:System.EventHandler> delegate type, the following code represents the method stub:</span></span>  
  
    ```csharp
    void HandleCustomEvent(object sender, CustomEventArgs a)  
    {  
       // Do something useful here.  
    }  
    ```  
  
2. <span data-ttu-id="9335d-117">加算代入演算子 (`+=`) を使って、イベントにイベント ハンドラーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="9335d-117">Use the addition assignment operator (`+=`) to attach an event handler to the event.</span></span> <span data-ttu-id="9335d-118">次の例では、`publisher` オブジェクトに `RaiseCustomEvent` という名前のイベントがあるものとします。</span><span class="sxs-lookup"><span data-stu-id="9335d-118">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent`.</span></span> <span data-ttu-id="9335d-119">イベントをサブスクライブするには、サブスクライバー クラスがそのパブリッシャー クラスを参照する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9335d-119">Note that the subscriber class needs a reference to the publisher class in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="9335d-120">上の構文は、C# 2.0 で新しく追加されたものです。</span><span class="sxs-lookup"><span data-stu-id="9335d-120">Note that the previous syntax is new in C# 2.0.</span></span> <span data-ttu-id="9335d-121">これは、`new` キーワードを使ってカプセル化するデリゲートを明示的に作成する必要がある C# 1.0 の構文と完全に同等です。</span><span class="sxs-lookup"><span data-stu-id="9335d-121">It is exactly equivalent to the C# 1.0 syntax in which the encapsulating delegate must be explicitly created by using the `new` keyword:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += new CustomEventHandler(HandleCustomEvent);  
    ```  
  
     <span data-ttu-id="9335d-122">また、[ラムダ式](../statements-expressions-operators/lambda-expressions.md)を使用してイベント ハンドラーを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="9335d-122">You also can use a [lambda expression](../statements-expressions-operators/lambda-expressions.md) to specify an event handler:</span></span>
  
    ```csharp
    public Form1()  
    {  
        InitializeComponent();  
        this.Click += (s,e) =>
            {
                MessageBox.Show(((MouseEventArgs)e).Location.ToString());
            };
    }  
    ```  
  
### <a name="to-subscribe-to-events-by-using-an-anonymous-method"></a><span data-ttu-id="9335d-123">匿名メソッドを使ってイベントをサブスクライブするには</span><span class="sxs-lookup"><span data-stu-id="9335d-123">To subscribe to events by using an anonymous method</span></span>  
  
- <span data-ttu-id="9335d-124">後でイベントのサブスクリプションを解除する必要がない場合は、加算代入演算子 (`+=`) を使って匿名メソッドをイベントにアタッチできます。</span><span class="sxs-lookup"><span data-stu-id="9335d-124">If you will not have to unsubscribe to an event later, you can use the addition assignment operator (`+=`) to attach an anonymous method to the event.</span></span> <span data-ttu-id="9335d-125">次の例では、`publisher` オブジェクトに `RaiseCustomEvent` という名前のイベントがあり、`CustomEventArgs` クラスもある種の特別なイベント情報を保持するように定義されているものとします。</span><span class="sxs-lookup"><span data-stu-id="9335d-125">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent` and that a `CustomEventArgs` class has also been defined to carry some kind of specialized event information.</span></span> <span data-ttu-id="9335d-126">イベントをサブスクライブするには、サブスクライバー クラスがその `publisher` クラスを参照する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9335d-126">Note that the subscriber class needs a reference to `publisher` in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += delegate(object o, CustomEventArgs e)  
    {  
      string s = o.ToString() + " " + e.ToString();  
      Console.WriteLine(s);  
    };  
    ```  
  
     <span data-ttu-id="9335d-127">匿名関数を使ってイベントをサブスクライブした場合、簡単にはイベントのサブスクリプションを解除できないことに注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="9335d-127">It is important to notice that you cannot easily unsubscribe from an event if you used an anonymous function to subscribe to it.</span></span> <span data-ttu-id="9335d-128">このシナリオでサブスクリプションを解除するには、イベントをサブスクライブするコードに戻り、匿名メソッドをデリゲート変数に格納して、イベントにデリゲートを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9335d-128">To unsubscribe in this scenario, it is necessary to go back to the code where you subscribe to the event, store the anonymous method in a delegate variable, and then add the delegate to the event.</span></span> <span data-ttu-id="9335d-129">一般に、後のコードでイベントのサブスクリプションを解除する必要がある場合は、イベントのサブスクライブに匿名関数を使わないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9335d-129">In general, we recommend that you do not use anonymous functions to subscribe to events if you will have to unsubscribe from the event at some later point in your code.</span></span> <span data-ttu-id="9335d-130">匿名関数について詳しくは、「[匿名関数](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9335d-130">For more information about anonymous functions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="unsubscribing"></a><span data-ttu-id="9335d-131">サブスクリプションの解除</span><span class="sxs-lookup"><span data-stu-id="9335d-131">Unsubscribing</span></span>  
 <span data-ttu-id="9335d-132">イベントが発生したときにイベント ハンドラーが呼び出されないようにするには、イベントからサブスクリプションを解除します。</span><span class="sxs-lookup"><span data-stu-id="9335d-132">To prevent your event handler from being invoked when the event is raised, unsubscribe from the event.</span></span> <span data-ttu-id="9335d-133">リソースのリークを防ぐには、サブスクライバー オブジェクトを破棄する前に、イベントのサブスクリプションを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9335d-133">In order to prevent resource leaks, you should unsubscribe from events before you dispose of a subscriber object.</span></span> <span data-ttu-id="9335d-134">イベントのサブスクリプションを解除するまで、パブリッシュ側オブジェクトでイベントの基盤になっているマルチキャスト デリゲートは、サブスクライバーのイベント ハンドラーをカプセル化するデリゲートへの参照を保持しています。</span><span class="sxs-lookup"><span data-stu-id="9335d-134">Until you unsubscribe from an event, the multicast delegate that underlies the event in the publishing object has a reference to the delegate that encapsulates the subscriber's event handler.</span></span> <span data-ttu-id="9335d-135">パブリッシュ側オブジェクトがその参照を保持している限り、ガベージ コレクションはサブスクライバー オブジェクトを削除しません。</span><span class="sxs-lookup"><span data-stu-id="9335d-135">As long as the publishing object holds that reference, garbage collection will not delete your subscriber object.</span></span>  
  
#### <a name="to-unsubscribe-from-an-event"></a><span data-ttu-id="9335d-136">イベントのサブスクリプションを解除するには</span><span class="sxs-lookup"><span data-stu-id="9335d-136">To unsubscribe from an event</span></span>  
  
- <span data-ttu-id="9335d-137">イベントのサブスクリプションを解除するには、減算代入演算子 (`-=`) を使います。</span><span class="sxs-lookup"><span data-stu-id="9335d-137">Use the subtraction assignment operator (`-=`) to unsubscribe from an event:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent -= HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="9335d-138">すべてのサブスクライバーがイベントのサブスクリプションを解除すると、パブリッシャー クラスのイベント インスタンスは `null` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9335d-138">When all subscribers have unsubscribed from an event, the event instance in the publisher class is set to `null`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9335d-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="9335d-139">See also</span></span>

- [<span data-ttu-id="9335d-140">イベント</span><span class="sxs-lookup"><span data-stu-id="9335d-140">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="9335d-141">event</span><span class="sxs-lookup"><span data-stu-id="9335d-141">event</span></span>](../../../csharp/language-reference/keywords/event.md)
- [<span data-ttu-id="9335d-142">方法: .NET Framework ガイドラインに準拠したイベントを発行する</span><span class="sxs-lookup"><span data-stu-id="9335d-142">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)
- [<span data-ttu-id="9335d-143">- および -= 演算子</span><span class="sxs-lookup"><span data-stu-id="9335d-143">- and -= operators</span></span>](../../language-reference/operators/subtraction-operator.md)
- [<span data-ttu-id="9335d-144">+ および += 演算子</span><span class="sxs-lookup"><span data-stu-id="9335d-144">+ and += operators</span></span>](../../language-reference/operators/addition-operator.md)
