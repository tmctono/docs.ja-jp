---
title: '方法: インストールされている .NET Framework バージョンを確認する'
ms.date: 02/20/2019
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
ms.openlocfilehash: d7661b3ebaa8f29d6d3b2adbc56c405c8f0945f3
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584175"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="15e0f-102">方法: インストールされている .NET Framework バージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="15e0f-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="15e0f-103">ユーザーはコンピューターに複数のバージョンの .NET Framework をインストールして実行できます。</span><span class="sxs-lookup"><span data-stu-id="15e0f-103">Users can install and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="15e0f-104">アプリを開発または配置する場合、どのバージョンの .NET Framework がユーザーのコンピューターにインストールされているかを確認しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="15e0f-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> <span data-ttu-id="15e0f-105">.NET Framework は、個別にバージョン管理される 2 つの主要コンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="15e0f-105">Note that the .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
- <span data-ttu-id="15e0f-106">アプリに機能を提供する型やリソースのコレクションである一連のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="15e0f-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="15e0f-107">.NET Framework とアセンブリは同じバージョン番号を共有します。</span><span class="sxs-lookup"><span data-stu-id="15e0f-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
- <span data-ttu-id="15e0f-108">アプリのコードを管理および実行する共通言語ランタイム (CLR)。</span><span class="sxs-lookup"><span data-stu-id="15e0f-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="15e0f-109">CLR は独自のバージョン番号で識別されます (「[バージョンおよび依存関係](~/docs/framework/migration-guide/versions-and-dependencies.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="15e0f-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  
  
