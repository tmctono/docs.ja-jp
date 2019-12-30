---
title: ローカライズされた IntelliSense ファイルをインストールする
description: Visual Studio で .NET Core プロジェクトのローカライズされた IntelliSense ファイルを使用するように開発用マシンを設定する方法について説明します。
author: mairaw
ms.author: mairaw
ms.date: 12/18/2019
ms.openlocfilehash: 98d75544ab853e75c175dd2919991b250cfaa3b0
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75436674"
---
# <a name="how-to-install-localized-intellisense-files-for-net-core"></a><span data-ttu-id="8a319-103">.NET Core のローカライズされた IntelliSense ファイルをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="8a319-103">How to install localized IntelliSense files for .NET Core</span></span>

<span data-ttu-id="8a319-104">[IntelliSense](/visualstudio/ide/using-intellisense) は、Visual Studio などのさまざまな統合開発環境 (IDE) で使用できるコード補完機能です。</span><span class="sxs-lookup"><span data-stu-id="8a319-104">[IntelliSense](/visualstudio/ide/using-intellisense) is a code-completion aid that is available in different integrated development environments (IDEs), such as Visual Studio.</span></span> <span data-ttu-id="8a319-105">既定では、.NET Core プロジェクトを開発している場合、SDK には、英語版の IntelliSense ファイルのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8a319-105">By default, when you're developing .NET Core projects, the SDK only includes the English version of the IntelliSense files.</span></span> <span data-ttu-id="8a319-106">この記事では、以下の内容について説明しています。</span><span class="sxs-lookup"><span data-stu-id="8a319-106">This article explains:</span></span>

- <span data-ttu-id="8a319-107">ローカライズ版のファイルをインストールする方法。</span><span class="sxs-lookup"><span data-stu-id="8a319-107">How to install the localized version of those files.</span></span>
- <span data-ttu-id="8a319-108">別の言語を使用するように Visual Studio のインストールを変更する方法。</span><span class="sxs-lookup"><span data-stu-id="8a319-108">How to modify the Visual Studio installation to use a different language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8a319-109">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8a319-109">Prerequisites</span></span>

