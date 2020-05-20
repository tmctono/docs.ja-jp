---
title: ローカライズされた IntelliSense ファイルをインストールする
description: Visual Studio で .NET Core プロジェクトのローカライズされた IntelliSense ファイルを使用するように開発用マシンを設定する方法について説明します。
ms.date: 01/23/2020
ms.openlocfilehash: e45e225e58865ca2b529000ada0984fbeca850f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157714"
---
# <a name="how-to-install-localized-intellisense-files-for-net-core"></a><span data-ttu-id="d90e7-103">.NET Core のローカライズされた IntelliSense ファイルをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="d90e7-103">How to install localized IntelliSense files for .NET Core</span></span>

<span data-ttu-id="d90e7-104">[IntelliSense](/visualstudio/ide/using-intellisense) は、Visual Studio などのさまざまな統合開発環境 (IDE) で使用できるコード補完機能です。</span><span class="sxs-lookup"><span data-stu-id="d90e7-104">[IntelliSense](/visualstudio/ide/using-intellisense) is a code-completion aid that is available in different integrated development environments (IDEs), such as Visual Studio.</span></span> <span data-ttu-id="d90e7-105">既定では、.NET Core プロジェクトを開発している場合、SDK には、英語版の IntelliSense ファイルのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d90e7-105">By default, when you're developing .NET Core projects, the SDK only includes the English version of the IntelliSense files.</span></span> <span data-ttu-id="d90e7-106">この記事では、以下の内容について説明しています。</span><span class="sxs-lookup"><span data-stu-id="d90e7-106">This article explains:</span></span>

- <span data-ttu-id="d90e7-107">ローカライズ版のファイルをインストールする方法。</span><span class="sxs-lookup"><span data-stu-id="d90e7-107">How to install the localized version of those files.</span></span>
- <span data-ttu-id="d90e7-108">別の言語を使用するように Visual Studio のインストールを変更する方法。</span><span class="sxs-lookup"><span data-stu-id="d90e7-108">How to modify the Visual Studio installation to use a different language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d90e7-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="d90e7-109">Prerequisites</span></span>

