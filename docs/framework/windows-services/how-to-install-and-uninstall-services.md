---
title: '方法: Windows サービスをインストールおよびアンインストールする'
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
ms.openlocfilehash: 38fc0172b5f97561d69fe495237e95597d7b9727
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003137"
---
# <a name="how-to-install-and-uninstall-windows-services"></a><span data-ttu-id="9482f-102">方法: Windows サービスをインストールおよびアンインストールする</span><span class="sxs-lookup"><span data-stu-id="9482f-102">How to: Install and uninstall Windows services</span></span>

<span data-ttu-id="9482f-103">.NET Framework で Windows サービスを開発している場合は、 [*installutil.exe*](../tools/installutil-exe-installer-tool.md)コマンドラインユーティリティまたは[PowerShell](/powershell/scripting/overview)を使用して、サービスアプリをすばやくインストールできます。</span><span class="sxs-lookup"><span data-stu-id="9482f-103">If you’re developing a Windows service with the .NET Framework, you can quickly install your service app by using the [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) command-line utility or [PowerShell](/powershell/scripting/overview).</span></span> <span data-ttu-id="9482f-104">ユーザーがインストールおよびアンインストールできる Windows サービスをリリースする開発者は、InstallShield を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9482f-104">Developers who want to release a Windows service that users can install and uninstall should use InstallShield.</span></span> <span data-ttu-id="9482f-105">詳細については、「[インストーラー パッケージを作成する (Windows デスクトップ)](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9482f-105">For more information, see [Create an installer package (Windows client)](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).</span></span>

> [!WARNING]
> <span data-ttu-id="9482f-106">サービスをコンピューターからアンインストールする場合は、この記事の手順には従わないでください。</span><span class="sxs-lookup"><span data-stu-id="9482f-106">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="9482f-107">代わりに、サービスをインストールしたプログラムまたはソフトウェア パッケージを確認し、[設定] で **[アプリ]** を選択してそのプログラムをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="9482f-107">Instead, find out which program or software package installed the service, and then choose **Apps** in Settings to uninstall that program.</span></span> <span data-ttu-id="9482f-108">多くのサービスが Windows の不可欠な構成要素であることに注意してください。それらを削除すると、システムが不安定になることがあります。</span><span class="sxs-lookup"><span data-stu-id="9482f-108">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>

