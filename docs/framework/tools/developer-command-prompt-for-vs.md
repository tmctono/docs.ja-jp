---
title: Visual Studio 用開発者コマンド プロンプト
ms.date: 08/14/2018
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cc88106a54a00b4b12e5043da7961791a98102c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344365"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="3e1d7-102">Visual Studio 用開発者コマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="3e1d7-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="3e1d7-103">Visual Studio 用開発者コマンド プロンプトでは、.NET Framework ツールをもっと簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-103">The Developer Command Prompt for Visual Studio enables you to use .NET Framework tools more easily.</span></span> <span data-ttu-id="3e1d7-104">それは、特定の環境変数を自動的に設定するコマンド プロンプトです。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-104">It is a command prompt that automatically sets specific environment variables.</span></span>

> [!div class="button"]
> [<span data-ttu-id="3e1d7-105">Visual Studio のダウンロード</span><span class="sxs-lookup"><span data-stu-id="3e1d7-105">Download Visual Studio</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="3e1d7-106">コンピューター上でのコマンド プロンプトの検索</span><span class="sxs-lookup"><span data-stu-id="3e1d7-106">Search for the command prompt on your machine</span></span>

<span data-ttu-id="3e1d7-107">Visual Studio のバージョンと、インストールした追加の SDK に応じて、複数のコマンド プロンプトがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-107">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="3e1d7-108">たとえば、Visual Studio の 64 ビット バージョンには、32 ビットと 64 ビットのコマンド プロンプトが用意されています</span><span class="sxs-lookup"><span data-stu-id="3e1d7-108">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="3e1d7-109">(ほとんどのツールでは、32 ビット バージョンと 64 ビット バージョンに違いはありませんが、一部のツールでは、32 ビット環境と 64 ビット環境に固有の変更が加えられています)。次の手順でうまくいかない場合は、「[コンピューター上のファイルを手動で探す](#manually-locate-the-files-on-your-machine)」または「[Visual Studio 内からコマンド プロンプトを実行する](#run-the-command-prompt-from-inside-visual-studio)」を試してください。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-109">(The 32-bit and 64-bit versions of most tools are the same; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the following steps don't work, you can try [Manually locate the files on your machine](#manually-locate-the-files-on-your-machine) or [Run the command prompt from inside Visual Studio](#run-the-command-prompt-from-inside-visual-studio).</span></span>

### <a name="in-windows-10"></a><span data-ttu-id="3e1d7-110">Windows 10 の場合</span><span class="sxs-lookup"><span data-stu-id="3e1d7-110">In Windows 10</span></span>

1. <span data-ttu-id="3e1d7-111">タスクバーの検索ボックスに、`dev` や `developer command prompt` など、ツールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-111">In the search box on the taskbar, start typing the name of the tool, such as `dev` or `developer command prompt`.</span></span> <span data-ttu-id="3e1d7-112">検索パターンに一致する、インストールされているアプリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-112">This brings up a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="3e1d7-113">別のコマンド プロンプトを探す場合は、別の検索語句 (「`prompt`」など) を入力してください。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-113">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>

2. <span data-ttu-id="3e1d7-114">**Visual Studio 用開発者コマンド プロンプト** (または、使用するコマンド プロンプト) を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-114">Choose the **Developer Command Prompt for Visual Studio** (or the command prompt you want to use).</span></span>

### <a name="in-windows-81"></a><span data-ttu-id="3e1d7-115">Windows 8.1 の場合</span><span class="sxs-lookup"><span data-stu-id="3e1d7-115">In Windows 8.1</span></span>

1. <span data-ttu-id="3e1d7-116">キーボードの Windows ロゴ キー ![Windows ロゴ](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") を押すなどして、**[スタート]** 画面に移動します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-116">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="3e1d7-117">**[スタート]** 画面で、**Ctrl**+**Tab** キーを押して **[アプリ]** の一覧を開き、`V`.と入力します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-117">On the **Start** screen, press **Ctrl**+**Tab** to open the **Apps** list, and then enter `V`.</span></span> <span data-ttu-id="3e1d7-118">インストールされているすべての Visual Studio コマンド プロンプトが含まれた一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-118">This brings a list that includes all installed Visual Studio command prompts.</span></span>

3. <span data-ttu-id="3e1d7-119">**[開発者コマンド プロンプト]** (または、使用するコマンド プロンプト) を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-119">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-8"></a><span data-ttu-id="3e1d7-120">Windows 8 の場合</span><span class="sxs-lookup"><span data-stu-id="3e1d7-120">In Windows 8</span></span>

1. <span data-ttu-id="3e1d7-121">キーボードの Windows ロゴ キー ![Windows ロゴ](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") を押すなどして、**[スタート]** 画面に移動します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-121">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="3e1d7-122">**[スタート]** 画面で、Windows ロゴ キー ![Windows ロゴ](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z` を押します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-122">On the **Start** screen, press the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>

3. <span data-ttu-id="3e1d7-123">画面下部にある**アプリ ビュー** アイコンを選択し、「`V`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-123">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="3e1d7-124">インストールされているすべての Visual Studio コマンド プロンプトが含まれた一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-124">This brings a list that includes all installed Visual Studio command prompts.</span></span>

4. <span data-ttu-id="3e1d7-125">**[開発者コマンド プロンプト]** (または、使用するコマンド プロンプト) を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-125">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-7"></a><span data-ttu-id="3e1d7-126">Windows 7 の場合</span><span class="sxs-lookup"><span data-stu-id="3e1d7-126">In Windows 7</span></span>

1. <span data-ttu-id="3e1d7-127">**[スタート]** を選択し、**[すべてのプログラム]**、**[Microsoft Visual Studio]** の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-127">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>

2. <span data-ttu-id="3e1d7-128">インストールされている Visual Studio のバージョンに応じて、**[Visual Studio Tools]**、**[Visual Studio コマンド プロンプト]**、または使用するコマンド プロンプトを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-128">Depending on the version of Visual Studio you've installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>

<span data-ttu-id="3e1d7-129">[Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) や[それ以前のバージョン](https://developer.microsoft.com/windows/downloads/sdk-archive)など、他の SDK をインストールしている場合、ARM、x86、または x64 の各アーキテクチャ用のコマンド プロンプトがさらに表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-129">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="3e1d7-130">各ツールのドキュメントを参照して、どのバージョンのコマンド プロンプトを使用する必要があるかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-130">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="3e1d7-131">コンピューター上のファイルを手動で探す</span><span class="sxs-lookup"><span data-stu-id="3e1d7-131">Manually locate the files on your machine</span></span>

<span data-ttu-id="3e1d7-132">インストール済みのコマンド プロンプトのショートカットは、通常 Visual Studio の **[スタート] メニュー**用のフォルダー (C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools 内など) にあります。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-132">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span></span> <span data-ttu-id="3e1d7-133">ただし、コマンド プロンプトを探しても、何らかの理由によって期待した結果を得られない場合は、コンピューター上でそのショートカットを手動で探すことができます。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-133">But if for some reason, searching for the command prompt doesn't bring the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="3e1d7-134">*VsDevCmd.bat* などのコマンド プロンプトのファイル名を検索するか、または Tools フォルダー (C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools など) に移動します (パスは、Visual Studio のバージョン、エディション、およびインストール先に応じて変わります)。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-134">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="run-the-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="3e1d7-135">Visual Studio 内からコマンド プロンプトを実行する</span><span class="sxs-lookup"><span data-stu-id="3e1d7-135">Run the command prompt from inside Visual Studio</span></span>

<span data-ttu-id="3e1d7-136">簡単にアクセスできるように、Visual Studio の開発者コマンド プロンプトまたは他のコマンド プロンプトを Visual Studio の **[ツール]** メニューに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-136">For easier access, you can add the Visual Studio Developer Command Prompt, or any other command prompt, to the **Tools** menu in Visual Studio.</span></span> <span data-ttu-id="3e1d7-137">ツールを使用できるようにするには、外部ツール一覧にそれを追加します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-137">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="3e1d7-138">次に手順を示します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-138">Here are the steps:</span></span>

1. <span data-ttu-id="3e1d7-139">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-139">Open Visual Studio.</span></span>

2. <span data-ttu-id="3e1d7-140">**[ツール]** メニューを選択し、**[外部ツール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-140">Select the **Tools** menu, and then choose **External Tools**.</span></span>

3. <span data-ttu-id="3e1d7-141">**[外部ツール]** ダイアログ ボックスで、**[追加]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-141">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="3e1d7-142">新しいエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-142">A new entry appears.</span></span>

4. <span data-ttu-id="3e1d7-143">新しいメニュー項目の **[タイトル]** を入力します (「`Command Prompt`」など)。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-143">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

5. <span data-ttu-id="3e1d7-144">**[コマンド]** フィールドに、起動するファイル (`%comspec%` や `C:\Windows\System32\cmd.exe` など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-144">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

6. <span data-ttu-id="3e1d7-145">**[引数]** フィールドに、使用する特定のコマンド プロンプトのある場所を指定します (`/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` など。このコマンドでは、Visual Studio 2017 Enterprise でインストールされた開発者コマンド プロンプトが起動されます)。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-145">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (this command launches the Developer Command Prompt that is installed with Visual Studio 2017 Enterprise).</span></span> <span data-ttu-id="3e1d7-146">この値は、Visual Studio のバージョン、エディション、インストール先に応じて変更します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-146">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

7. <span data-ttu-id="3e1d7-147">**[初期ディレクトリ]** フィールドの値 (**[プロジェクト ディレクトリ]** など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-147">Choose a value for the **Initial directory** field, such as **Project Directory**.</span></span>

8. <span data-ttu-id="3e1d7-148">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-148">Choose the **OK** button.</span></span>

   <span data-ttu-id="3e1d7-149">新しいメニュー項目が追加され、このコマンド プロンプトに **[ツール]** メニューからアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="3e1d7-149">The new menu item is added, and you can access the command prompt from the **Tools** menu.</span></span>

   ![Visual Studio でのコマンド プロンプト メニュー項目](media/command-prompt-vs-menu.png)

## <a name="see-also"></a><span data-ttu-id="3e1d7-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e1d7-151">See also</span></span>

- [<span data-ttu-id="3e1d7-152">ツール</span><span class="sxs-lookup"><span data-stu-id="3e1d7-152">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="3e1d7-153">Visual Studio の外部ツール</span><span class="sxs-lookup"><span data-stu-id="3e1d7-153">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
