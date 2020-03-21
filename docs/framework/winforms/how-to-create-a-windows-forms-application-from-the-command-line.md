---
title: コマンド ラインから Windows フォーム アプリケーションを作成する
titleSuffix: ''
ms.date: 03/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
ms.openlocfilehash: 7bd3add526a6b60d628b05d46eca22ce407c36b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181985"
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a><span data-ttu-id="5184e-102">方法: コマンド ラインから Windows フォーム アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="5184e-102">How to: Create a Windows Forms application from the command line</span></span>

<span data-ttu-id="5184e-103">次の手順では、コマンドラインから Windows フォーム アプリケーションを作成して実行するために完了する必要のある基本的な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="5184e-103">The following procedures describe the basic steps that you must complete to create and run a Windows Forms application from the command line.</span></span> <span data-ttu-id="5184e-104">Visual Studio では、これらの手順に対する広範なサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5184e-104">There is extensive support for these procedures in Visual Studio.</span></span>  <span data-ttu-id="5184e-105">[チュートリアル: WPF で Windows フォーム コントロールをホスト](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5184e-105">Also see [Walkthrough: Hosting a Windows Forms Control in WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>
  
## <a name="procedure"></a><span data-ttu-id="5184e-106">手順</span><span class="sxs-lookup"><span data-stu-id="5184e-106">Procedure</span></span>  
  
#### <a name="to-create-the-form"></a><span data-ttu-id="5184e-107">フォームを作成するには</span><span class="sxs-lookup"><span data-stu-id="5184e-107">To create the form</span></span>  
  
1. <span data-ttu-id="5184e-108">空のコード ファイルに、次`Imports`のステートメント`using`を入力します。</span><span class="sxs-lookup"><span data-stu-id="5184e-108">In an empty code file, type the following `Imports` or `using` statements:</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2. <span data-ttu-id="5184e-109">Form クラスから`Form1`継承するクラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="5184e-109">Declare a class named `Form1` that inherits from the Form class:</span></span>
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3. <span data-ttu-id="5184e-110">のパラメーターなしのコンストラクターを`Form1`作成します。</span><span class="sxs-lookup"><span data-stu-id="5184e-110">Create a parameterless constructor for `Form1`.</span></span>
  
     <span data-ttu-id="5184e-111">後続の手順で、コンストラクターにさらにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5184e-111">You will add more code to the constructor in a subsequent procedure.</span></span>
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4. <span data-ttu-id="5184e-112">`Main` メソッドをクラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="5184e-112">Add a `Main` method to the class.</span></span>
  
    1. <span data-ttu-id="5184e-113"><xref:System.STAThreadAttribute> Windows フォーム アプリケーションを`Main`指定する C# メソッドにを適用するシングルスレッド アパートメントです。</span><span class="sxs-lookup"><span data-stu-id="5184e-113">Apply the <xref:System.STAThreadAttribute> to the C# `Main` method to specify your Windows Forms application is a single-threaded apartment.</span></span> <span data-ttu-id="5184e-114">(Visual Basic で開発された Windows フォーム アプリケーションは既定でシングル スレッド アパートメント モデルを使用するため、この属性は必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="5184e-114">(The attribute is not necessary in Visual Basic, since Windows forms applications developed with Visual Basic use a single-threaded apartment model by default.)</span></span>  
  
    2. <span data-ttu-id="5184e-115">アプリケーション<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>にオペレーティング システム スタイルを適用する呼び出し。</span><span class="sxs-lookup"><span data-stu-id="5184e-115">Call <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> to apply operating system styles to your application.</span></span>  
  
    3. <span data-ttu-id="5184e-116">フォームのインスタンスを作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="5184e-116">Create an instance of the form and run it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a><span data-ttu-id="5184e-117">アプリケーションをコンパイルして実行するには</span><span class="sxs-lookup"><span data-stu-id="5184e-117">To compile and run the application</span></span>  
  
1. <span data-ttu-id="5184e-118">.NET Framework コマンド プロンプトで、`Form1` クラスを作成したディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="5184e-118">At the .NET Framework command prompt, navigate to the directory you created the `Form1` class.</span></span>  
  
2. <span data-ttu-id="5184e-119">フォームをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="5184e-119">Compile the form.</span></span>  
  
    - <span data-ttu-id="5184e-120">C# を使用している場合は、次のように入力します。`csc form1.cs`</span><span class="sxs-lookup"><span data-stu-id="5184e-120">If you are using C#, type: `csc form1.cs`</span></span>  
  
         `-or-`  
  
    - <span data-ttu-id="5184e-121">Visual Basic を使用している場合は、次のように入力します。`vbc form1.vb`</span><span class="sxs-lookup"><span data-stu-id="5184e-121">If you are using Visual Basic, type: `vbc form1.vb`</span></span>  
  
3. <span data-ttu-id="5184e-122">コマンド プロンプトに `Form1.exe` を入力します。</span><span class="sxs-lookup"><span data-stu-id="5184e-122">At the command prompt, type: `Form1.exe`</span></span>  
  
## <a name="adding-a-control-and-handling-an-event"></a><span data-ttu-id="5184e-123">コントロールの追加とイベントの処理</span><span class="sxs-lookup"><span data-stu-id="5184e-123">Adding a control and handling an event</span></span>

<span data-ttu-id="5184e-124">前の手順は、コンパイルして実行する基本的な Windows フォームを作成する方法を示しました。</span><span class="sxs-lookup"><span data-stu-id="5184e-124">The previous procedure steps demonstrated how to just create a basic Windows Form that compiles and runs.</span></span> <span data-ttu-id="5184e-125">次の手順では、コントロールを作成してフォームに追加し、コントロールのイベントを処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5184e-125">The next procedure will show you how to create and add a control to the form, and handle an event for the control.</span></span> <span data-ttu-id="5184e-126">Windows フォームに追加できるコントロールの詳細については、「 Windows[フォーム コントロール](./controls/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5184e-126">For more information about the controls you can add to Windows Forms, see [Windows Forms Controls](./controls/index.md).</span></span>
  
 <span data-ttu-id="5184e-127">Windows フォーム アプリケーションを作成する方法を理解するだけでなく、イベント ベースのプログラミングとユーザー入力を処理する方法を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5184e-127">In addition to understanding how to create Windows Forms applications, you should understand event-based programming and how to handle user input.</span></span> <span data-ttu-id="5184e-128">詳細については、「 [Windows フォームでのイベント ハンドラの作成](creating-event-handlers-in-windows-forms.md)」および「[ユーザー入力の処理](./controls/handling-user-input.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5184e-128">For more information, see [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md), and [Handling User Input](./controls/handling-user-input.md)</span></span>  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a><span data-ttu-id="5184e-129">ボタン コントロールを宣言して、クリック イベントを処理するには</span><span class="sxs-lookup"><span data-stu-id="5184e-129">To declare a button control and handle its click event</span></span>  
  
1. <span data-ttu-id="5184e-130">`button1` という名前のボタン コントロールを宣言します。</span><span class="sxs-lookup"><span data-stu-id="5184e-130">Declare a button control named `button1`.</span></span>  
  
2. <span data-ttu-id="5184e-131">コンストラクターでボタンを作成し、<xref:System.Windows.Forms.Control.Size%2A>、<xref:System.Windows.Forms.Control.Location%2A>、および <xref:System.Windows.Forms.Control.Text%2A> の各プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5184e-131">In the constructor, create the button and set its <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Text%2A> properties.</span></span>  
  
3. <span data-ttu-id="5184e-132">フォームにボタンを追加します。</span><span class="sxs-lookup"><span data-stu-id="5184e-132">Add the button to the form.</span></span>  
  
     <span data-ttu-id="5184e-133">ボタン コントロールを宣言する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="5184e-133">The following code example demonstrates how to declare the button control:</span></span>
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4. <span data-ttu-id="5184e-134">ボタンで <xref:System.Windows.Forms.Control.Click> イベントを処理するメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="5184e-134">Create a method to handle the <xref:System.Windows.Forms.Control.Click> event for the button.</span></span>  
  
5. <span data-ttu-id="5184e-135">クリック イベント ハンドラーで、メッセージ "Hello World" と共に <xref:System.Windows.Forms.MessageBox> を表示します。</span><span class="sxs-lookup"><span data-stu-id="5184e-135">In the click event handler, display a <xref:System.Windows.Forms.MessageBox> with the message, "Hello World".</span></span>  
  
     <span data-ttu-id="5184e-136">ボタン コントロールのクリック イベントを処理する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="5184e-136">The following code example demonstrates how to handle the button control's click event:</span></span>
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6. <span data-ttu-id="5184e-137"><xref:System.Windows.Forms.Control.Click> イベントを作成したメソッドに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="5184e-137">Associate the <xref:System.Windows.Forms.Control.Click> event with the method you created.</span></span>  
  
     <span data-ttu-id="5184e-138">次のコード例は、イベントをメソッドに関連付ける方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5184e-138">The following code example demonstrates how to associate the event with the method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7. <span data-ttu-id="5184e-139">前の手順で説明したように、アプリケーションをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="5184e-139">Compile and run the application as described in the previous procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5184e-140">例</span><span class="sxs-lookup"><span data-stu-id="5184e-140">Example</span></span>  

<span data-ttu-id="5184e-141">次のコード例は、前の手順の完全な例です。</span><span class="sxs-lookup"><span data-stu-id="5184e-141">The following code example is the complete example from the previous procedures:</span></span>
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5184e-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="5184e-142">See also</span></span>

- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Control>
- [<span data-ttu-id="5184e-143">Windows フォームの表示形式の変更</span><span class="sxs-lookup"><span data-stu-id="5184e-143">Changing the Appearance of Windows Forms</span></span>](changing-the-appearance-of-windows-forms.md)
- [<span data-ttu-id="5184e-144">Windows フォーム アプリケーションの拡張</span><span class="sxs-lookup"><span data-stu-id="5184e-144">Enhancing Windows Forms Applications</span></span>](./advanced/index.md)
- [<span data-ttu-id="5184e-145">Windows フォームについて</span><span class="sxs-lookup"><span data-stu-id="5184e-145">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