<span data-ttu-id="15e0f-110">コンピューターにインストールされている .NET Framework バージョンの正確な一覧を取得するには、レジストリを表示するか、コードでレジストリを照会することができます。</span><span class="sxs-lookup"><span data-stu-id="15e0f-110">To get an accurate list of the .NET Framework versions installed on a computer, you can view the registry or query the registry in code:</span></span>  
  
 [<span data-ttu-id="15e0f-111">レジストリで .NET Framework バージョン 1 ～ 4 を探す</span><span class="sxs-lookup"><span data-stu-id="15e0f-111">Find .NET Framework versions 1-4 in the registry</span></span>](#net_a)  
 [<span data-ttu-id="15e0f-112">レジストリで .NET Framework バージョン 4.5 以降を探す</span><span class="sxs-lookup"><span data-stu-id="15e0f-112">Find .NET Framework versions 4.5 and later in the registry)</span></span>](#net_b)  
 [<span data-ttu-id="15e0f-113">コードによるレジストリの照会 (バージョン 1 ～ 4)</span><span class="sxs-lookup"><span data-stu-id="15e0f-113">Using code to query the registry (versions 1-4)</span></span>](#net_c)  
 [<span data-ttu-id="15e0f-114">コードによるレジストリの照会 (バージョン 4.5 以降)</span><span class="sxs-lookup"><span data-stu-id="15e0f-114">Using code to query the registry (version 4.5 and later)</span></span>](#net_d)  
 [<span data-ttu-id="15e0f-115">PowerShell を使用したレジストリの照会 (バージョン 4.5 以降)</span><span class="sxs-lookup"><span data-stu-id="15e0f-115">Using PowerShell to query the registry (version 4.5 and later)</span></span>](#ps_a)  

 <span data-ttu-id="15e0f-116">CLR のバージョンを検索するには、ツールまたはコードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="15e0f-116">To find the CLR version, you can use a tool or code:</span></span>  
  
 [<span data-ttu-id="15e0f-117">Clrver ツールの使用</span><span class="sxs-lookup"><span data-stu-id="15e0f-117">Using the Clrver tool</span></span>](#clr_a)  
 [<span data-ttu-id="15e0f-118">コードによる System.Environment クラスの照会</span><span class="sxs-lookup"><span data-stu-id="15e0f-118">Using code to query the System.Environment class</span></span>](#clr_b)  

> [!NOTE]
> <span data-ttu-id="15e0f-119">.NET Framework のバージョンと共通言語ランタイム (CLR) のバージョンの間には違いがあります。</span><span class="sxs-lookup"><span data-stu-id="15e0f-119">There is a difference between the .NET Framework version and the common language runtime (CLR) version.</span></span> <span data-ttu-id="15e0f-120">.NET Framework は、.NET Framework のクラス ライブラリを構成するアセンブリのセットに基づいてバージョン管理されています。</span><span class="sxs-lookup"><span data-stu-id="15e0f-120">The .NET Framework is versioned based on the set of assemblies that form the .NET Framework Class Library.</span></span> <span data-ttu-id="15e0f-121">たとえば、.NET Framework のバージョンには、4.5、4.6.1、および 4.7.2 が含まれます。</span><span class="sxs-lookup"><span data-stu-id="15e0f-121">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span> <span data-ttu-id="15e0f-122">CLR は .NET Framework アプリケーションが実行されるランタイムに基づいてバージョン管理されており、通常、CLR の 1 つのバージョンでは .NET Framework の複数のバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="15e0f-122">The CLR is versioned based on the runtime on which .NET Framework applications execute, and a single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="15e0f-123">CLR バージョン 4.30319.*xxxxx* では .NET Framework バージョン 4 ～ 4.5.2 がサポートされており、CLR バージョン 4.30319.42000 では .NET Framework 4.6 以降がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="15e0f-123">CLR version 4.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2; CLR version 4.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span> <span data-ttu-id="15e0f-124">詳細については、<xref:System.Environment.Version?displayProperty=nameWithType> プロパティを参照してください。</span><span class="sxs-lookup"><span data-stu-id="15e0f-124">For more information, see the <xref:System.Environment.Version?displayProperty=nameWithType> property.</span></span>

 <span data-ttu-id="15e0f-125">.NET Framework の各バージョン用にインストールされている更新プログラムの検出については、「[方法:インストールされている .NET Framework の更新プログラムを確認する](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15e0f-125">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine Which .NET Framework Updates Are Installed](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span></span> <span data-ttu-id="15e0f-126">.NET Framework のインストールの詳細については、「[開発者向けの .NET Framework のインストール](../../../docs/framework/install/guide-for-developers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15e0f-126">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
<a name="net_a"></a>   
## <a name="find-net-framework-versions-1-4-in-the-registry"></a><span data-ttu-id="15e0f-127">レジストリで .NET Framework バージョン 1 ～ 4 を探す</span><span class="sxs-lookup"><span data-stu-id="15e0f-127">Find .NET Framework versions 1-4 in the registry</span></span> 
  
1.  <span data-ttu-id="15e0f-128">**[スタート]** ボタンをクリックし、**[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15e0f-128">On the **Start** menu, choose **Run**.</span></span>  
  
2.  <span data-ttu-id="15e0f-129">**[開く]** ボックスに「**regedit.exe**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="15e0f-129">In the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="15e0f-130">regedit.exe を実行するには、管理特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="15e0f-130">You must have administrative credentials to run regedit.exe.</span></span>  
  
3.  <span data-ttu-id="15e0f-131">レジストリ エディターで、次のサブキーを開きます。</span><span class="sxs-lookup"><span data-stu-id="15e0f-131">In the Registry Editor, open the following subkey:</span></span>  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     <span data-ttu-id="15e0f-132">.NET Framework バージョン 1.1 ～ 3.5 の場合、インストールされているバージョンは、`NDP` サブキーの下のサブキーとして列挙されます。</span><span class="sxs-lookup"><span data-stu-id="15e0f-132">For .NET Framework versions 1.1 through 3.5, the installed versions are listed as subkeys under the `NDP` subkey.</span></span> <span data-ttu-id="15e0f-133">バージョン番号は、バージョン サブキーの **Version** エントリに格納されています。</span><span class="sxs-lookup"><span data-stu-id="15e0f-133">The version number is stored in the version subkey's **Version** entry.</span></span> 
     
     <span data-ttu-id="15e0f-134">.NET Framework 4 の場合は、**Version** エントリは `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client` サブキーと `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full` サブキーのどちらか一方または両方の下にあります。</span><span class="sxs-lookup"><span data-stu-id="15e0f-134">For .NET Framework 4, the **Version** entry is under the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client` subkey, the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full` subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="15e0f-135">レジストリの ".NET Framework セットアップ" フォルダーの先頭はピリオドではありません。</span><span class="sxs-lookup"><span data-stu-id="15e0f-135">The "NET Framework Setup" folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="15e0f-136">次の図では、.NET Framework 3.5 のサブキーと共にその **Version** エントリが示されています。</span><span class="sxs-lookup"><span data-stu-id="15e0f-136">The following figure shows that the subkey for the .NET Framework 3.5 along with its **Version** entry.</span></span>

     <span data-ttu-id="15e0f-137">![.NET Framework 3.5 のレジストリ エントリ。](../../../docs/framework/migration-guide/media/net-4-and-earlier.png ".NET Framework 4 以前のバージョン")</span><span class="sxs-lookup"><span data-stu-id="15e0f-137">![The registry entry for the .NET Framework 3.5.](../../../docs/framework/migration-guide/media/net-4-and-earlier.png ".NET Framework 4 and earlier versions")</span></span>

<a name="net_b"></a> 
## <a name="find-net-framework-versions-45-and-later-in-the-registry"></a><span data-ttu-id="15e0f-138">レジストリで .NET Framework バージョン 4.5 以降を探す</span><span class="sxs-lookup"><span data-stu-id="15e0f-138">Find .NET Framework versions 4.5 and later in the registry</span></span>

1. <span data-ttu-id="15e0f-139">**[スタート]** ボタンをクリックし、**[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15e0f-139">On the **Start** menu, choose **Run**.</span></span>

2. <span data-ttu-id="15e0f-140">**[開く]** ボックスに「**regedit.exe**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="15e0f-140">In the **Open** box, enter **regedit.exe**.</span></span>

     <span data-ttu-id="15e0f-141">regedit.exe を実行するには、管理特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="15e0f-141">You must have administrative credentials to run regedit.exe.</span></span>

3. <span data-ttu-id="15e0f-142">レジストリ エディターで、次のサブキーを開きます。</span><span class="sxs-lookup"><span data-stu-id="15e0f-142">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     <span data-ttu-id="15e0f-143">`Full` サブキーへのパスに `.NET Framework` ではなく `Net Framework` サブキーが含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="15e0f-143">Note that the path to the `Full` subkey includes the subkey `Net Framework` rather than `.NET Framework`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="15e0f-144">`Full` サブキーが存在しない場合は、.NET Framework 4.5 以降がインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="15e0f-144">If the `Full` subkey is not present, then you do not have the .NET Framework 4.5 or later installed.</span></span>

     <span data-ttu-id="15e0f-145">`Release` という名前の DWORD 値を確認します。</span><span class="sxs-lookup"><span data-stu-id="15e0f-145">Check for a DWORD value named `Release`.</span></span> <span data-ttu-id="15e0f-146">`Release` DWORD がある場合は、.NET Framework 4.5 以降がそのコンピューターにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="15e0f-146">The existence of the `Release` DWORD indicates that .NET Framework 4.5 or later has been installed on that computer.</span></span> <span data-ttu-id="15e0f-147">その値は、.NET Framework の特定のバージョンに対応するリリース キーです。</span><span class="sxs-lookup"><span data-stu-id="15e0f-147">Its value is a release key that corresponds to a particular version of .NET Framework.</span></span> <span data-ttu-id="15e0f-148">たとえば、次の図では、`Release` DWORD の値は 378389 で、これは .NET Framework 4.5 のリリース キーです。</span><span class="sxs-lookup"><span data-stu-id="15e0f-148">In the following figure, for example, the value of the `Release` DWORD is 378389, which is the release key for .NET Framework 4.5.</span></span> 

     <span data-ttu-id="15e0f-149">![.NET Framework 4.5 のレジストリ エントリ。](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span><span class="sxs-lookup"><span data-stu-id="15e0f-149">![The registry entry for the .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span></span>

<span data-ttu-id="15e0f-150">次の表では、.NET Framework の各バージョンに対する `Release` DWORD の最小値の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="15e0f-150">The following table lists the minimum value of the `Release` DWORD for each .NET Framework version.</span></span> <span data-ttu-id="15e0f-151">これらの値は次のように使用できます。</span><span class="sxs-lookup"><span data-stu-id="15e0f-151">You can use these values as follows:</span></span>

- <span data-ttu-id="15e0f-152">.NET Framework の最小バージョンが存在するかどうかを確認するには、レジストリの `Release` DWORD 値が表で示されている値と "*等しいかそれより大きい*" かどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="15e0f-152">To determine whether a minimum .NET Framework version is present, test whether the `Release` DWORD value found in the registry is *greater than or equal to* the value listed in the table.</span></span> <span data-ttu-id="15e0f-153">たとえば、アプリケーションで .NET Framework 4.7 以降が必要な場合は、最小のリリース キー値 460798 について調べます。</span><span class="sxs-lookup"><span data-stu-id="15e0f-153">For example, if your application requires .NET Framework 4.7 or later, you would test for a minimum release key value of 460798.</span></span>

- <span data-ttu-id="15e0f-154">複数のバージョンについて調べるには、.NET Framework の最新のバージョンから始めて、以前のバージョンに順番に遡りながら調べます。</span><span class="sxs-lookup"><span data-stu-id="15e0f-154">To test for multiple versions, begin with the latest .NET Framework version, and then test for each successive earlier version.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

|<span data-ttu-id="15e0f-155">.NET Framework のバージョン</span><span class="sxs-lookup"><span data-stu-id="15e0f-155">.NET Framework Version</span></span>|<span data-ttu-id="15e0f-156">Release DWORD の値</span><span class="sxs-lookup"><span data-stu-id="15e0f-156">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="15e0f-157">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="15e0f-157">.NET Framework 4.5</span></span>|<span data-ttu-id="15e0f-158">378389</span><span class="sxs-lookup"><span data-stu-id="15e0f-158">378389</span></span>|
|<span data-ttu-id="15e0f-159">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="15e0f-159">.NET Framework 4.5.1</span></span>|<span data-ttu-id="15e0f-160">378675</span><span class="sxs-lookup"><span data-stu-id="15e0f-160">378675</span></span>|
|<span data-ttu-id="15e0f-161">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="15e0f-161">.NET Framework 4.5.2</span></span>|<span data-ttu-id="15e0f-162">379893</span><span class="sxs-lookup"><span data-stu-id="15e0f-162">379893</span></span>|
|<span data-ttu-id="15e0f-163">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="15e0f-163">.NET Framework 4.6</span></span>|<span data-ttu-id="15e0f-164">393295</span><span class="sxs-lookup"><span data-stu-id="15e0f-164">393295</span></span>|
|<span data-ttu-id="15e0f-165">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="15e0f-165">.NET Framework 4.6.1</span></span>|<span data-ttu-id="15e0f-166">394254</span><span class="sxs-lookup"><span data-stu-id="15e0f-166">394254</span></span>|
|<span data-ttu-id="15e0f-167">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="15e0f-167">.NET Framework 4.6.2</span></span>|<span data-ttu-id="15e0f-168">394802</span><span class="sxs-lookup"><span data-stu-id="15e0f-168">394802</span></span>|
|<span data-ttu-id="15e0f-169">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="15e0f-169">.NET Framework 4.7</span></span>|<span data-ttu-id="15e0f-170">460798</span><span class="sxs-lookup"><span data-stu-id="15e0f-170">460798</span></span>|
|<span data-ttu-id="15e0f-171">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="15e0f-171">.NET Framework 4.7.1</span></span>|<span data-ttu-id="15e0f-172">461308</span><span class="sxs-lookup"><span data-stu-id="15e0f-172">461308</span></span>|
|<span data-ttu-id="15e0f-173">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="15e0f-173">.NET Framework 4.7.2</span></span>|<span data-ttu-id="15e0f-174">461808</span><span class="sxs-lookup"><span data-stu-id="15e0f-174">461808</span></span>|

<span data-ttu-id="15e0f-175">Windows オペレーティング システムの特定のバージョンに対する .NET Framework のリリース キーの完全な表については、「[.NET Framework のリリース キーと Windows オペレーティング システムのバージョン](release-keys-and-os-versions.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="15e0f-175">For a complete table of release keys for the .NET Framework for specific Windows operating system versions, see [.NET Framework release keys and Windows operating system versions](release-keys-and-os-versions.md).</span></span>

<a name="net_c"></a> 
## <a name="find-net-framework-versions-1-4-with-code"></a><span data-ttu-id="15e0f-176">コードで .NET Framework バージョン 1 ～ 4 を探す</span><span class="sxs-lookup"><span data-stu-id="15e0f-176">Find .NET Framework versions 1-4 with code</span></span>

- <span data-ttu-id="15e0f-177">Windows レジストリ内の `HKEY_LOCAL_MACHINE` ブランチの下にある `Software\Microsoft\NET Framework Setup\NDP\` サブキーにアクセスするには、<xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="15e0f-177">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the `Software\Microsoft\NET Framework Setup\NDP\` subkey under `HKEY_LOCAL_MACHINE` branch in the Windows registry.</span></span>

     <span data-ttu-id="15e0f-178">このクエリの例を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="15e0f-178">The following code shows an example of this query.</span></span>

    > [!NOTE]
    > <span data-ttu-id="15e0f-179">このコードでは、.NET Framework 4.5 以降を検出する方法は示されていません。</span><span class="sxs-lookup"><span data-stu-id="15e0f-179">This code does not show how to detect .NET Framework 4.5 or later.</span></span> <span data-ttu-id="15e0f-180">前のセクションで説明したように、これらのバージョンを検出するには、`Release` DWORD を確認してください。</span><span class="sxs-lookup"><span data-stu-id="15e0f-180">Check the `Release` DWORD to detect those versions, as described in the previous section.</span></span> <span data-ttu-id="15e0f-181">.NET Framework 4.5 以降のバージョンを検出するコードについては、この記事の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="15e0f-181">For code that detects .NET Framework 4.5 or later versions, see the next section in this article.</span></span>

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

<a name="net_d"></a> 
## <a name="find-net-framework-versions-45-and-later-with-code"></a><span data-ttu-id="15e0f-182">コードで .NET Framework バージョン 4.5 以降を探す</span><span class="sxs-lookup"><span data-stu-id="15e0f-182">Find .NET Framework versions 4.5 and later with code</span></span>

1. <span data-ttu-id="15e0f-183">`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` キーに `Release` DWORD がある場合は、.NET Framework 4.5 以降がコンピューターにインストールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="15e0f-183">The existence of the `Release` DWORD in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key indicates that the .NET Framework 4.5 or later is installed on a computer.</span></span> <span data-ttu-id="15e0f-184">キーワードの値はインストールされているバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="15e0f-184">The value of the keyword indicates the installed version.</span></span> <span data-ttu-id="15e0f-185">このキーワードを調べるには、<xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> および <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> メソッドを使用して、Windows レジストリのサブキーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="15e0f-185">To check this keyword, use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the subkey in the Windows registry.</span></span>

2. <span data-ttu-id="15e0f-186">`Release` キーワードの値を確認して、インストールされているバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="15e0f-186">Check the value of the `Release` keyword to determine the installed version.</span></span> <span data-ttu-id="15e0f-187">上位互換性を確認するには、「[レジストリで .NET Framework バージョン 4.5 以降を探す](#net_b)」セクションの表で示されている値と等しいかそれより大きい値を調べます。</span><span class="sxs-lookup"><span data-stu-id="15e0f-187">To be forward-compatible, you can check for a value greater than or equal to the value listed in the table in the [Find .NET Framework versions 4.5 and later in the registry](#net_b) section.</span></span>

<span data-ttu-id="15e0f-188">レジストリの `Release` 値を確認して .NET Framework 4.5 以降のバージョンがインストールされているかどうかを判断する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="15e0f-188">The following example checks the `Release` value in the registry to determine whether .NET Framework 4.5 or a later version is installed.</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="15e0f-189">この例では、バージョンのチェックで推奨されている方法に従います。</span><span class="sxs-lookup"><span data-stu-id="15e0f-189">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="15e0f-190">`Release` エントリの値が既知のリリース キー値*以上*かどうかをチェックします。</span><span class="sxs-lookup"><span data-stu-id="15e0f-190">It checks whether the value of the `Release` entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="15e0f-191">最新バージョンから最も古いバージョンの順にチェックします。</span><span class="sxs-lookup"><span data-stu-id="15e0f-191">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
## <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a><span data-ttu-id="15e0f-192">PowerShell を使用して最低限必要な .NET Framework のバージョン (4.5 以降) を確認する</span><span class="sxs-lookup"><span data-stu-id="15e0f-192">Check for a minimum required .NET Framework version (4.5 and later) with PowerShell</span></span>

<span data-ttu-id="15e0f-193">次の例では、`Release` キーワードの値を確認して、.NET Framework 4.6.2 以降がインストールされているかどうかを判断します (インストールされている場合は `True` が返され、それ以外の場合は `False` が返されます)。</span><span class="sxs-lookup"><span data-stu-id="15e0f-193">The following example checks the value of the `Release` keyword to determine whether .NET Framework 4.6.2 or higher is installed (returning `True` if it is and `False` otherwise).</span></span>

    ```PowerShell
    # PowerShell 5
    Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' | Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
    ```

    ```PowerShell
    # PowerShell 4
    (Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -gt 394802
    ```

    You can replace `394802` in the previous example with another value from the following table in the [Find .NET Framework versions 4.5 and later in the registry](#net_b) section to check for a different minimum required .NET Framework version.
  
<a name="clr_a"></a> 
## <a name="find-the-current-clr-version-with-clrverexe"></a><span data-ttu-id="15e0f-194">Clrver.exe を使用して現在の CLR のバージョンを調べる</span><span class="sxs-lookup"><span data-stu-id="15e0f-194">Find the current CLR version with Clrver.exe</span></span>

<span data-ttu-id="15e0f-195">CLR バージョン ツール (Clrver.exe) を使用して、コンピューターにインストールされている共通言語ランタイムのバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="15e0f-195">Use the CLR Version Tool (Clrver.exe) to determine which versions of the common language runtime are installed on a computer.</span></span>

<span data-ttu-id="15e0f-196">Visual Studio 用開発者コマンド プロンプトで「`clrver`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="15e0f-196">From a Developer Command Prompt for Visual Studio, enter `clrver`.</span></span> <span data-ttu-id="15e0f-197">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="15e0f-197">This command produces output similar to the following:</span></span>

```console
Versions installed on the machine:
v2.0.50727
v4.0.30319
```

<span data-ttu-id="15e0f-198">このツールの使用については、「[Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15e0f-198">For more information about using this tool, see [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span></span>

<a name="clr_b"></a> 
## <a name="find-the-current-clr-version-with-the-environment-class"></a><span data-ttu-id="15e0f-199">Environment クラスを使用して現在の CLR のバージョンを調べる</span><span class="sxs-lookup"><span data-stu-id="15e0f-199">Find the current CLR version with the Environment class</span></span>

<span data-ttu-id="15e0f-200"><xref:System.Environment.Version?displayProperty=nameWithType> プロパティの値を取得して <xref:System.Version> オブジェクトを取得し、現在コードを実行しているランタイムのバージョンを識別できます。</span><span class="sxs-lookup"><span data-stu-id="15e0f-200">You can retrieve the value of the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object that identifies the version of the runtime that is currently executing the code.</span></span> <span data-ttu-id="15e0f-201">このプロパティでは、現在コードを実行しているランタイムのバージョンを表す単一の値が返されますが、アセンブリのバージョンやコンピューターにインストールされている可能性があるランタイムの他のバージョンは返されません。メジャー リリースの識別子 (バージョン 4.0 の "4" など) を取得するには <xref:System.Version.Major%2A?displayProperty=nameWithType> プロパティを、マイナー リリースの識別子 (バージョン 4.0 の "0" など) を取得するには <xref:System.Version.Minor%2A?displayProperty=nameWithType> プロパティを、バージョン文字列全体 (次のコードに示すような "4.0.30319.18010" など) を取得するには <xref:System.Version.ToString%2A?displayProperty=nameWithType> メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="15e0f-201">This property returns a single value that reflects the version of the runtime that is currently executing the code; it does not return assembly versions or other versions of the runtime that may have been installed on the computer.You can use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property to get the major release identifier (for example, "4" for version 4.0), the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property to get the minor release identifier (for example, "0" for version 4.0), or the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method to get the entire version string (for example, "4.0.30319.18010", as shown in the following code).</span></span> 

<span data-ttu-id="15e0f-202">.NET Framework バージョン 4、4.5、4.5.1、および 4.5.2 の場合は、<xref:System.Environment.Version%2A?displayProperty=nameWithType> プロパティから返される <xref:System.Version> オブジェクトの文字列表現が `4.0.30319.xxxxx` という形式になっています。</span><span class="sxs-lookup"><span data-stu-id="15e0f-202">For the .NET Framework Versions 4, 4.5, 4.5.1, and 4.5.2, the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property returns a <xref:System.Version> object whose string representation has the form `4.0.30319.xxxxx`.</span></span> <span data-ttu-id="15e0f-203">.NET Framework 4.6 以降の場合は、`4.0.30319.42000` という形式です。</span><span class="sxs-lookup"><span data-stu-id="15e0f-203">For the .NET Framework 4.6 and later, it has the form `4.0.30319.42000`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="15e0f-204">.NET Framework 4.5 以降の場合、ランタイムのバージョンの検出に <xref:System.Environment.Version%2A?displayProperty=nameWithType> プロパティを使用することは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="15e0f-204">For the .NET Framework 4.5 and later, we do not recommend using the  <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the runtime.</span></span> <span data-ttu-id="15e0f-205">代わりに、この記事で前述した「[コードでレジストリを照会して .NET Framework のバージョンを検索するには (.NET Framework 4.5 以降)](#net_d)」に従って、レジストリを紹介することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15e0f-205">Instead, we recommend that you query the registry, as described in the [To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)](#net_d) section earlier in this article.</span></span>

<span data-ttu-id="15e0f-206">次の例では、<xref:System.Environment.Version%2A?displayProperty=nameWithType> プロパティを使用してランタイム バージョンの情報を取得しています。</span><span class="sxs-lookup"><span data-stu-id="15e0f-206">The following example used the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve runtime version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="15e0f-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="15e0f-207">See also</span></span>

- [<span data-ttu-id="15e0f-208">方法: インストールされている .NET Framework の更新プログラムを確認する</span><span class="sxs-lookup"><span data-stu-id="15e0f-208">How to: Determine Which .NET Framework Updates Are Installed</span></span>](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="15e0f-209">開発者向けの .NET Framework のインストール</span><span class="sxs-lookup"><span data-stu-id="15e0f-209">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)
- [<span data-ttu-id="15e0f-210">バージョンおよび依存関係</span><span class="sxs-lookup"><span data-stu-id="15e0f-210">Versions and Dependencies</span></span>](~/docs/framework/migration-guide/versions-and-dependencies.md)
