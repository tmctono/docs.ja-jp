---
title: RaiseEvent ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: e04f2bbaf57789f0bdaa07c1ebd68b22e3ae6178
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333058"
---
# <a name="raiseevent-statement"></a><span data-ttu-id="434f6-102">RaiseEvent ステートメント</span><span class="sxs-lookup"><span data-stu-id="434f6-102">RaiseEvent Statement</span></span>
<span data-ttu-id="434f6-103">クラス、フォーム、またはドキュメント内のモジュール レベルで宣言されたイベントをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="434f6-103">Triggers an event declared at module level within a class, form, or document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="434f6-104">構文</span><span class="sxs-lookup"><span data-stu-id="434f6-104">Syntax</span></span>  
  
```vb  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a><span data-ttu-id="434f6-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="434f6-105">Parts</span></span>  
 `eventname`  
 <span data-ttu-id="434f6-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="434f6-106">Required.</span></span> <span data-ttu-id="434f6-107">トリガーするイベントの名前です。</span><span class="sxs-lookup"><span data-stu-id="434f6-107">Name of the event to trigger.</span></span>  
  
 `argumentlist`  
 <span data-ttu-id="434f6-108">任意。</span><span class="sxs-lookup"><span data-stu-id="434f6-108">Optional.</span></span> <span data-ttu-id="434f6-109">変数、配列、または式のコンマ区切りのリストです。</span><span class="sxs-lookup"><span data-stu-id="434f6-109">Comma-delimited list of variables, arrays, or expressions.</span></span> <span data-ttu-id="434f6-110">`argumentlist` 引数はかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="434f6-110">The `argumentlist` argument must be enclosed by parentheses.</span></span> <span data-ttu-id="434f6-111">引数がない場合は、かっこを省略する必要があります。</span><span class="sxs-lookup"><span data-stu-id="434f6-111">If there are no arguments, the parentheses must be omitted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="434f6-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="434f6-112">Remarks</span></span>  
 <span data-ttu-id="434f6-113">必須の `eventname` は、モジュール内で宣言されたイベントの名前です。</span><span class="sxs-lookup"><span data-stu-id="434f6-113">The required `eventname` is the name of an event declared within the module.</span></span> <span data-ttu-id="434f6-114">Visual Basic 変数の名前付け規則に従います。</span><span class="sxs-lookup"><span data-stu-id="434f6-114">It follows Visual Basic variable naming conventions.</span></span>  
  
 <span data-ttu-id="434f6-115">イベントが発生するモジュール内でそれが宣言されていない場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="434f6-115">If the event has not been declared within the module in which it is raised, an error occurs.</span></span> <span data-ttu-id="434f6-116">次のコード フラグメントは、イベントの宣言と、イベントが発生するプロシージャを示しています。</span><span class="sxs-lookup"><span data-stu-id="434f6-116">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span></span>  
  
 [!code-vb[VbVbalrEvents#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#37)]  
  
 <span data-ttu-id="434f6-117">モジュール内で明示的に宣言されていないイベントを、`RaiseEvent` を使用して発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="434f6-117">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span></span> <span data-ttu-id="434f6-118">たとえば、すべてのフォームが <xref:System.Windows.Forms.Form?displayProperty=nameWithType> から <xref:System.Windows.Forms.Control.Click> イベントを継承している場合、それを派生フォーム内の `RaiseEvent` を使用して発生させることはできません。</span><span class="sxs-lookup"><span data-stu-id="434f6-118">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, it cannot be raised using `RaiseEvent` in a derived form.</span></span> <span data-ttu-id="434f6-119">フォーム モジュール内で `Click` イベントを宣言すると、それによってフォーム独自の <xref:System.Windows.Forms.Control.Click> イベントはシャドウされます。</span><span class="sxs-lookup"><span data-stu-id="434f6-119">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="434f6-120">それでも、そのフォームの <xref:System.Windows.Forms.Control.Click> イベントは、<xref:System.Windows.Forms.Control.OnClick%2A> メソッドを呼び出すことで呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="434f6-120">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="434f6-121">既定では、Visual Basic で定義されたイベントはそのイベント ハンドラーを、接続が確立された順に発生させます。</span><span class="sxs-lookup"><span data-stu-id="434f6-121">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span></span> <span data-ttu-id="434f6-122">イベントには `ByRef` パラメーターを含めることができるため、遅れて接続するプロセスでは、先行するイベント ハンドラーによって変更されたパラメーターを受け取る場合があります。</span><span class="sxs-lookup"><span data-stu-id="434f6-122">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span></span> <span data-ttu-id="434f6-123">イベント ハンドラーが実行されると、イベントを発生させたサブルーチンに制御が返されます。</span><span class="sxs-lookup"><span data-stu-id="434f6-123">After the event handlers execute, control is returned to the subroutine that raised the event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="434f6-124">非共有イベントは、それらが宣言されているクラスのコンストラクター内で発生させないでください。</span><span class="sxs-lookup"><span data-stu-id="434f6-124">Non-shared events should not be raised within the constructor of the class in which they are declared.</span></span> <span data-ttu-id="434f6-125">このようなイベントが実行時エラーの原因となることはありませんが、関連付けられたイベント ハンドラーでキャッチされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="434f6-125">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span></span> <span data-ttu-id="434f6-126">コンストラクターからイベントを発生させる必要がある場合は、`Shared` 修飾子を使用して共有イベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="434f6-126">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="434f6-127">イベントの既定の動作を変更するには、カスタム イベントを定義します。</span><span class="sxs-lookup"><span data-stu-id="434f6-127">You can change the default behavior of events by defining a custom event.</span></span> <span data-ttu-id="434f6-128">カスタム イベントの場合は、`RaiseEvent` ステートメントによってイベントの `RaiseEvent` アクセサーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="434f6-128">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span></span> <span data-ttu-id="434f6-129">カスタム イベントの詳細については、「[Event ステートメント](../../../visual-basic/language-reference/statements/event-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="434f6-129">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="434f6-130">例</span><span class="sxs-lookup"><span data-stu-id="434f6-130">Example</span></span>  
 <span data-ttu-id="434f6-131">次の例では、イベントを使用して 10 秒から 0 秒までカウント ダウンします。</span><span class="sxs-lookup"><span data-stu-id="434f6-131">The following example uses events to count down seconds from 10 to 0.</span></span> <span data-ttu-id="434f6-132">このコードは、イベント関連のいくつかのメソッド、プロパティ、およびステートメント (`RaiseEvent` など) の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="434f6-132">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span></span>  
  
 <span data-ttu-id="434f6-133">イベントを発生させるクラスをイベント ソース、イベントを処理するメソッドをイベント ハンドラーと呼びます。</span><span class="sxs-lookup"><span data-stu-id="434f6-133">The class that raises an event is the event source, and the methods that process the event are the event handlers.</span></span> <span data-ttu-id="434f6-134">イベント ソースでは、生成されるイベントに対して複数のイベント ハンドラーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="434f6-134">An event source can have multiple handlers for the events it generates.</span></span> <span data-ttu-id="434f6-135">クラスでイベントが発生すると、そのイベントは、オブジェクトのインスタンスに対するイベントを処理するために選択されたすべてのクラスで発生します。</span><span class="sxs-lookup"><span data-stu-id="434f6-135">When the class raises the event, that event is raised on every class that has elected to handle events for that instance of the object.</span></span>  
  
 <span data-ttu-id="434f6-136">また、この例では、ボタン (`Button1`) とテキスト ボックス (`TextBox1`) を含んだフォーム (`Form1`) も使用しています。</span><span class="sxs-lookup"><span data-stu-id="434f6-136">The example also uses a form (`Form1`) with a button (`Button1`) and a text box (`TextBox1`).</span></span> <span data-ttu-id="434f6-137">ボタンをクリックすると、1 つ目のテキスト ボックスに 10 秒から 0 秒までのカウントダウンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="434f6-137">When you click the button, the first text box displays a countdown from 10 to 0 seconds.</span></span> <span data-ttu-id="434f6-138">カウントダウンが終わると (10 秒が経過すると)、1 つ目のテキスト ボックスに "Done" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="434f6-138">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
 <span data-ttu-id="434f6-139">`Form1` のコードでは、フォームの初期状態と終了状態を指定しています。</span><span class="sxs-lookup"><span data-stu-id="434f6-139">The code for `Form1` specifies the initial and terminal states of the form.</span></span> <span data-ttu-id="434f6-140">イベント発生時に実行されるコードも含まれています。</span><span class="sxs-lookup"><span data-stu-id="434f6-140">It also contains the code executed when events are raised.</span></span>  
  
 <span data-ttu-id="434f6-141">この例を使用するには、新しい Windows アプリケーション プロジェクトを開き、`Button1` という名前のボタンと、`TextBox1` という名前のテキスト ボックスを、`Form1` という名前のメイン フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="434f6-141">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span></span> <span data-ttu-id="434f6-142">続いてフォームを右クリックし、 **[コードの表示]** をクリックしてコード エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="434f6-142">Then right-click the form and click **View Code** to open the Code Editor.</span></span>  
  
 <span data-ttu-id="434f6-143">`Form1` クラスの宣言セクションに、`WithEvents` 変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="434f6-143">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span></span>  
  
 [!code-vb[VbVbalrEvents#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="434f6-144">例</span><span class="sxs-lookup"><span data-stu-id="434f6-144">Example</span></span>  
 <span data-ttu-id="434f6-145">`Form1` のコードに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="434f6-145">Add the following code to the code for `Form1`.</span></span> <span data-ttu-id="434f6-146">`Form_Load` や `Button_Click` など、重複して存在する可能性のあるプロシージャを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="434f6-146">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span></span>  
  
 [!code-vb[VbVbalrEvents#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#15)]  
  
 <span data-ttu-id="434f6-147">F5 キーを押して上の例を実行し、**Start** というラベルのボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="434f6-147">Press F5 to run the preceding example, and click the button labeled **Start**.</span></span> <span data-ttu-id="434f6-148">最初のテキスト ボックスで、秒のカウント ダウンが開始されます。</span><span class="sxs-lookup"><span data-stu-id="434f6-148">The first text box starts to count down the seconds.</span></span> <span data-ttu-id="434f6-149">カウントダウンが終わると (10 秒が経過すると)、1 つ目のテキスト ボックスに "Done" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="434f6-149">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="434f6-150">`My.Application.DoEvents` メソッドがイベントを処理する方法は、フォームによる方法とは一部異なります。</span><span class="sxs-lookup"><span data-stu-id="434f6-150">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="434f6-151">フォームでイベントを直接処理できるようにするには、マルチスレッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="434f6-151">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="434f6-152">詳細については、「[マネージド スレッド処理](../../../standard/threading/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="434f6-152">For more information, see [Managed Threading](../../../standard/threading/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="434f6-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="434f6-153">See also</span></span>

- [<span data-ttu-id="434f6-154">イベント</span><span class="sxs-lookup"><span data-stu-id="434f6-154">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="434f6-155">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="434f6-155">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="434f6-156">AddHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="434f6-156">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="434f6-157">RemoveHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="434f6-157">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="434f6-158">Handles</span><span class="sxs-lookup"><span data-stu-id="434f6-158">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