<span data-ttu-id="9482f-109">この記事の手順を使用するには、まず、Windows サービスにサービス インストーラーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9482f-109">To use the steps in this article, you first need to add a service installer to your Windows service.</span></span> <span data-ttu-id="9482f-110">詳細については、「[チュートリアル:Windows サービス アプリケーションを作成する](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9482f-110">For more information, see [Walkthrough: Creating a Windows service app](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>

<span data-ttu-id="9482f-111">Windows サービス プロジェクトを、F5 キーを押して Visual Studio 開発環境から直接実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="9482f-111">You can't run Windows service projects directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="9482f-112">プロジェクトを実行するには、プロジェクトにサービスを事前にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9482f-112">Before you can run the project, you must install the service in the project.</span></span>

> [!TIP]
> <span data-ttu-id="9482f-113">**サーバー エクスプローラー**を使用して、サービスがインストールまたはアンインストールされているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9482f-113">You can use **Server Explorer** to verify that you've installed or uninstalled your service.</span></span> <span data-ttu-id="9482f-114">詳細については、[Visual Studio でのサーバー エクスプローラーの使用方法](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9482f-114">For more information, see [How to use Server Explorer in Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span></span>

### <a name="install-your-service-manually-using-installutilexe-utility"></a><span data-ttu-id="9482f-115">Installutil.exe ユーティリティを使用して手動でサービスをインストールする</span><span class="sxs-lookup"><span data-stu-id="9482f-115">Install your service manually using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="9482f-116">**[スタート]** メニューから **[Visual Studio \<*バージョン*>]** ディレクトリを選択し、 **[開発者コマンド プロンプト for VS \<*バージョン*>]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9482f-116">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="9482f-117">Visual Studio 用開発者コマンド プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9482f-117">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="9482f-118">プロジェクトのコンパイル済み実行可能ファイルが格納されているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="9482f-118">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="9482f-119">プロジェクトの実行可能ファイルをパラメーターとして指定し、コマンド プロンプトから *InstallUtil.exe* を実行します。</span><span class="sxs-lookup"><span data-stu-id="9482f-119">Run *InstallUtil.exe* from the command prompt with your project's executable as a parameter:</span></span>

    ```console
    installutil <yourproject>.exe
    ```

     <span data-ttu-id="9482f-120">Visual Studio 用開発者コマンド プロンプトを使用している場合、*InstallUtil.exe* はシステム パス上にあるはずです。</span><span class="sxs-lookup"><span data-stu-id="9482f-120">If you’re using the Developer Command Prompt for Visual Studio, *InstallUtil.exe* should be on the system path.</span></span> <span data-ttu-id="9482f-121">ない場合は、パスに追加するか、完全修飾パスを使用して起動します。</span><span class="sxs-lookup"><span data-stu-id="9482f-121">Otherwise, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="9482f-122">このツールは、.NET Framework と共に *%WINDIR%\Microsoft.NET\Framework[64]\\<フレームワーク_バージョン\>* フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9482f-122">This tool is installed with the .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<framework_version\>*.</span></span>

     <span data-ttu-id="9482f-123">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9482f-123">For example:</span></span>
     - <span data-ttu-id="9482f-124">32 ビット バージョンの .NET Framework 4 または 4.5 以降では、Windows のインストール ディレクトリが *C:\Windows* の場合、既定のパスは *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe* です。</span><span class="sxs-lookup"><span data-stu-id="9482f-124">For the 32-bit version of the .NET Framework 4 or 4.5 and later, if your Windows installation directory is *C:\Windows*, the default path is *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>
     - <span data-ttu-id="9482f-125">64 ビット バージョンの .NET Framework 4 または 4.5 以降では、既定のパスは *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe* です。</span><span class="sxs-lookup"><span data-stu-id="9482f-125">For the 64-bit version of the .NET Framework 4 or 4.5 and later, the default path is *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>

### <a name="uninstall-your-service-manually-using-installutilexe-utility"></a><span data-ttu-id="9482f-126">Installutil.exe ユーティリティを使用してサービスを手動でアンインストールする</span><span class="sxs-lookup"><span data-stu-id="9482f-126">Uninstall your service manually using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="9482f-127">**[スタート]** メニューから **[Visual Studio \<*バージョン*>]** ディレクトリを選択し、 **[開発者コマンド プロンプト for VS \<*バージョン*>]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9482f-127">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="9482f-128">Visual Studio 用開発者コマンド プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9482f-128">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="9482f-129">プロジェクトの出力先ファイルをパラメーターとして指定し、コマンド プロンプトから *InstallUtil.exe* を実行します。</span><span class="sxs-lookup"><span data-stu-id="9482f-129">Run *InstallUtil.exe* from the command prompt with your project's output as a parameter:</span></span>

    ```console
    installutil /u <yourproject>.exe
    ```

3. <span data-ttu-id="9482f-130">実行可能ファイルを削除した後も、レジストリ内にサービスが存在したままになることがあります。</span><span class="sxs-lookup"><span data-stu-id="9482f-130">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="9482f-131">このような場合は、コマンド [sc delete](/windows-server/administration/windows-commands/sc-delete) を使って、レジストリからサービスのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="9482f-131">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

### <a name="install-your-service-manually-using-powershell"></a><span data-ttu-id="9482f-132">PowerShell を使用して手動でサービスをインストールする</span><span class="sxs-lookup"><span data-stu-id="9482f-132">Install your service manually using PowerShell</span></span>

1. <span data-ttu-id="9482f-133">**[スタート]** メニューから**windows powershell**ディレクトリを選択し、 **[windows powershell]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9482f-133">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="9482f-134">プロジェクトのコンパイル済み実行可能ファイルが格納されているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="9482f-134">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="9482f-135">プロジェクトの出力を指定し、サービス名をパラメーターとして指定して、[**新しいサービス**](/powershell/module/microsoft.powershell.management/new-service)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9482f-135">Run the [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) cmdlet with the with your project's output and a service name as parameters:</span></span>

    ```powershell
    New-Service -Name "YourServiceName" -BinaryPathName <yourproject>.exe
    ```

### <a name="uninstall-your-service-manually-using-powershell"></a><span data-ttu-id="9482f-136">PowerShell を使用して手動でサービスをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="9482f-136">Uninstall your service manually using PowerShell</span></span>

1. <span data-ttu-id="9482f-137">**[スタート]** メニューから**windows powershell**ディレクトリを選択し、 **[windows powershell]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9482f-137">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="9482f-138">サービスの名前をパラメーターとして指定して、[**サービスの削除**](/powershell/module/microsoft.powershell.management/remove-service)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9482f-138">Run the [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) cmdlet with the name of your service as parameter:</span></span>

    ```powershell
    Remove-Service -Name "YourServiceName"
    ```

3. <span data-ttu-id="9482f-139">実行可能ファイルを削除した後も、レジストリ内にサービスが存在したままになることがあります。</span><span class="sxs-lookup"><span data-stu-id="9482f-139">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="9482f-140">このような場合は、コマンド [sc delete](/windows-server/administration/windows-commands/sc-delete) を使って、レジストリからサービスのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="9482f-140">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

    ```powershell
    sc.exe delete "YourServiceName"
    ```

## <a name="see-also"></a><span data-ttu-id="9482f-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="9482f-141">See also</span></span>

- [<span data-ttu-id="9482f-142">Windows サービス アプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="9482f-142">Introduction to Windows service applications</span></span>](../windows-services/introduction-to-windows-service-applications.md)
- [<span data-ttu-id="9482f-143">2 つのオブジェクトが等しいかどうかをテストする方法Windows サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="9482f-143">How to: Create Windows services</span></span>](../windows-services/how-to-create-windows-services.md)
- [<span data-ttu-id="9482f-144">2 つのオブジェクトが等しいかどうかをテストする方法サービス アプリケーションにインストーラーを追加する</span><span class="sxs-lookup"><span data-stu-id="9482f-144">How to: Add installers to your service application</span></span>](../windows-services/how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="9482f-145">Installutil.exe (インストーラー ツール)</span><span class="sxs-lookup"><span data-stu-id="9482f-145">Installutil.exe (Installer tool)</span></span>](../tools/installutil-exe-installer-tool.md)