- <span data-ttu-id="d90e7-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) 以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="d90e7-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="d90e7-111">[Visual Studio 2019 バージョン 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="d90e7-111">[Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or a later version.</span></span>

## <a name="download-and-install-the-localized-intellisense-files"></a><span data-ttu-id="d90e7-112">ローカライズされた IntelliSense ファイルをダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="d90e7-112">Download and install the localized IntelliSense files</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d90e7-113">この手順では、IntelliSense ファイルを .NET Core のインストール フォルダーにコピーするための管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="d90e7-113">This procedure requires that you have administrator permission to copy the IntelliSense files to the .NET Core installation folder.</span></span>

1. <span data-ttu-id="d90e7-114">[IntelliSense ファイルのダウンロード](https://dotnet.microsoft.com/download/dotnet-core/intellisense)のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-114">Go to the [Download IntelliSense files](https://dotnet.microsoft.com/download/dotnet-core/intellisense) page.</span></span>

1. <span data-ttu-id="d90e7-115">使用したい言語とバージョンの IntelliSense ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d90e7-115">Download the IntelliSense file for the language and version you'd like to use.</span></span>

1. <span data-ttu-id="d90e7-116">.zip ファイルの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-116">Extract the contents of the zip file.</span></span>

1. <span data-ttu-id="d90e7-117">.NET Core の IntelliSense フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-117">Navigate to the .NET Core Intellisense folder.</span></span>

   1. <span data-ttu-id="d90e7-118">.NET Core のインストール フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-118">Navigate to the .NET Core installation folder.</span></span> <span data-ttu-id="d90e7-119">既定では *%ProgramFiles%\dotnet\packs* の下にあります。</span><span class="sxs-lookup"><span data-stu-id="d90e7-119">By default, it's under *%ProgramFiles%\dotnet\packs*.</span></span>
   1. <span data-ttu-id="d90e7-120">IntelliSense をインストールする SDK を選択し、関連付けられているパスに移動します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-120">Choose which SDK you want to install the IntelliSense for, and navigate to the associated path.</span></span> <span data-ttu-id="d90e7-121">次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="d90e7-121">You have the following options:</span></span>

      | <span data-ttu-id="d90e7-122">SDK の種類</span><span class="sxs-lookup"><span data-stu-id="d90e7-122">SDK type</span></span>        | <span data-ttu-id="d90e7-123">Path</span><span class="sxs-lookup"><span data-stu-id="d90e7-123">Path</span></span>                               |
      | --------------- | ---------------------------------- |
      | <span data-ttu-id="d90e7-124">.NET Core</span><span class="sxs-lookup"><span data-stu-id="d90e7-124">.NET Core</span></span>       | <span data-ttu-id="d90e7-125">*Microsoft.NETCore.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="d90e7-125">*Microsoft.NETCore.App.Ref*</span></span>        |
      | <span data-ttu-id="d90e7-126">Windows デスクトップ</span><span class="sxs-lookup"><span data-stu-id="d90e7-126">Windows Desktop</span></span> | <span data-ttu-id="d90e7-127">*Microsoft.WindowsDesktop.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="d90e7-127">*Microsoft.WindowsDesktop.App.Ref*</span></span> |
      | <span data-ttu-id="d90e7-128">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="d90e7-128">.NET Standard</span></span>   | <span data-ttu-id="d90e7-129">*NETStandard.Library.Ref*</span><span class="sxs-lookup"><span data-stu-id="d90e7-129">*NETStandard.Library.Ref*</span></span>          |

   1. <span data-ttu-id="d90e7-130">ローカライズされた IntelliSense をインストールするバージョンに移動します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-130">Navigate to the version you want to install the localized IntelliSense for.</span></span> <span data-ttu-id="d90e7-131">たとえば、*3.1.0* です。</span><span class="sxs-lookup"><span data-stu-id="d90e7-131">For example, *3.1.0*.</span></span>
   1. <span data-ttu-id="d90e7-132">*ref* フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="d90e7-132">Open the *ref* folder.</span></span>
   1. <span data-ttu-id="d90e7-133">モニカー フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="d90e7-133">Open the moniker folder.</span></span> <span data-ttu-id="d90e7-134">たとえば、*netcoreapp3.1* です。</span><span class="sxs-lookup"><span data-stu-id="d90e7-134">For example, *netcoreapp3.1*.</span></span>

   <span data-ttu-id="d90e7-135">したがって、移動先の完全なパスは *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1* のようになります。</span><span class="sxs-lookup"><span data-stu-id="d90e7-135">So, the full path that you'd navigate to would look similar to *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.</span></span>

1. <span data-ttu-id="d90e7-136">開いたばかりのモニカー フォルダー内にサブフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-136">Create a subfolder inside the moniker folder you just opened.</span></span> <span data-ttu-id="d90e7-137">フォルダーの名前は、使用する言語を示します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-137">The name of the folder indicates which language you want to use.</span></span> <span data-ttu-id="d90e7-138">次の表に、さまざまなオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-138">The following table specifies the different options:</span></span>

   | <span data-ttu-id="d90e7-139">言語</span><span class="sxs-lookup"><span data-stu-id="d90e7-139">Language</span></span>              | <span data-ttu-id="d90e7-140">[フォルダー名]</span><span class="sxs-lookup"><span data-stu-id="d90e7-140">Folder name</span></span> |
   | --------------------- | ----------- |
   | <span data-ttu-id="d90e7-141">ポルトガル語 (ブラジル)</span><span class="sxs-lookup"><span data-stu-id="d90e7-141">Brazilian Portuguese</span></span>  | <span data-ttu-id="d90e7-142">*pt-br*</span><span class="sxs-lookup"><span data-stu-id="d90e7-142">*pt-br*</span></span>     |
   | <span data-ttu-id="d90e7-143">簡体中国語</span><span class="sxs-lookup"><span data-stu-id="d90e7-143">Chinese (simplified)</span></span>  | <span data-ttu-id="d90e7-144">*zh-hans*</span><span class="sxs-lookup"><span data-stu-id="d90e7-144">*zh-hans*</span></span>   |
   | <span data-ttu-id="d90e7-145">繁体中国語</span><span class="sxs-lookup"><span data-stu-id="d90e7-145">Chinese (traditional)</span></span> | <span data-ttu-id="d90e7-146">*zh-hant*</span><span class="sxs-lookup"><span data-stu-id="d90e7-146">*zh-hant*</span></span>   |
   | <span data-ttu-id="d90e7-147">フランス語</span><span class="sxs-lookup"><span data-stu-id="d90e7-147">French</span></span>                | <span data-ttu-id="d90e7-148">*fr*</span><span class="sxs-lookup"><span data-stu-id="d90e7-148">*fr*</span></span>        |
   | <span data-ttu-id="d90e7-149">German</span><span class="sxs-lookup"><span data-stu-id="d90e7-149">German</span></span>                | <span data-ttu-id="d90e7-150">*de*</span><span class="sxs-lookup"><span data-stu-id="d90e7-150">*de*</span></span>        |
   | <span data-ttu-id="d90e7-151">イタリア語</span><span class="sxs-lookup"><span data-stu-id="d90e7-151">Italian</span></span>               | <span data-ttu-id="d90e7-152">*it*</span><span class="sxs-lookup"><span data-stu-id="d90e7-152">*it*</span></span>        |
   | <span data-ttu-id="d90e7-153">日本語</span><span class="sxs-lookup"><span data-stu-id="d90e7-153">Japanese</span></span>              | <span data-ttu-id="d90e7-154">*ja*</span><span class="sxs-lookup"><span data-stu-id="d90e7-154">*ja*</span></span>        |
   | <span data-ttu-id="d90e7-155">韓国語</span><span class="sxs-lookup"><span data-stu-id="d90e7-155">Korean</span></span>                | <span data-ttu-id="d90e7-156">*ko*</span><span class="sxs-lookup"><span data-stu-id="d90e7-156">*ko*</span></span>        |
   | <span data-ttu-id="d90e7-157">ロシア語</span><span class="sxs-lookup"><span data-stu-id="d90e7-157">Russian</span></span>               | <span data-ttu-id="d90e7-158">*ru*</span><span class="sxs-lookup"><span data-stu-id="d90e7-158">*ru*</span></span>        |
   | <span data-ttu-id="d90e7-159">スペイン語</span><span class="sxs-lookup"><span data-stu-id="d90e7-159">Spanish</span></span>               | <span data-ttu-id="d90e7-160">*es*</span><span class="sxs-lookup"><span data-stu-id="d90e7-160">*es*</span></span>        |

1. <span data-ttu-id="d90e7-161">ステップ 3 で抽出した *.xml* ファイルをこの新しいフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d90e7-161">Copy the *.xml* files you extracted on step 3 to this new folder.</span></span> <span data-ttu-id="d90e7-162">*.xml* ファイルは SDK フォルダーごとに分割されているため、ステップ 4 で選択したものと一致する SDK にコピーします。</span><span class="sxs-lookup"><span data-stu-id="d90e7-162">The *.xml* files are broken down by SDK folders, so copy them to the matching SDK you chose on step 4.</span></span>

## <a name="modify-visual-studio-language"></a><span data-ttu-id="d90e7-163">Visual Studio の言語を変更する</span><span class="sxs-lookup"><span data-stu-id="d90e7-163">Modify Visual Studio language</span></span>

<span data-ttu-id="d90e7-164">Visual Studio で IntelliSense に別の言語を使用するには、適切な言語パックをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d90e7-164">For Visual Studio to use a different language for IntelliSense, install the appropriate language pack.</span></span> <span data-ttu-id="d90e7-165">これは[インストール時](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional)に行うことも、後から Visual Studio のインストールを変更して行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="d90e7-165">This can be done [during installation](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) or at a later time by modifying the Visual Studio installation.</span></span> <span data-ttu-id="d90e7-166">Visual Studio が既に選択した言語に構成されている場合は、IntelliSense のインストールの準備ができています。</span><span class="sxs-lookup"><span data-stu-id="d90e7-166">If you already have Visual Studio configured to the language of your choice, your IntelliSense installation is ready.</span></span>

### <a name="install-the-language-pack"></a><span data-ttu-id="d90e7-167">言語パックをインストールする</span><span class="sxs-lookup"><span data-stu-id="d90e7-167">Install the language pack</span></span>

<span data-ttu-id="d90e7-168">設定時に目的の言語パックをインストールしなかった場合は、次のようにして Visual Studio を更新して言語パックをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d90e7-168">If you didn't install the desired language pack during setup, update Visual Studio as follows to install the language pack:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d90e7-169">Visual Studio をインストール、更新、または変更するには、管理者のアクセス許可を持つアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d90e7-169">To install, update, or modify Visual Studio, you must log on with an account that has administrator permission.</span></span> <span data-ttu-id="d90e7-170">詳細については、「[ユーザー アクセス許可と Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d90e7-170">For more information, see [User permissions and Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span></span>

1. <span data-ttu-id="d90e7-171">コンピューター上で Visual Studio インストーラーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="d90e7-171">Find the Visual Studio Installer on your computer.</span></span>

   <span data-ttu-id="d90e7-172">たとえば、Windows 10 を実行しているコンピューター上で、 **[スタート]** を選択し、**Visual Studio インストーラー**としてリスト表示される **V** の文字までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="d90e7-172">For example, on a computer running Windows 10, select **Start**, and then scroll to the letter **V**, where it's listed as **Visual Studio Installer**.</span></span>

   ![Windows から Visual Studio インストーラーを開く](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > <span data-ttu-id="d90e7-174">また、Visual Studio インストーラーは次の場所にもあります。</span><span class="sxs-lookup"><span data-stu-id="d90e7-174">You can also find the Visual Studio Installer in the following location:</span></span>
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   <span data-ttu-id="d90e7-175">続行する前に、インストーラーの更新が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d90e7-175">You might have to update the installer before continuing.</span></span> <span data-ttu-id="d90e7-176">その場合は、画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="d90e7-176">If so, follow the prompts.</span></span>

1. <span data-ttu-id="d90e7-177">インストーラーで、言語パックを追加する Visual Studio のエディションを探し、 **[変更]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-177">In the installer, look for the edition of Visual Studio that you want to add the language pack to, and then choose **Modify**.</span></span>

   ![Visual Studio の更新または変更](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > <span data-ttu-id="d90e7-179">**[変更]** ボタンが表示されず、代わりに **[更新]** ボタンが表示されている場合は、インストールを変更する前に Visual Studio を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d90e7-179">If you don't see a **Modify** button but you see an **Update** one instead, you need to update your Visual Studio before you can modify your installation.</span></span>
   > <span data-ttu-id="d90e7-180">更新が完了すると、 **[変更]** ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d90e7-180">After the update is finished, the **Modify** button should appear.</span></span>

1. <span data-ttu-id="d90e7-181">**[言語パック]** タブで、インストールまたはアンインストールする言語を選択または選択解除します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-181">In the **Language packs** tab, select or deselect the languages you want to install or uninstall.</span></span>

   ![Visual Studio の [言語パック] タブ](./media/localized-intellisense/vs-modify-language-packs.png)

1. <span data-ttu-id="d90e7-183">**[変更]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-183">Choose **Modify**.</span></span> <span data-ttu-id="d90e7-184">更新が開始されます。</span><span class="sxs-lookup"><span data-stu-id="d90e7-184">The update starts.</span></span>

### <a name="modify-language-settings-in-visual-studio"></a><span data-ttu-id="d90e7-185">Visual Studio の言語設定を変更する</span><span class="sxs-lookup"><span data-stu-id="d90e7-185">Modify language settings in Visual Studio</span></span>

<span data-ttu-id="d90e7-186">目的の言語パックをインストールしたら、別の言語を使用するように Visual Studio の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-186">Once you've installed the desired language packs, modify your Visual Studio settings to use a different language:</span></span>

1. <span data-ttu-id="d90e7-187">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="d90e7-187">Open Visual Studio.</span></span>

1. <span data-ttu-id="d90e7-188">スタート ウィンドウで、 **[コードなしで続行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-188">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="d90e7-189">メニュー バーで、 **[ツール]**  >  **[オプション]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-189">On the menu bar, select **Tools** > **Options**.</span></span> <span data-ttu-id="d90e7-190">[オプション] ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d90e7-190">The Options dialog opens.</span></span>

1. <span data-ttu-id="d90e7-191">**[環境]** ノードで、 **[国際対応の設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-191">Under the **Environment** node, choose **International Settings**.</span></span>

1. <span data-ttu-id="d90e7-192">**[言語]** ドロップダウンで目的の言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-192">On the **Language** drop-down, select the desired language.</span></span> <span data-ttu-id="d90e7-193">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d90e7-193">Choose **OK**.</span></span>

1. <span data-ttu-id="d90e7-194">変更を有効にするために Visual Studio を再起動する必要があることを示すダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d90e7-194">A dialog informs you that you have to restart Visual Studio for the changes to take effect.</span></span> <span data-ttu-id="d90e7-195">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d90e7-195">Choose **OK**.</span></span>

1. <span data-ttu-id="d90e7-196">Visual Studio を再起動します。</span><span class="sxs-lookup"><span data-stu-id="d90e7-196">Restart Visual Studio.</span></span>

<span data-ttu-id="d90e7-197">その後、インストールした IntelliSense ファイルのバージョンを対象とする .NET Core プロジェクトを開くと、IntelliSense が期待どおりに動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="d90e7-197">After this, your IntelliSense should work as expected when you open a .NET Core project that targets the version of the IntelliSense files you just installed.</span></span>

## <a name="see-also"></a><span data-ttu-id="d90e7-198">参照</span><span class="sxs-lookup"><span data-stu-id="d90e7-198">See also</span></span>

- [<span data-ttu-id="d90e7-199">Visual Studio での IntelliSense</span><span class="sxs-lookup"><span data-stu-id="d90e7-199">IntelliSense in Visual Studio</span></span>](/visualstudio/ide/using-intellisense)