- <span data-ttu-id="8a319-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) 以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="8a319-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="8a319-111">[Visual Studio 2019 バージョン 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="8a319-111">[Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or a later version.</span></span>

## <a name="download-and-install-the-localized-intellisense-files"></a><span data-ttu-id="8a319-112">ローカライズされた IntelliSense ファイルをダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="8a319-112">Download and install the localized IntelliSense files</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a319-113">この手順では、IntelliSense ファイルを .NET Core のインストール フォルダーにコピーするための管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="8a319-113">This procedure requires that you have administrator permission to copy the IntelliSense files to the .NET Core installation folder.</span></span>

1. <span data-ttu-id="8a319-114">[IntelliSense ファイルのダウンロード](https://dotnet.microsoft.com/download/dotnet-core/intellisense)のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="8a319-114">Go to the [Download IntelliSense files](https://dotnet.microsoft.com/download/dotnet-core/intellisense) page.</span></span>

1. <span data-ttu-id="8a319-115">使用したい言語とバージョンの IntelliSense ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8a319-115">Download the IntelliSense file for the language and version you'd like to use.</span></span>

1. <span data-ttu-id="8a319-116">.zip ファイルの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="8a319-116">Extract the contents of the zip file.</span></span>

1. <span data-ttu-id="8a319-117">.NET Core のインストール フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="8a319-117">Navigate to the .NET Core installation folder.</span></span> <span data-ttu-id="8a319-118">既定では *%ProgramFiles%\dotnet\packs* の下にあります。</span><span class="sxs-lookup"><span data-stu-id="8a319-118">By default, it's under *%ProgramFiles%\dotnet\packs*.</span></span>

   - <span data-ttu-id="8a319-119">IntelliSense をインストールする SDK を選択し、関連付けられているパスに移動します。</span><span class="sxs-lookup"><span data-stu-id="8a319-119">Choose which SDK you want to install the IntelliSense for, and navigate to the associated path.</span></span> <span data-ttu-id="8a319-120">次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8a319-120">You have the following options:</span></span>

      | <span data-ttu-id="8a319-121">SDK の種類</span><span class="sxs-lookup"><span data-stu-id="8a319-121">SDK type</span></span>        | <span data-ttu-id="8a319-122">パス</span><span class="sxs-lookup"><span data-stu-id="8a319-122">Path</span></span>                               |
      | --------------- | ---------------------------------- |
      | <span data-ttu-id="8a319-123">.NET Core</span><span class="sxs-lookup"><span data-stu-id="8a319-123">.NET Core</span></span>       | <span data-ttu-id="8a319-124">*Microsoft.NETCore.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="8a319-124">*Microsoft.NETCore.App.Ref*</span></span>        |
      | <span data-ttu-id="8a319-125">Windows デスクトップ</span><span class="sxs-lookup"><span data-stu-id="8a319-125">Windows Desktop</span></span> | <span data-ttu-id="8a319-126">*Microsoft.WindowsDesktop.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="8a319-126">*Microsoft.WindowsDesktop.App.Ref*</span></span> |
      | <span data-ttu-id="8a319-127">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="8a319-127">.NET Standard</span></span>   | <span data-ttu-id="8a319-128">*NETStandard.Library.Ref*</span><span class="sxs-lookup"><span data-stu-id="8a319-128">*NETStandard.Library.Ref*</span></span>          |
   
   - <span data-ttu-id="8a319-129">ローカライズされた IntelliSense をインストールするバージョンに移動します。</span><span class="sxs-lookup"><span data-stu-id="8a319-129">Navigate to the version you want to install the localized IntelliSense for.</span></span> <span data-ttu-id="8a319-130">たとえば、*3.1.0* です。</span><span class="sxs-lookup"><span data-stu-id="8a319-130">For example, *3.1.0*.</span></span>
   - <span data-ttu-id="8a319-131">*ref* フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="8a319-131">Open the *ref* folder.</span></span>
   - <span data-ttu-id="8a319-132">モニカー フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="8a319-132">Open the moniker folder.</span></span> <span data-ttu-id="8a319-133">たとえば、*netcoreapp3.1* です。</span><span class="sxs-lookup"><span data-stu-id="8a319-133">For example, *netcoreapp3.1*.</span></span>

   <span data-ttu-id="8a319-134">したがって、移動先の完全なパスは *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1* のようになります。</span><span class="sxs-lookup"><span data-stu-id="8a319-134">So, the full path that you'd navigate to would look similar to *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.</span></span>

1. <span data-ttu-id="8a319-135">開いたばかりのモニカー フォルダー内にサブフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8a319-135">Create a subfolder inside the moniker folder you just opened.</span></span> <span data-ttu-id="8a319-136">フォルダーの名前は、使用する言語を示します。</span><span class="sxs-lookup"><span data-stu-id="8a319-136">The name of the folder indicates which language you want to use.</span></span> <span data-ttu-id="8a319-137">次の表に、さまざまなオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="8a319-137">The following table specifies the different options:</span></span>

   | <span data-ttu-id="8a319-138">言語</span><span class="sxs-lookup"><span data-stu-id="8a319-138">Language</span></span>              | <span data-ttu-id="8a319-139">フォルダー名</span><span class="sxs-lookup"><span data-stu-id="8a319-139">Folder name</span></span> |
   | --------------------- | ----------- |
   | <span data-ttu-id="8a319-140">ポルトガル語 (ブラジル)</span><span class="sxs-lookup"><span data-stu-id="8a319-140">Brazilian Portuguese</span></span>  | <span data-ttu-id="8a319-141">*pt-br*</span><span class="sxs-lookup"><span data-stu-id="8a319-141">*pt-br*</span></span>     |
   | <span data-ttu-id="8a319-142">簡体中国語</span><span class="sxs-lookup"><span data-stu-id="8a319-142">Chinese (simplified)</span></span>  | <span data-ttu-id="8a319-143">*zh-hans*</span><span class="sxs-lookup"><span data-stu-id="8a319-143">*zh-hans*</span></span>   |
   | <span data-ttu-id="8a319-144">繁体中国語</span><span class="sxs-lookup"><span data-stu-id="8a319-144">Chinese (traditional)</span></span> | <span data-ttu-id="8a319-145">*zh-hant*</span><span class="sxs-lookup"><span data-stu-id="8a319-145">*zh-hant*</span></span>   |
   | <span data-ttu-id="8a319-146">フランス語</span><span class="sxs-lookup"><span data-stu-id="8a319-146">French</span></span>                | <span data-ttu-id="8a319-147">*fr*</span><span class="sxs-lookup"><span data-stu-id="8a319-147">*fr*</span></span>        |
   | <span data-ttu-id="8a319-148">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="8a319-148">German</span></span>                | <span data-ttu-id="8a319-149">*de*</span><span class="sxs-lookup"><span data-stu-id="8a319-149">*de*</span></span>        |
   | <span data-ttu-id="8a319-150">イタリア語</span><span class="sxs-lookup"><span data-stu-id="8a319-150">Italian</span></span>               | <span data-ttu-id="8a319-151">*it*</span><span class="sxs-lookup"><span data-stu-id="8a319-151">*it*</span></span>        |
   | <span data-ttu-id="8a319-152">日本語</span><span class="sxs-lookup"><span data-stu-id="8a319-152">Japanese</span></span>              | <span data-ttu-id="8a319-153">*ja*</span><span class="sxs-lookup"><span data-stu-id="8a319-153">*ja*</span></span>        |
   | <span data-ttu-id="8a319-154">韓国語</span><span class="sxs-lookup"><span data-stu-id="8a319-154">Korean</span></span>                | <span data-ttu-id="8a319-155">*ko*</span><span class="sxs-lookup"><span data-stu-id="8a319-155">*ko*</span></span>        |
   | <span data-ttu-id="8a319-156">ロシア語</span><span class="sxs-lookup"><span data-stu-id="8a319-156">Russian</span></span>               | <span data-ttu-id="8a319-157">*ru*</span><span class="sxs-lookup"><span data-stu-id="8a319-157">*ru*</span></span>        |
   | <span data-ttu-id="8a319-158">スペイン語</span><span class="sxs-lookup"><span data-stu-id="8a319-158">Spanish</span></span>               | <span data-ttu-id="8a319-159">*es*</span><span class="sxs-lookup"><span data-stu-id="8a319-159">*es*</span></span>        |

1. <span data-ttu-id="8a319-160">ステップ 3 で抽出した *.xml* ファイルをこの新しいフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="8a319-160">Copy the *.xml* files you extracted on step 3 to this new folder.</span></span> <span data-ttu-id="8a319-161">*.xml* ファイルは SDK フォルダーごとに分割されているため、ステップ 4 で選択したものと一致する SDK にコピーします。</span><span class="sxs-lookup"><span data-stu-id="8a319-161">The *.xml* files are broken down by SDK folders, so copy them to the matching SDK you chose on step 4.</span></span>

## <a name="modify-visual-studio-language"></a><span data-ttu-id="8a319-162">Visual Studio の言語を変更する</span><span class="sxs-lookup"><span data-stu-id="8a319-162">Modify Visual Studio language</span></span>

<span data-ttu-id="8a319-163">Visual Studio で IntelliSense に別の言語を使用するには、適切な言語パックをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a319-163">For Visual Studio to use a different language for IntelliSense, install the appropriate language pack.</span></span> <span data-ttu-id="8a319-164">これは[インストール時](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional)に行うことも、後から Visual Studio のインストールを変更して行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="8a319-164">This can be done [during installation](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) or at a later time by modifying the Visual Studio installation.</span></span> <span data-ttu-id="8a319-165">Visual Studio が既に選択した言語に構成されている場合は、IntelliSense のインストールの準備ができています。</span><span class="sxs-lookup"><span data-stu-id="8a319-165">If you already have Visual Studio configured to the language of your choice, your IntelliSense installation is ready.</span></span>

### <a name="install-the-language-pack"></a><span data-ttu-id="8a319-166">言語パックをインストールする</span><span class="sxs-lookup"><span data-stu-id="8a319-166">Install the language pack</span></span>

<span data-ttu-id="8a319-167">設定時に目的の言語パックをインストールしなかった場合は、次のようにして Visual Studio を更新して言語パックをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a319-167">If you didn't install the desired language pack during setup, update Visual Studio as follows to install the language pack:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a319-168">Visual Studio をインストール、更新、または変更するには、管理アクセス許可を持つアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a319-168">To install, update, or modify Visual Studio, you must log on with an account that has administrative permissions.</span></span> <span data-ttu-id="8a319-169">詳細については、「[ユーザー アクセス許可と Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a319-169">For more information, see [User permissions and Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span></span>

1. <span data-ttu-id="8a319-170">コンピューター上で Visual Studio インストーラーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="8a319-170">Find the Visual Studio Installer on your computer.</span></span>

   <span data-ttu-id="8a319-171">たとえば、Windows 10 を実行しているコンピューター上で、 **[スタート]** を選択し、**Visual Studio インストーラー**としてリスト表示される **V** の文字までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="8a319-171">For example, on a computer running Windows 10, select **Start**, and then scroll to the letter **V**, where it's listed as **Visual Studio Installer**.</span></span>

   ![Windows から Visual Studio インストーラーを開く](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > <span data-ttu-id="8a319-173">また、Visual Studio インストーラーは次の場所にもあります。</span><span class="sxs-lookup"><span data-stu-id="8a319-173">You can also find the Visual Studio Installer in the following location:</span></span>
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   <span data-ttu-id="8a319-174">続行する前に、インストーラーの更新が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8a319-174">You might have to update the installer before continuing.</span></span> <span data-ttu-id="8a319-175">その場合は、画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="8a319-175">If so, follow the prompts.</span></span>

1. <span data-ttu-id="8a319-176">インストーラーで、言語パックを追加する Visual Studio のエディションを探し、 **[変更]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a319-176">In the installer, look for the edition of Visual Studio that you want to add the language pack to, and then choose **Modify**.</span></span>

   ![Visual Studio の更新または変更](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > <span data-ttu-id="8a319-178">**[変更]** ボタンが表示されず、代わりに **[更新]** ボタンが表示されている場合は、インストールを変更する前に Visual Studio を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a319-178">If you don't see a **Modify** button but you see an **Update** one instead, you need to update your Visual Studio before you can modify your installation.</span></span>
   > <span data-ttu-id="8a319-179">更新が完了すると、 **[変更]** ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a319-179">After the update is finished, the **Modify** button should appear.</span></span>

1. <span data-ttu-id="8a319-180">**[言語パック]** タブで、インストールまたはアンインストールする言語を選択または選択解除します。</span><span class="sxs-lookup"><span data-stu-id="8a319-180">In the **Language packs** tab, select or deselect the languages you want to install or uninstall.</span></span>

   ![Visual Studio の [言語パック] タブ](./media/localized-intellisense/vs-modify-language-packs.png)

1. <span data-ttu-id="8a319-182">**[変更]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a319-182">Choose **Modify**.</span></span> <span data-ttu-id="8a319-183">更新プログラムが開始します。</span><span class="sxs-lookup"><span data-stu-id="8a319-183">The update starts.</span></span>

### <a name="modify-language-settings-in-visual-studio"></a><span data-ttu-id="8a319-184">Visual Studio の言語設定を変更する</span><span class="sxs-lookup"><span data-stu-id="8a319-184">Modify language settings in Visual Studio</span></span>

<span data-ttu-id="8a319-185">目的の言語パックをインストールしたら、別の言語を使用するように Visual Studio の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="8a319-185">Once you've installed the desired language packs, modify your Visual Studio settings to use a different language:</span></span>

1. <span data-ttu-id="8a319-186">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="8a319-186">Open Visual Studio.</span></span>

1. <span data-ttu-id="8a319-187">スタート ウィンドウで、 **[コードなしで続行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a319-187">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="8a319-188">メイン メニューで、 **[ツール]**  >  **[オプション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a319-188">On the main menu, select **Tools** > **Options**.</span></span> <span data-ttu-id="8a319-189">[オプション] ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a319-189">The Options dialog opens.</span></span>

1. <span data-ttu-id="8a319-190">**[環境]** フォルダーで、 **[国際対応の設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a319-190">Under the **Environment** folder, choose **International Settings**.</span></span>

1. <span data-ttu-id="8a319-191">**[言語]** ドロップダウンで目的の言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a319-191">On the **Language** drop-down, select the desired language.</span></span> <span data-ttu-id="8a319-192">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a319-192">Choose **OK**.</span></span> 

1. <span data-ttu-id="8a319-193">変更を有効にするために Visual Studio を再起動する必要があることを示すダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a319-193">A dialog informs you that you have to restart Visual Studio for the changes to take effect.</span></span> <span data-ttu-id="8a319-194">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a319-194">Choose **OK**.</span></span>

1. <span data-ttu-id="8a319-195">Visual Studio を再起動します。</span><span class="sxs-lookup"><span data-stu-id="8a319-195">Restart Visual Studio.</span></span>

<span data-ttu-id="8a319-196">その後、インストールした IntelliSense ファイルのバージョンを対象とする .NET Core プロジェクトを開くと、IntelliSense が期待どおりに動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="8a319-196">After this, your IntelliSense should work as expected when you open a .NET Core project that targets the version of the IntelliSense files you just installed.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a319-197">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a319-197">See also</span></span>

- [<span data-ttu-id="8a319-198">Visual Studio での IntelliSense</span><span class="sxs-lookup"><span data-stu-id="8a319-198">IntelliSense in Visual Studio</span></span>](/visualstudio/ide/using-intellisense)
