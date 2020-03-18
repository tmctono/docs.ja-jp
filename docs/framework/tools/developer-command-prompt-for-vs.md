---
title: Visual Studio 用開発者コマンド プロンプト
ms.date: 01/05/2020
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
ms.openlocfilehash: f028281d477284acf3ac4dac63f5ddbbd79f5259
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "75715843"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="e89a8-102">Visual Studio 用開発者コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="e89a8-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="e89a8-103">Visual Studio 用開発者コマンド プロンプトでは、.NET Framework ツールをもっと簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e89a8-103">Developer Command Prompt for Visual Studio enables you to use .NET Framework tools more easily.</span></span> <span data-ttu-id="e89a8-104">それは、特定の環境変数を自動的に設定するコマンド プロンプトです。</span><span class="sxs-lookup"><span data-stu-id="e89a8-104">It's a command prompt that automatically sets specific environment variables.</span></span> <span data-ttu-id="e89a8-105">開発者コマンド プロンプトを開いた後、`ildasm` や `clrver` などの [.NET Framework ツール](index.md)のコマンドを入力できます。</span><span class="sxs-lookup"><span data-stu-id="e89a8-105">After opening Developer Command Prompt, you can enter the commands for [.NET Framework tools](index.md) such as `ildasm` or `clrver`.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e89a8-106">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e89a8-106">Prerequisites</span></span>

