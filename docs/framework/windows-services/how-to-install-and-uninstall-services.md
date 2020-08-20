---
title: '方法: Windows サービスをインストールおよびアンインストールする'
description: Windows サービスをインストールおよびアンインストールする方法について確認します。 .NET を使用して Windows サービスを開発している場合は、InstallUtil.exe または PowerShell を使用することができます。
ms.date: 02/05/2019
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, apps, Windows services
- installation, Windows services
- uninstalling Windows services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
author: ghogen
ms.openlocfilehash: 883b587a7ef60bc686d6f453c775f6651f0ccb7f
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063823"
---
# <a name="how-to-install-and-uninstall-windows-services"></a><span data-ttu-id="69f57-104">方法: Windows サービスをインストールおよびアンインストールする</span><span class="sxs-lookup"><span data-stu-id="69f57-104">How to: Install and uninstall Windows services</span></span>

<span data-ttu-id="69f57-105">.NET Framework を使用して Windows サービスを開発している場合は、[*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) コマンド ライン ユーティリティまたは [PowerShell](/powershell/scripting/overview) を使用してサービス アプリをすばやくインストールできます。</span><span class="sxs-lookup"><span data-stu-id="69f57-105">If you’re developing a Windows service with the .NET Framework, you can quickly install your service app by using the [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) command-line utility or [PowerShell](/powershell/scripting/overview).</span></span> <span data-ttu-id="69f57-106">ユーザーがインストールおよびアンインストールできる Windows サービスをリリースしたい開発者は、無料の [WiX ツールセット](https://wixtoolset.org/)、あるいは [Advanced Installer](https://www.advancedinstaller.com/) や [InstallShield](https://www.revenera.com/install/products/installshield.html) などの商用ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="69f57-106">Developers who want to release a Windows service that users can install and uninstall can use the free [WiX Toolset](https://wixtoolset.org/) or commercial tools like [Advanced Installer](https://www.advancedinstaller.com/), [InstallShield](https://www.revenera.com/install/products/installshield.html), or others.</span></span> <span data-ttu-id="69f57-107">詳細については、「[インストーラー パッケージを作成する (Windows デスクトップ)](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69f57-107">For more information, see [Create an installer package (Windows desktop)](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>

> [!WARNING]
> <span data-ttu-id="69f57-108">サービスをコンピューターからアンインストールする場合は、この記事の手順には従わないでください。</span><span class="sxs-lookup"><span data-stu-id="69f57-108">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="69f57-109">代わりに、サービスをインストールしたプログラムまたはソフトウェア パッケージを確認し、[設定] で **[アプリ]** を選択してそのプログラムをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="69f57-109">Instead, find out which program or software package installed the service, and then choose **Apps** in Settings to uninstall that program.</span></span> <span data-ttu-id="69f57-110">多くのサービスが Windows の不可欠な構成要素であることに注意してください。それらを削除すると、システムが不安定になることがあります。</span><span class="sxs-lookup"><span data-stu-id="69f57-110">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>

<span data-ttu-id="69f57-111">この記事の手順を使用するには、まず、Windows サービスにサービス インストーラーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69f57-111">To use the steps in this article, you first need to add a service installer to your Windows service.</span></span> <span data-ttu-id="69f57-112">詳細については、「[チュートリアル:Windows サービス アプリケーションを作成する](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69f57-112">For more information, see [Walkthrough: Creating a Windows service app](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>

<span data-ttu-id="69f57-113">Windows サービス プロジェクトを、F5 キーを押して Visual Studio 開発環境から直接実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="69f57-113">You can't run Windows service projects directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="69f57-114">プロジェクトを実行するには、プロジェクトにサービスを事前にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69f57-114">Before you can run the project, you must install the service in the project.</span></span>

> [!TIP]
> <span data-ttu-id="69f57-115">**サーバー エクスプローラー**を使用して、サービスがインストールまたはアンインストールされているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="69f57-115">You can use **Server Explorer** to verify that you've installed or uninstalled your service.</span></span> <span data-ttu-id="69f57-116">詳細については、[Visual Studio でのサーバー エクスプローラーの使用方法](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="69f57-116">For more information, see [How to use Server Explorer in Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span></span>

### <a name="install-your-service-manually-using-installutilexe-utility"></a><span data-ttu-id="69f57-117">Installutil.exe ユーティリティを使用してサービスを手動でインストールする</span><span class="sxs-lookup"><span data-stu-id="69f57-117">Install your service manually using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="69f57-118">**[スタート]** メニューから **[Visual Studio \<*version*>]** ディレクトリを選択し、 **[VS 用開発者コマンド プロンプト\<*version*>]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="69f57-118">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="69f57-119">Visual Studio 用開発者コマンド プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69f57-119">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="69f57-120">プロジェクトのコンパイル済み実行可能ファイルが格納されているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="69f57-120">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="69f57-121">プロジェクトの実行可能ファイルをパラメーターとして指定し、コマンド プロンプトから *InstallUtil.exe* を実行します。</span><span class="sxs-lookup"><span data-stu-id="69f57-121">Run *InstallUtil.exe* from the command prompt with your project's executable as a parameter:</span></span>

    ```console
    installutil <yourproject>.exe
    ```

     <span data-ttu-id="69f57-122">Visual Studio 用開発者コマンド プロンプトを使用している場合、*InstallUtil.exe* はシステム パス上にあるはずです。</span><span class="sxs-lookup"><span data-stu-id="69f57-122">If you’re using the Developer Command Prompt for Visual Studio, *InstallUtil.exe* should be on the system path.</span></span> <span data-ttu-id="69f57-123">ない場合は、パスに追加するか、完全修飾パスを使用して起動します。</span><span class="sxs-lookup"><span data-stu-id="69f57-123">Otherwise, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="69f57-124">このツールは、.NET Framework と共に *%WINDIR%\Microsoft.NET\Framework[64]\\<フレームワーク_バージョン\>* フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="69f57-124">This tool is installed with the .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<framework_version\>*.</span></span>

     <span data-ttu-id="69f57-125">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="69f57-125">For example:</span></span>
     - <span data-ttu-id="69f57-126">32 ビット バージョンの .NET Framework 4 または 4.5 以降では、Windows のインストール ディレクトリが *C:\Windows* の場合、既定のパスは *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe* です。</span><span class="sxs-lookup"><span data-stu-id="69f57-126">For the 32-bit version of the .NET Framework 4 or 4.5 and later, if your Windows installation directory is *C:\Windows*, the default path is *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>
     - <span data-ttu-id="69f57-127">64 ビット バージョンの .NET Framework 4 または 4.5 以降では、既定のパスは *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe* です。</span><span class="sxs-lookup"><span data-stu-id="69f57-127">For the 64-bit version of the .NET Framework 4 or 4.5 and later, the default path is *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>

### <a name="uninstall-your-service-manually-using-installutilexe-utility"></a><span data-ttu-id="69f57-128">Installutil.exe ユーティリティを使用してサービスを手動でアンインストールする</span><span class="sxs-lookup"><span data-stu-id="69f57-128">Uninstall your service manually using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="69f57-129">**[スタート]** メニューから **[Visual Studio \<*version*>]** ディレクトリを選択し、 **[VS 用開発者コマンド プロンプト\<*version*>]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="69f57-129">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="69f57-130">Visual Studio 用開発者コマンド プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69f57-130">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="69f57-131">プロジェクトの出力先ファイルをパラメーターとして指定し、コマンド プロンプトから *InstallUtil.exe* を実行します。</span><span class="sxs-lookup"><span data-stu-id="69f57-131">Run *InstallUtil.exe* from the command prompt with your project's output as a parameter:</span></span>

    ```console
    installutil /u <yourproject>.exe
    ```

3. <span data-ttu-id="69f57-132">実行可能ファイルを削除した後も、レジストリ内にサービスが存在したままになることがあります。</span><span class="sxs-lookup"><span data-stu-id="69f57-132">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="69f57-133">このような場合は、コマンド [sc delete](/windows-server/administration/windows-commands/sc-delete) を使って、レジストリからサービスのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="69f57-133">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

### <a name="install-your-service-manually-using-powershell"></a><span data-ttu-id="69f57-134">PowerShell を使用してサービスを手動でインストールする</span><span class="sxs-lookup"><span data-stu-id="69f57-134">Install your service manually using PowerShell</span></span>

1. <span data-ttu-id="69f57-135">**スタート** メニューから、**Windows PowerShell** ディレクトリを選択し、 **[Windows PowerShell]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="69f57-135">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="69f57-136">プロジェクトのコンパイル済み実行可能ファイルが格納されているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="69f57-136">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="69f57-137">プロジェクトの出力とサービス名をパラメーターとして指定して、[**New-Service**](/powershell/module/microsoft.powershell.management/new-service) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="69f57-137">Run the [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) cmdlet with the with your project's output and a service name as parameters:</span></span>

    ```powershell
    New-Service -Name "YourServiceName" -BinaryPathName <yourproject>.exe
    ```

### <a name="uninstall-your-service-manually-using-powershell"></a><span data-ttu-id="69f57-138">PowerShell を使用してサービスを手動でアンインストールする</span><span class="sxs-lookup"><span data-stu-id="69f57-138">Uninstall your service manually using PowerShell</span></span>

1. <span data-ttu-id="69f57-139">**スタート** メニューから、**Windows PowerShell** ディレクトリを選択し、 **[Windows PowerShell]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="69f57-139">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="69f57-140">サービスの名前をパラメーターとして指定して、[**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="69f57-140">Run the [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) cmdlet with the name of your service as parameter:</span></span>

    ```powershell
    Remove-Service -Name "YourServiceName"
    ```

3. <span data-ttu-id="69f57-141">実行可能ファイルを削除した後も、レジストリ内にサービスが存在したままになることがあります。</span><span class="sxs-lookup"><span data-stu-id="69f57-141">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="69f57-142">このような場合は、コマンド [sc delete](/windows-server/administration/windows-commands/sc-delete) を使って、レジストリからサービスのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="69f57-142">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

    ```powershell
    sc.exe delete "YourServiceName"
    ```

## <a name="see-also"></a><span data-ttu-id="69f57-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="69f57-143">See also</span></span>

- [<span data-ttu-id="69f57-144">Windows サービス アプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="69f57-144">Introduction to Windows service applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="69f57-145">方法: Windows サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="69f57-145">How to: Create Windows services</span></span>](how-to-create-windows-services.md)
- [<span data-ttu-id="69f57-146">方法: サービス アプリケーションにインストーラーを追加する</span><span class="sxs-lookup"><span data-stu-id="69f57-146">How to: Add installers to your service application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="69f57-147">Installutil.exe (インストーラー ツール)</span><span class="sxs-lookup"><span data-stu-id="69f57-147">Installutil.exe (Installer tool)</span></span>](../tools/installutil-exe-installer-tool.md)
