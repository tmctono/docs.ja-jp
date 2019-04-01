---
title: '方法: インストールされている .NET Framework バージョンを確認する'
ms.date: 03/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c4ad3ca5694457637a82a36c8db4534df43a9d7
ms.sourcegitcommit: 8258515adc6c37ab6278e5a3d102d593246f8672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "58504432"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="d4023-102">方法: インストールされている .NET Framework バージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="d4023-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="d4023-103">ユーザーはコンピューターに複数のバージョンの .NET Framework を[インストール](https://docs.microsoft.com/dotnet/framework/install)して実行できます。</span><span class="sxs-lookup"><span data-stu-id="d4023-103">Users can [install](https://docs.microsoft.com/dotnet/framework/install) and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="d4023-104">アプリを開発または配置する場合、どのバージョンの .NET Framework がユーザーのコンピューターにインストールされているかを確認しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d4023-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> 

<span data-ttu-id="d4023-105">.NET Framework は、個別にバージョン管理される 2 つの主要コンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="d4023-105">The .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
- <span data-ttu-id="d4023-106">アプリに機能を提供する型やリソースのコレクションである一連のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="d4023-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="d4023-107">.NET Framework とアセンブリは同じバージョン番号を共有します。</span><span class="sxs-lookup"><span data-stu-id="d4023-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
- <span data-ttu-id="d4023-108">アプリのコードを管理および実行する共通言語ランタイム (CLR)。</span><span class="sxs-lookup"><span data-stu-id="d4023-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="d4023-109">CLR は独自のバージョン番号で識別されます (「[バージョンおよび依存関係](~/docs/framework/migration-guide/versions-and-dependencies.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="d4023-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  