- [<span data-ttu-id="e89a8-107">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e89a8-107">Visual Studio 2019</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="e89a8-108">コンピューター上でのコマンド プロンプトの検索</span><span class="sxs-lookup"><span data-stu-id="e89a8-108">Search for the command prompt on your machine</span></span>

<span data-ttu-id="e89a8-109">Visual Studio のバージョンと、インストールした追加の SDK およびワークロードに応じて、複数のコマンド プロンプトがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e89a8-109">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs and workloads you've installed.</span></span> <span data-ttu-id="e89a8-110">次の手順でうまくいかない場合は、[マシン上のファイルを手動で探す](#manually-locate-the-files-on-your-machine)か、[Visual Studio 内からコマンド プロンプトを開始](#start-the-command-prompt-from-inside-visual-studio)してみることができます。</span><span class="sxs-lookup"><span data-stu-id="e89a8-110">If the following steps don't work, you can try to [manually locate the files on your machine](#manually-locate-the-files-on-your-machine) or [start the command prompt from inside Visual Studio](#start-the-command-prompt-from-inside-visual-studio).</span></span>

### <a name="windows-10"></a><span data-ttu-id="e89a8-111">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e89a8-111">Windows 10</span></span>

1. <span data-ttu-id="e89a8-112">**スタート** ![キーボードの Windows ロゴ キー](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)を選択し、</span><span class="sxs-lookup"><span data-stu-id="e89a8-112">Select **Start** ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="e89a8-113">文字 **V** までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="e89a8-113">and scroll to the letter **V**.</span></span>

1. <span data-ttu-id="e89a8-114">**[Visual Studio 2019]** フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-114">Expand the **Visual Studio 2019** folder.</span></span>

1. <span data-ttu-id="e89a8-115">**VS 2019 用開発者コマンド プロンプト** (または、使用するコマンド プロンプト) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-115">Choose **Developer Command Prompt for VS 2019** (or the command prompt you want to use).</span></span>

   <span data-ttu-id="e89a8-116">また、最初にタスク バーの [検索] ボックスにコマンド プロンプトの名前を入力することもできます。その名前と一致するコマンド プロンプトが結果一覧に表示されたら、その中から必要なものを選択します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-116">Alternatively, you can start typing the name of the command prompt in the search box on the taskbar, and choose the result you want as the result list starts to display the search matches.</span></span>

   ![Windows 10 での検索動作を示すアニメーション GIF](./media/developer-command-prompt-for-vs/windows10-search.gif)

### <a name="windows-81"></a><span data-ttu-id="e89a8-118">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="e89a8-118">Windows 8.1</span></span>

1. <span data-ttu-id="e89a8-119">キーボードの Windows ロゴ キー ![キーボードの Windows ロゴ キー](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png) を押すなどして、 **[スタート]** 画面に</span><span class="sxs-lookup"><span data-stu-id="e89a8-119">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="e89a8-120">移動します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-120">on your keyboard for example.</span></span>

1. <span data-ttu-id="e89a8-121">**[スタート]** 画面で、**Ctrl**+**Tab** キーを押して **[アプリ]** の一覧を開き、**V** を押します。インストールされているすべての Visual Studio コマンド プロンプトが含まれた一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e89a8-121">On the **Start** screen, press **Ctrl**+**Tab** to open the **Apps** list, and then press **V**. This brings up a list that includes all installed Visual Studio command prompts.</span></span>

1. <span data-ttu-id="e89a8-122">**VS 2019 用開発者コマンド プロンプト** (または、使用するコマンド プロンプト) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-122">Choose **Developer Command Prompt for VS 2019** (or the command prompt you want to use).</span></span>

### <a name="windows-7"></a><span data-ttu-id="e89a8-123">Windows 7</span><span class="sxs-lookup"><span data-stu-id="e89a8-123">Windows 7</span></span>

1. <span data-ttu-id="e89a8-124">**[スタート]** を選択し、 **[すべてのプログラム]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-124">Choose **Start** and then expand **All Programs**.</span></span>

1. <span data-ttu-id="e89a8-125">**[Visual Studio 2019]**  >  **[Visual Studio Tools]**  > **VS 2019 用開発者コマンド プロンプト**、または使用するコマンド プロンプトを選択します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-125">Choose **Visual Studio 2019** > **Visual Studio Tools** > **Developer Command Prompt for VS 2019**, or the command prompt you want to use.</span></span>

   ![コマンド プロンプトが強調表示されている Windows 7 の [スタート] メニュー](./media/developer-command-prompt-for-vs/windows7-menu.png)

<span data-ttu-id="e89a8-127">[Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) や[それ以前のバージョン](https://developer.microsoft.com/windows/downloads/sdk-archive)など、他の SDK がインストールされている場合は、コマンド プロンプトがさらに表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="e89a8-127">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts.</span></span> <span data-ttu-id="e89a8-128">各ツールのドキュメントを参照して、どのバージョンのコマンド プロンプトを使用する必要があるかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e89a8-128">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="e89a8-129">コンピューター上のファイルを手動で探す</span><span class="sxs-lookup"><span data-stu-id="e89a8-129">Manually locate the files on your machine</span></span>

<span data-ttu-id="e89a8-130">インストール済みのコマンド プロンプトのショートカットは、通常、Visual Studio 用の **スタート メニュー** フォルダー ( *%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2019\Visual Studio Tools* 内など) にあります。</span><span class="sxs-lookup"><span data-stu-id="e89a8-130">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in *%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2019\Visual Studio Tools*.</span></span> <span data-ttu-id="e89a8-131">ただし、コマンド プロンプトを探しても、何らかの理由によって期待した結果を生成されない場合は、コンピューター上でそのショートカットを手動で探すことができます。</span><span class="sxs-lookup"><span data-stu-id="e89a8-131">But if, for some reason, searching for the command prompt doesn't produce the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="e89a8-132">*VsDevCmd.bat* などのコマンド プロンプトのファイル名を検索するか、または Tools フォルダー ( *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\Community\Common7\Tools* など) に移動します (パスは、Visual Studio のバージョン、エディション、およびインストール先に応じて変わります)。</span><span class="sxs-lookup"><span data-stu-id="e89a8-132">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder, such as *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\Community\Common7\Tools* (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="start-the-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="e89a8-133">Visual Studio 内からコマンド プロンプトを開始する</span><span class="sxs-lookup"><span data-stu-id="e89a8-133">Start the command prompt from inside Visual Studio</span></span>

<span data-ttu-id="e89a8-134">簡単にアクセスできるように、開発者コマンド プロンプトまたは他のコマンド プロンプトを Visual Studio の [ツール] メニューに追加できます。</span><span class="sxs-lookup"><span data-stu-id="e89a8-134">For easier access, you can add Developer Command Prompt, or any other command prompt, to the Tools menu in Visual Studio.</span></span> <span data-ttu-id="e89a8-135">ツールを使用できるようにするには、外部ツール一覧にそれを追加します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-135">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="e89a8-136">次に手順を示します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-136">Here are the steps:</span></span>

1. <span data-ttu-id="e89a8-137">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="e89a8-137">Open Visual Studio.</span></span>

1. <span data-ttu-id="e89a8-138">スタート ウィンドウで、 **[コードなしで続行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-138">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="e89a8-139">メニュー バーで **[ツール]**  >  **[外部ツール]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-139">On the menu bar, choose **Tools** > **External Tools**.</span></span>

1. <span data-ttu-id="e89a8-140">**[外部ツール]** ダイアログ ボックスで、 **[追加]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e89a8-140">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="e89a8-141">新しいエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e89a8-141">A new entry appears.</span></span>

1. <span data-ttu-id="e89a8-142">新しいメニュー項目の **[タイトル]** を入力します (「`Command Prompt`」など)。</span><span class="sxs-lookup"><span data-stu-id="e89a8-142">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

1. <span data-ttu-id="e89a8-143">**[コマンド]** フィールドに、起動するファイル (`%comspec%` や `C:\Windows\System32\cmd.exe` など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-143">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

1. <span data-ttu-id="e89a8-144">**[引数]** フィールドに、使用する特定のコマンド プロンプトのある場所を指定します (`/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"` など)。</span><span class="sxs-lookup"><span data-stu-id="e89a8-144">In the **Arguments** field, specify where to find the specific command prompt you want to use, such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"`.</span></span> <span data-ttu-id="e89a8-145">このコマンドによって、Visual Studio 2019 Community でインストールされた開発者コマンド プロンプトが起動します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-145">This command launches the Developer Command Prompt that's installed with Visual Studio 2019 Community.</span></span> <span data-ttu-id="e89a8-146">この値は、Visual Studio のバージョン、エディション、インストール先に応じて変更します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-146">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

1. <span data-ttu-id="e89a8-147">**[初期ディレクトリ]** フィールドで、コマンド プロンプトが開始するディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-147">In the **Initial directory** field, specify the directory in which the command prompt will start.</span></span> <span data-ttu-id="e89a8-148">フィールドの横にある矢印を選択して、 **[プロジェクト ディレクトリ]** などの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-148">Choose a value such as **Project Directory** by selecting the arrow next to the field.</span></span>

1. <span data-ttu-id="e89a8-149">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e89a8-149">Choose the **OK** button.</span></span>

   ![フィールドに値が入力された [外部ツール] ダイアログ。](./media/developer-command-prompt-for-vs/add-external-tool.png)

   <span data-ttu-id="e89a8-151">新しいメニュー項目が追加され、このコマンド プロンプトに [ツール] メニューからアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="e89a8-151">The new menu item is added, and you can access the command prompt from the Tools menu.</span></span>

   ![Visual Studio でのコマンド プロンプト メニュー項目](./media/developer-command-prompt-for-vs/command-prompt-vs-menu.png)

## <a name="see-also"></a><span data-ttu-id="e89a8-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="e89a8-153">See also</span></span>

- [<span data-ttu-id="e89a8-154">.NET Framework ツール</span><span class="sxs-lookup"><span data-stu-id="e89a8-154">.NET Framework Tools</span></span>](index.md)
- [<span data-ttu-id="e89a8-155">Visual Studio の外部ツール</span><span class="sxs-lookup"><span data-stu-id="e89a8-155">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
- [<span data-ttu-id="e89a8-156">コマンド ラインから Microsoft C++ ツールセットを使用する</span><span class="sxs-lookup"><span data-stu-id="e89a8-156">Use the Microsoft C++ toolset from the command line</span></span>](/cpp/build/building-on-the-command-line)
