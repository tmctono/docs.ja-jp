---
title: Visual Studio での System.windows.controls.inkcanvas> の作成
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: b8087d6db04f7024b9ee48f28002bee04045a14b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737888"
---
# <a name="get-started-with-ink-in-wpf"></a><span data-ttu-id="07805-102">WPF でインクを使ってみる</span><span class="sxs-lookup"><span data-stu-id="07805-102">Get Started with Ink in WPF</span></span>

<span data-ttu-id="07805-103">Windows Presentation Foundation (WPF) には、デジタルインクをアプリに簡単に組み込むことができるインク機能があります。</span><span class="sxs-lookup"><span data-stu-id="07805-103">Windows Presentation Foundation (WPF) has an ink feature that makes it easy to incorporate digital ink into your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="07805-104">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="07805-104">Prerequisites</span></span>

<span data-ttu-id="07805-105">次の例を使用するには、最初に[Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="07805-105">To use the following examples, first install [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span></span> <span data-ttu-id="07805-106">また、基本的な WPF アプリの記述方法を理解するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="07805-106">It also helps to know how to write basic WPF apps.</span></span> <span data-ttu-id="07805-107">WPF の概要については、「[チュートリアル: 初めての wpf デスクトップアプリケーション](../getting-started/walkthrough-my-first-wpf-desktop-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07805-107">For help getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="quick-start"></a><span data-ttu-id="07805-108">クイック スタート</span><span class="sxs-lookup"><span data-stu-id="07805-108">Quick Start</span></span>

<span data-ttu-id="07805-109">このセクションでは、インクを収集する単純な WPF アプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07805-109">This section helps you write a simple WPF application that collects ink.</span></span>

### <a name="got-ink"></a><span data-ttu-id="07805-110">インクを持っていますか?</span><span class="sxs-lookup"><span data-stu-id="07805-110">Got Ink?</span></span>

<span data-ttu-id="07805-111">インクをサポートする WPF アプリを作成するには:</span><span class="sxs-lookup"><span data-stu-id="07805-111">To create a WPF app that supports ink:</span></span>

1. <span data-ttu-id="07805-112">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="07805-112">Open Visual Studio.</span></span>

2. <span data-ttu-id="07805-113">新しい**WPF アプリ**を作成します。</span><span class="sxs-lookup"><span data-stu-id="07805-113">Create a new **WPF App**.</span></span>

   <span data-ttu-id="07805-114">**[新しいプロジェクト]** ダイアログで、[**インストールされている** > **ビジュアルC#**  ] または [ **Visual Basic** > **Windows デスクトップ**] カテゴリを展開します。</span><span class="sxs-lookup"><span data-stu-id="07805-114">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="07805-115">次に、 **[WPF アプリ (.NET Framework)]** アプリテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="07805-115">Then, select the **WPF App (.NET Framework)** app template.</span></span> <span data-ttu-id="07805-116">名前を入力し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="07805-116">Enter a name, and then select **OK**.</span></span>

   <span data-ttu-id="07805-117">Visual Studio によってプロジェクトが作成され、 *mainwindow.xaml*がデザイナーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="07805-117">Visual Studio creates the project, and *MainWindow.xaml* opens in the designer.</span></span>

3. <span data-ttu-id="07805-118">`<Grid>` タグ間の `<InkCanvas/>` を入力します。</span><span class="sxs-lookup"><span data-stu-id="07805-118">Type `<InkCanvas/>` between the `<Grid>` tags.</span></span>

   ![System.windows.controls.inkcanvas> タグを持つ XAML デザイナー](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. <span data-ttu-id="07805-120">**F5**キーを押して、デバッガーでアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="07805-120">Press **F5** to launch your application in the debugger.</span></span>

5. <span data-ttu-id="07805-121">スタイラスまたはマウスを使用して、ウィンドウに**hello world**と記述します。</span><span class="sxs-lookup"><span data-stu-id="07805-121">Using a stylus or mouse, write **hello world** in the window.</span></span>

<span data-ttu-id="07805-122">"Hello world" アプリケーションに相当するインクを12個のキーストロークだけで記述しました。</span><span class="sxs-lookup"><span data-stu-id="07805-122">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>

### <a name="spice-up-your-app"></a><span data-ttu-id="07805-123">アプリをスパイスする</span><span class="sxs-lookup"><span data-stu-id="07805-123">Spice Up Your App</span></span>

<span data-ttu-id="07805-124">WPF の一部の機能を活用してみましょう。</span><span class="sxs-lookup"><span data-stu-id="07805-124">Let’s take advantage of some features of the WPF.</span></span> <span data-ttu-id="07805-125">\<ウィンドウの開始と終了の間にあるすべての要素 > タグを次のマークアップに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="07805-125">Replace everything between the opening and closing \<Window> tags with the following markup:</span></span>

```xaml
<Page>
  <InkCanvas Name="myInkCanvas" MouseRightButtonUp="RightMouseUpHandler">
    <InkCanvas.Background>
      <LinearGradientBrush>
        <GradientStop Color="Yellow" Offset="0.0" />
          <GradientStop Color="Blue" Offset="0.5" />
            <GradientStop Color="HotPink" Offset="1.0" />
              </LinearGradientBrush>
    </InkCanvas.Background>
  </InkCanvas>
</Page>
```

<span data-ttu-id="07805-126">この XAML は、インク描画サーフェイスにグラデーションブラシの背景を作成します。</span><span class="sxs-lookup"><span data-stu-id="07805-126">This XAML creates a gradient brush background on your inking surface.</span></span>

![WPF アプリでのインク描画画面のグラデーションの色](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a><span data-ttu-id="07805-128">XAML の背後にコードを追加する</span><span class="sxs-lookup"><span data-stu-id="07805-128">Add Some Code Behind the XAML</span></span>

<span data-ttu-id="07805-129">XAML を使用すると、ユーザーインターフェイスを簡単にデザインできますが、実際のアプリケーションでは、イベントを処理するコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07805-129">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="07805-130">マウスからの右クリックに応じてインクを拡大する簡単な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="07805-130">Here is a simple example that zooms in on the ink in response to a right-click from a mouse.</span></span>

1. <span data-ttu-id="07805-131">XAML で `MouseRightButtonUp` ハンドラーを設定します。</span><span class="sxs-lookup"><span data-stu-id="07805-131">Set the `MouseRightButtonUp` handler in your XAML:</span></span>

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. <span data-ttu-id="07805-132">**ソリューションエクスプローラー**で、mainwindow.xaml を展開し、分離コードファイル (MainWindow.xaml.cs または mainwindow.xaml) を開きます。</span><span class="sxs-lookup"><span data-stu-id="07805-132">In **Solution Explorer**, expand MainWindow.xaml and open the code-behind file (MainWindow.xaml.cs or MainWindow.xaml.vb).</span></span> <span data-ttu-id="07805-133">次のイベントハンドラーコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="07805-133">Add the following event handler code:</span></span>

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. <span data-ttu-id="07805-134">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="07805-134">Run the application.</span></span> <span data-ttu-id="07805-135">インクをいくつか追加し、マウスで右クリックするか、またはスタイラスを使用してプレスアンドホールドと同等の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="07805-135">Add some ink, and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>

   <span data-ttu-id="07805-136">マウスの右ボタンをクリックするたびに、画面がズームされます。</span><span class="sxs-lookup"><span data-stu-id="07805-136">The display zooms in each time you click with the right mouse button.</span></span>

### <a name="use-procedural-code-instead-of-xaml"></a><span data-ttu-id="07805-137">XAML ではなく手続き型コードを使用する</span><span class="sxs-lookup"><span data-stu-id="07805-137">Use Procedural Code Instead of XAML</span></span>

<span data-ttu-id="07805-138">すべての WPF 機能には、手続き型コードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="07805-138">You can access all WPF features from procedural code.</span></span> <span data-ttu-id="07805-139">次の手順に従って、XAML をまったく使用しない "Hello Ink World" アプリケーションを WPF に作成します。</span><span class="sxs-lookup"><span data-stu-id="07805-139">Follow these steps to create a "Hello Ink World" application for WPF that doesn’t use any XAML at all.</span></span>

1. <span data-ttu-id="07805-140">Visual Studio で新しいコンソールアプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="07805-140">Create a new console application project in Visual Studio.</span></span>

   <span data-ttu-id="07805-141">**[新しいプロジェクト]** ダイアログで、[**インストールされている** > **ビジュアルC#**  ] または [ **Visual Basic** > **Windows デスクトップ**] カテゴリを展開します。</span><span class="sxs-lookup"><span data-stu-id="07805-141">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="07805-142">次に、 **[コンソールアプリ (.NET Framework)]** アプリテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="07805-142">Then, select the **Console App (.NET Framework)** app template.</span></span> <span data-ttu-id="07805-143">名前を入力し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="07805-143">Enter a name, and then select **OK**.</span></span>

1. <span data-ttu-id="07805-144">Program.cs ファイルまたは .vb ファイルに次のコードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="07805-144">Paste the following code into the Program.cs or Program.vb file:</span></span>

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. <span data-ttu-id="07805-145">**ソリューションエクスプローラー**の**参照**を右クリックし、 **[参照の追加]** を選択して、プレゼンテーションコア、プレゼンテーションフレームワーク、および windowsbase アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="07805-145">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies by right-clicking on **References** in **Solution Explorer** and choosing **Add Reference**.</span></span>

   ![プレゼンテーションコアとプレゼンテーションフレームワークを示すリファレンスマネージャー](./media/getting-started-with-ink/reference-manager-presentationcore-presentationframework.png)

1. <span data-ttu-id="07805-147">**F5**キーを押してアプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="07805-147">Build the application by pressing **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="07805-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="07805-148">See also</span></span>

- [<span data-ttu-id="07805-149">デジタル インク</span><span class="sxs-lookup"><span data-stu-id="07805-149">Digital Ink</span></span>](digital-ink.md)
- [<span data-ttu-id="07805-150">インクの収集</span><span class="sxs-lookup"><span data-stu-id="07805-150">Collecting Ink</span></span>](collecting-ink.md)
- [<span data-ttu-id="07805-151">手書き認識</span><span class="sxs-lookup"><span data-stu-id="07805-151">Handwriting Recognition</span></span>](handwriting-recognition.md)
- [<span data-ttu-id="07805-152">インクの格納</span><span class="sxs-lookup"><span data-stu-id="07805-152">Storing Ink</span></span>](storing-ink.md)