> [!NOTE]
> <span data-ttu-id="d4023-110">新しい各バージョンの .NET Framework には、1 つ前のバージョンの機能が含まれると共に、新機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="d4023-110">Each new version of the .NET Framework retains features from the previous versions and adds new features.</span></span> <span data-ttu-id="d4023-111">同じコンピューターに .NET Framework の複数のバージョンを同時に読み込むことができます。これは、以前のバージョンをアンインストールせずに、.NET Framework をインストールできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d4023-111">You can load multiple versions of the .NET Framework on a single computer at the same time, which means that you can install the .NET Framework without having to uninstall previous versions.</span></span> <span data-ttu-id="d4023-112">一般に、以前の .NET Framework のバージョンはアンインストールしないでください。使用するアプリケーションが特定のバージョンに依存しており、そのバージョンが削除されると破損してしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d4023-112">In general, you shouldn't uninstall previous versions of the .NET Framework, because an application you use may depend on a specific version and may break if that version is removed.</span></span>
>
> <span data-ttu-id="d4023-113">.NET Framework のバージョンと CLR のバージョンの間には違いがあります。</span><span class="sxs-lookup"><span data-stu-id="d4023-113">There is a difference between the .NET Framework version and the CLR version:</span></span> 
> - <span data-ttu-id="d4023-114">.NET Framework は、.NET Framework のクラス ライブラリを構成するアセンブリのセットに基づいてバージョン管理されています。</span><span class="sxs-lookup"><span data-stu-id="d4023-114">The .NET Framework version is based on the set of assemblies that form the .NET Framework class library.</span></span> <span data-ttu-id="d4023-115">たとえば、.NET Framework のバージョンには、4.5、4.6.1、および 4.7.2 が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d4023-115">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span> 
>- <span data-ttu-id="d4023-116">CLR は、.NET Framework アプリケーションが実行されているランタイムに基づいてバージョン管理されています。</span><span class="sxs-lookup"><span data-stu-id="d4023-116">The CLR version is based on the runtime on which .NET Framework applications execute.</span></span> <span data-ttu-id="d4023-117">1 つの CLR バージョンは、通常複数の NET Framework バージョンをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d4023-117">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="d4023-118">たとえば、CLR バージョン 4.0.30319.*xxxxx* は .NET Framework バージョン 4 から 4.5.2 をサポートしており、CLR バージョン 4.0.30319.42000 は .NET Framework 4.6 以降をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d4023-118">For example, CLR version 4.0.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2 and CLR version 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span> 
>
> <span data-ttu-id="d4023-119">バージョンの詳細については、「[.NET Framework のバージョンおよび依存関係](versions-and-dependencies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4023-119">For more information about versions, see [.NET Framework versions and dependencies](versions-and-dependencies.md).</span></span>


<span data-ttu-id="d4023-120">コンピューターにインストールされている .NET Framework のバージョンの一覧を取得するには、レジストリにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d4023-120">To get a list of the .NET Framework versions installed on a computer, you access the registry.</span></span> <span data-ttu-id="d4023-121">レジストリを確認するには、レジストリ エディタを使用するか、次に従ってコードで照会します。</span><span class="sxs-lookup"><span data-stu-id="d4023-121">You can either use the Registry Editor to view the registry or use code to query it:</span></span>
 
- <span data-ttu-id="d4023-122">.NET Framework の新しいバージョンを探す (4.5 以降):</span><span class="sxs-lookup"><span data-stu-id="d4023-122">Find newer .NET Framework versions (4.5 and later):</span></span> 
     - [<span data-ttu-id="d4023-123">レジストリ エディターを使用し .NET Framework のバージョンを探す</span><span class="sxs-lookup"><span data-stu-id="d4023-123">Use the Registry Editor to find .NET Framework versions</span></span>](#net_b)  
     - [<span data-ttu-id="d4023-124">コードを使用し .NET Framework のバージョンのレジストリを照会する</span><span class="sxs-lookup"><span data-stu-id="d4023-124">Use code to query the registry for .NET Framework versions</span></span>](#net_d)  
     - [<span data-ttu-id="d4023-125">PowerShell を使用し .NET Framework のバージョンのレジストリを照会する</span><span class="sxs-lookup"><span data-stu-id="d4023-125">Use PowerShell to query the registry for .NET Framework versions</span></span>](#ps_a)
- <span data-ttu-id="d4023-126">.NET Framework の古いバージョンを探す (1 から 4):</span><span class="sxs-lookup"><span data-stu-id="d4023-126">Find older .NET Framework versions (1&#8211;4):</span></span>
     - [<span data-ttu-id="d4023-127">レジストリ エディターを使用し .NET Framework のバージョンを探す</span><span class="sxs-lookup"><span data-stu-id="d4023-127">Use the Registry Editor to find .NET Framework versions</span></span>](#net_a)
     - [<span data-ttu-id="d4023-128">コードを使用し .NET Framework のバージョンのレジストリを照会する</span><span class="sxs-lookup"><span data-stu-id="d4023-128">Use code to query the registry for .NET Framework versions</span></span>](#net_c)   

<span data-ttu-id="d4023-129">コンピューターにインストールされている CLR のバージョンの一覧を取得するには、次のツールまたはコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4023-129">To get a list of the CLR versions installed on a computer, use a tool or code:</span></span>  
  
- [<span data-ttu-id="d4023-130">Clrver ツールを使用する</span><span class="sxs-lookup"><span data-stu-id="d4023-130">Use the Clrver tool</span></span>](#clr_a)  
- [<span data-ttu-id="d4023-131">コードを使用して Environment クラスを照会する</span><span class="sxs-lookup"><span data-stu-id="d4023-131">Use code to query the Environment class</span></span>](#clr_b)  

<span data-ttu-id="d4023-132">.NET Framework の各バージョン用にインストールされている更新プログラムの検出については、「[方法:インストールされている .NET Framework の更新プログラムを確認する](how-to-determine-which-net-framework-updates-are-installed.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4023-132">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span> 
  

## <a name="find-newer-net-framework-versions-45-and-later"></a><span data-ttu-id="d4023-133">.NET Framework の新しいバージョンを探す (4.5 以降)</span><span class="sxs-lookup"><span data-stu-id="d4023-133">Find newer .NET Framework versions (4.5 and later)</span></span>

<a name="net_b"></a> 
### <a name="find-net-framework-versions-45-and-later-in-the-registry"></a><span data-ttu-id="d4023-134">レジストリで .NET Framework バージョン 4.5 以降を探す</span><span class="sxs-lookup"><span data-stu-id="d4023-134">Find .NET Framework versions 4.5 and later in the registry</span></span>

1. <span data-ttu-id="d4023-135">**スタート** メニューの **[ファイル名を指定して実行]** を選択し、「*regedit*」と入力し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4023-135">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

     <span data-ttu-id="d4023-136">regedit を実行するには、管理特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="d4023-136">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="d4023-137">レジストリ エディターで、次のサブキーを開きます。**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**</span><span class="sxs-lookup"><span data-stu-id="d4023-137">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span></span> <span data-ttu-id="d4023-138">**Full** サブキーが存在しない場合は、.NET Framework 4.5 以降はインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="d4023-138">If the **Full** subkey isn't present, then you don't have the .NET Framework 4.5 or later installed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4023-139">レジストリの **NET Framework セットアップ** フォルダーの先頭はピリオドではありません。</span><span class="sxs-lookup"><span data-stu-id="d4023-139">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

3. <span data-ttu-id="d4023-140">**Release** という DWORD のエントリを探します。</span><span class="sxs-lookup"><span data-stu-id="d4023-140">Check for a DWORD entry named **Release**.</span></span> <span data-ttu-id="d4023-141">それがある場合、.NET Framework 4.5 以降のバージョンがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="d4023-141">If it exists, then you have .NET Framework 4.5 or later versions installed.</span></span> <span data-ttu-id="d4023-142">その値は、.NET Framework の特定のバージョンのリリース キーです。</span><span class="sxs-lookup"><span data-stu-id="d4023-142">Its value is a release key that corresponds to a particular version of the .NET Framework.</span></span> <span data-ttu-id="d4023-143">たとえば、次の図では、**Release** エントリの値は *378389* で、これは .NET Framework 4.5 のリリース キーです。</span><span class="sxs-lookup"><span data-stu-id="d4023-143">In the following figure, for example, the value of the **Release** entry is *378389*, which is the release key for .NET Framework 4.5.</span></span> 

     <span data-ttu-id="d4023-144">![.NET Framework 4.5 のレジストリ エントリ](media/clr-installdir.png ".NET Framework 4.5 のレジストリ エントリ")</span><span class="sxs-lookup"><span data-stu-id="d4023-144">![Registry entry for the .NET Framework 4.5](media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span></span>

<span data-ttu-id="d4023-145">次の表に、.NET Framework の各バージョンの最小の **Release** エントリ値の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="d4023-145">The following table lists the minimum value of the **Release** entry for each .NET Framework version.</span></span> <span data-ttu-id="d4023-146">これらの値は次のように使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4023-146">You can use these values as follows:</span></span>

- <span data-ttu-id="d4023-147">.NET Framework の最小バージョンが存在するかどうかを確認するには、レジストリの **Release** DWORD 値が表で示されている値*以上*であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4023-147">To determine whether a minimum .NET Framework version is present, test whether the **Release** DWORD value found in the registry is *greater than or equal to* the value listed in the table.</span></span> <span data-ttu-id="d4023-148">たとえば、アプリケーションで .NET Framework 4.7 以降が必要な場合は、最小のリリース キー値 *460798* があるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4023-148">For example, if your application requires the .NET Framework 4.7 or later, you test for a minimum release key value of *460798*.</span></span>

- <span data-ttu-id="d4023-149">複数のバージョンについて調べるには、.NET Framework の最新のバージョンから始めて、以前のバージョンに順番に遡りながら調べます。</span><span class="sxs-lookup"><span data-stu-id="d4023-149">To test for multiple versions, begin with the latest .NET Framework version, and then test for each successive earlier version.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|<span data-ttu-id="d4023-150">.NET Framework のバージョン</span><span class="sxs-lookup"><span data-stu-id="d4023-150">.NET Framework version</span></span>|<span data-ttu-id="d4023-151">Release DWORD の値</span><span class="sxs-lookup"><span data-stu-id="d4023-151">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="d4023-152">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="d4023-152">.NET Framework 4.5</span></span>|<span data-ttu-id="d4023-153">378389</span><span class="sxs-lookup"><span data-stu-id="d4023-153">378389</span></span>|
|<span data-ttu-id="d4023-154">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="d4023-154">.NET Framework 4.5.1</span></span>|<span data-ttu-id="d4023-155">378675</span><span class="sxs-lookup"><span data-stu-id="d4023-155">378675</span></span>|
|<span data-ttu-id="d4023-156">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="d4023-156">.NET Framework 4.5.2</span></span>|<span data-ttu-id="d4023-157">379893</span><span class="sxs-lookup"><span data-stu-id="d4023-157">379893</span></span>|
|<span data-ttu-id="d4023-158">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="d4023-158">.NET Framework 4.6</span></span>|<span data-ttu-id="d4023-159">393295</span><span class="sxs-lookup"><span data-stu-id="d4023-159">393295</span></span>|
|<span data-ttu-id="d4023-160">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="d4023-160">.NET Framework 4.6.1</span></span>|<span data-ttu-id="d4023-161">394254</span><span class="sxs-lookup"><span data-stu-id="d4023-161">394254</span></span>|
|<span data-ttu-id="d4023-162">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="d4023-162">.NET Framework 4.6.2</span></span>|<span data-ttu-id="d4023-163">394802</span><span class="sxs-lookup"><span data-stu-id="d4023-163">394802</span></span>|
|<span data-ttu-id="d4023-164">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="d4023-164">.NET Framework 4.7</span></span>|<span data-ttu-id="d4023-165">460798</span><span class="sxs-lookup"><span data-stu-id="d4023-165">460798</span></span>|
|<span data-ttu-id="d4023-166">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="d4023-166">.NET Framework 4.7.1</span></span>|<span data-ttu-id="d4023-167">461308</span><span class="sxs-lookup"><span data-stu-id="d4023-167">461308</span></span>|
|<span data-ttu-id="d4023-168">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="d4023-168">.NET Framework 4.7.2</span></span>|<span data-ttu-id="d4023-169">461808</span><span class="sxs-lookup"><span data-stu-id="d4023-169">461808</span></span>|

<span data-ttu-id="d4023-170">Windows オペレーティング システムの特定のバージョンに対する .NET Framework のリリース キーの完全な表については、「[.NET Framework のリリース キーと Windows オペレーティング システムのバージョン](release-keys-and-os-versions.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d4023-170">For a complete table of release keys for the .NET Framework for specific Windows operating system versions, see [.NET Framework release keys and Windows operating system versions](release-keys-and-os-versions.md).</span></span>


<a name="net_d"></a> 
### <a name="find-net-framework-versions-45-and-later-with-code"></a><span data-ttu-id="d4023-171">コードで .NET Framework バージョン 4.5 以降を探す</span><span class="sxs-lookup"><span data-stu-id="d4023-171">Find .NET Framework versions 4.5 and later with code</span></span>

1. <span data-ttu-id="d4023-172"><xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> メソッドと <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> メソッドを使用し、Windows レジストリの **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** サブキーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d4023-172">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey in the Windows registry.</span></span>

    <span data-ttu-id="d4023-173">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** サブキーに **Release** DWORD があるということは、コンピューターに .NET Framework 4.5 以降のバージョンがインストールされていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d4023-173">The existence of the **Release** DWORD entry in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey indicates that the .NET Framework 4.5 or a later version is installed on a computer.</span></span> 

2. <span data-ttu-id="d4023-174">**Release** エントリの値を確認して、インストールされているバージョンを判断します。</span><span class="sxs-lookup"><span data-stu-id="d4023-174">Check the value of the **Release** entry to determine the installed version.</span></span> <span data-ttu-id="d4023-175">上位互換性があるかを確認するには、[.NET Framework のバージョンの表](#version_table)で示されている値以上の値があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4023-175">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="d4023-176">次の例では、レジストリから **Release** の値を確認し、インストールされている .NET Framework 4.5 以降のバージョンを探しています。</span><span class="sxs-lookup"><span data-stu-id="d4023-176">The following example checks the value of the **Release** entry in the registry to find the .NET Framework 4.5 and later versions that are installed:</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="d4023-177">この例では、バージョンのチェックで推奨されている方法に従います。</span><span class="sxs-lookup"><span data-stu-id="d4023-177">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="d4023-178">**Release** エントリの値が、既知のリリース キー値*以上*かどうかを確認しています。</span><span class="sxs-lookup"><span data-stu-id="d4023-178">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="d4023-179">最新バージョンから最も古いバージョンの順にチェックします。</span><span class="sxs-lookup"><span data-stu-id="d4023-179">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
### <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a><span data-ttu-id="d4023-180">PowerShell を使用して最低限必要な .NET Framework のバージョン (4.5 以降) を確認する</span><span class="sxs-lookup"><span data-stu-id="d4023-180">Check for a minimum-required .NET Framework version (4.5 and later) with PowerShell</span></span>

- <span data-ttu-id="d4023-181">PowerShell コマンドを使用し、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** サブキーから **Release** エントリの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="d4023-181">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey.</span></span>

<span data-ttu-id="d4023-182">次の例では、**Release** エントリの値を確認して、.NET Framework 4.6.2 以降がインストールされているかどうかを判断しています。</span><span class="sxs-lookup"><span data-stu-id="d4023-182">The following examples check the value of the **Release** entry to determine whether the .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="d4023-183">このコードでは、インストールされていない場合は、`True` が返され、されている場合は `False` が返されます。</span><span class="sxs-lookup"><span data-stu-id="d4023-183">This code returns `True` if it's installed and `False` otherwise.</span></span>

```PowerShell
# PowerShell 5
 Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' |  Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
 ```

```PowerShell
# PowerShell 4
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

<span data-ttu-id="d4023-184">さまざまな必要最低限の .NET Framework バージョンを確認するには、これらの例の *394802* を [.NET Framework のバージョンの表](#version_table)の **Release** 値と置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d4023-184">To check for a different minimum-required .NET Framework version, replace *394802* in these examples with a **Release** value from the [.NET Framework version table](#version_table).</span></span>

## <a name="find-older-net-framework-versions-182114"></a><span data-ttu-id="d4023-185">.NET Framework の古いバージョンを探す (1 から 4)</span><span class="sxs-lookup"><span data-stu-id="d4023-185">Find older .NET Framework versions (1&#8211;4)</span></span>

<a name="net_a"></a>
### <a name="find-net-framework-versions-182114-in-the-registry"></a><span data-ttu-id="d4023-186">レジストリで .NET Framework バージョン 1 から 4 を探す</span><span class="sxs-lookup"><span data-stu-id="d4023-186">Find .NET Framework versions 1&#8211;4 in the registry</span></span> 
  
1. <span data-ttu-id="d4023-187">**スタート** メニューの **[ファイル名を指定して実行]** を選択し、「*regedit*」と入力し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4023-187">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>
  
    <span data-ttu-id="d4023-188">regedit を実行するには、管理特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="d4023-188">You must have administrative credentials to run regedit.</span></span>  

2. <span data-ttu-id="d4023-189">レジストリ エディターで、次のサブキーを開きます。**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span><span class="sxs-lookup"><span data-stu-id="d4023-189">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span></span>  

    - <span data-ttu-id="d4023-190">.NET Framework バージョン 1.1 から 3.5 では、インストールされている各バージョンは **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** サブキーの下にサブキーとして列挙されます。</span><span class="sxs-lookup"><span data-stu-id="d4023-190">For .NET Framework versions 1.1 through 3.5, each installed version is listed as a subkey under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** subkey.</span></span> <span data-ttu-id="d4023-191">たとえば、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5** です。</span><span class="sxs-lookup"><span data-stu-id="d4023-191">For example, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span></span> <span data-ttu-id="d4023-192">バージョン番号は、バージョン サブキーの **Version** エントリに値として格納されています。</span><span class="sxs-lookup"><span data-stu-id="d4023-192">The version number is stored as a value in the version subkey's **Version** entry.</span></span> 
     
    - <span data-ttu-id="d4023-193">.NET Framework 4 では、**Version** エントリは、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** サブキー、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** サブキーまたは両サブキーの下にあります。</span><span class="sxs-lookup"><span data-stu-id="d4023-193">For .NET Framework 4, the **Version** entry is under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** subkey, the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4023-194">レジストリの **NET Framework セットアップ** フォルダーの先頭はピリオドではありません。</span><span class="sxs-lookup"><span data-stu-id="d4023-194">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="d4023-195">次の図では、.NET Framework 3.5 のサブキーとその **Version** エントリを示しています。</span><span class="sxs-lookup"><span data-stu-id="d4023-195">The following figure shows the subkey and its **Version** entry for the .NET Framework 3.5.</span></span>

    <span data-ttu-id="d4023-196">![.NET Framework 3.5 のレジストリ エントリ。](media/net-4-and-earlier.png ".NET Framework 3.5 以前のバージョン")</span><span class="sxs-lookup"><span data-stu-id="d4023-196">![The registry entry for the .NET Framework 3.5.](media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

<a name="net_c"></a> 
### <a name="find-net-framework-versions-182114-with-code"></a><span data-ttu-id="d4023-197">コードで .NET Framework バージョン 1 から 4 を探す</span><span class="sxs-lookup"><span data-stu-id="d4023-197">Find .NET Framework versions 1&#8211;4 with code</span></span>

- <span data-ttu-id="d4023-198"><xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> クラスを使用して、Windows レジストリの **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** サブキーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d4023-198">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** subkey in the Windows registry.</span></span>

<span data-ttu-id="d4023-199">次の例では、インストールされている .NET Framework のバージョン 1 から 4 が検索されています。</span><span class="sxs-lookup"><span data-stu-id="d4023-199">The following example finds the .NET Framework 1&#8211;4 versions that are installed:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]


## <a name="find-clr-versions"></a><span data-ttu-id="d4023-200">CLR のバージョンを探す</span><span class="sxs-lookup"><span data-stu-id="d4023-200">Find CLR versions</span></span>
  
<a name="clr_a"></a> 
### <a name="find-the-current-clr-version-with-clrverexe"></a><span data-ttu-id="d4023-201">Clrver.exe を使用して現在の CLR のバージョンを調べる</span><span class="sxs-lookup"><span data-stu-id="d4023-201">Find the current CLR version with Clrver.exe</span></span>

<span data-ttu-id="d4023-202">[CLR バージョン ツール (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) を使用して、コンピューターにインストールされている CLR のバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4023-202">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer:</span></span>

- <span data-ttu-id="d4023-203">[Visual Studio 用開発者コマンド プロンプト](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs)で「`clrver`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d4023-203">From a [Developer Command Prompt for Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs), enter `clrver`.</span></span>

    <span data-ttu-id="d4023-204">出力例:</span><span class="sxs-lookup"><span data-stu-id="d4023-204">Sample output:</span></span>

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a> 
### <a name="find-the-current-clr-version-with-the-environment-class"></a><span data-ttu-id="d4023-205">Environment クラスを使用して現在の CLR のバージョンを調べる</span><span class="sxs-lookup"><span data-stu-id="d4023-205">Find the current CLR version with the Environment class</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4023-206">.NET Framework 4.5 以降のバージョンでは、CLR のバージョンの検出に <xref:System.Environment.Version%2A?displayProperty=nameWithType> プロパティを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="d4023-206">For the .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="d4023-207">代わりに、「[コードで .NET Framework バージョン 4.5 以降を探す](#net_d)」の説明に従い、レジストリを照会します。</span><span class="sxs-lookup"><span data-stu-id="d4023-207">Instead, query the registry as described in [Find .NET Framework versions 4.5 and later with code](#net_d).</span></span>

1. <span data-ttu-id="d4023-208"><xref:System.Environment.Version?displayProperty=nameWithType> プロパティを照会し、<xref:System.Version> オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="d4023-208">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span> 

    <span data-ttu-id="d4023-209">返された `System.Version` オブジェクトは、現在コードを実行しているランタイムのバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="d4023-209">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="d4023-210">コンピューターにインストールされている可能性のある、アセンブリのバージョンやランタイムのその他のバージョンは返されません。</span><span class="sxs-lookup"><span data-stu-id="d4023-210">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

    <span data-ttu-id="d4023-211">.NET Framework バージョン 4、4.5、4.5.1、および 4.5.2 の場合は、返される <xref:System.Version> オブジェクトの文字列表現は 4.0.30319.*xxxxx* という形式です。</span><span class="sxs-lookup"><span data-stu-id="d4023-211">For the .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*.</span></span> <span data-ttu-id="d4023-212">.NET Framework 4.6 以降のバージョンの場合は、4.0.30319.42000 という形式です。</span><span class="sxs-lookup"><span data-stu-id="d4023-212">For the .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>    

2. <span data-ttu-id="d4023-213">`Version` オブジェクトを取得したら、次のように照会します。</span><span class="sxs-lookup"><span data-stu-id="d4023-213">After you have the `Version` object, query it as follows:</span></span>

   - <span data-ttu-id="d4023-214">メジャー リリース識別子 (たとえば、バージョン 4.0 の場合の *4*) には、<xref:System.Version.Major%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4023-214">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="d4023-215">マイナー リリース識別子 (たとえば、バージョン 4.0 の場合の *0*) には、<xref:System.Version.Minor%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4023-215">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="d4023-216">バージョンの完全な文字列 (たとえば、*4.0.30319.18010*) には、<xref:System.Version.ToString%2A?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4023-216">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d4023-217">このメソッドでは、コードを実行しているランタイムのバージョンを示す値が 1 つ返されます。</span><span class="sxs-lookup"><span data-stu-id="d4023-217">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="d4023-218">コンピューターにインストールされている可能性のあるアセンブリ バージョンやその他のランタイム バージョンは返されません。</span><span class="sxs-lookup"><span data-stu-id="d4023-218">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>



<span data-ttu-id="d4023-219">次の例では、<xref:System.Environment.Version%2A?displayProperty=nameWithType> プロパティを使用して CLR バージョンの情報を取得しています。</span><span class="sxs-lookup"><span data-stu-id="d4023-219">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="d4023-220">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4023-220">See also</span></span>

- [<span data-ttu-id="d4023-221">方法: インストールされている .NET Framework の更新プログラムを確認する</span><span class="sxs-lookup"><span data-stu-id="d4023-221">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="d4023-222">開発者向けの .NET Framework のインストール</span><span class="sxs-lookup"><span data-stu-id="d4023-222">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="d4023-223">.NET Framework のバージョンおよび依存関係</span><span class="sxs-lookup"><span data-stu-id="d4023-223">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)
