---
title: インストールされている .NET Framework バージョンを確認する
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
ms.openlocfilehash: b860aac01780acb67c53e822eff478b78198996b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738190"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="f388d-102">方法: インストールされている .NET Framework バージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="f388d-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="f388d-103">ユーザーはコンピューターに複数のバージョンの .NET Framework を[インストール](../install/index.md)して実行できます。</span><span class="sxs-lookup"><span data-stu-id="f388d-103">Users can [install](../install/index.md) and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="f388d-104">アプリを開発または配置する場合、どのバージョンの .NET Framework がユーザーのコンピューターにインストールされているかを確認しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f388d-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span>

<span data-ttu-id="f388d-105">.NET Framework は、個別にバージョン管理される 2 つの主要コンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="f388d-105">The .NET Framework consists of two main components, which are versioned separately:</span></span>

- <span data-ttu-id="f388d-106">アプリに機能を提供する型やリソースのコレクションである一連のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="f388d-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="f388d-107">.NET Framework とアセンブリは同じバージョン番号を共有します。</span><span class="sxs-lookup"><span data-stu-id="f388d-107">The .NET Framework and assemblies share the same version number.</span></span>

- <span data-ttu-id="f388d-108">アプリのコードを管理および実行する共通言語ランタイム (CLR)。</span><span class="sxs-lookup"><span data-stu-id="f388d-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="f388d-109">CLR は独自のバージョン番号で識別されます (「[バージョンおよび依存関係](versions-and-dependencies.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f388d-109">The CLR is identified by its own version number (see [Versions and dependencies](versions-and-dependencies.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="f388d-110">新しい各バージョンの .NET Framework には、1 つ前のバージョンの機能が含まれると共に、新機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="f388d-110">Each new version of the .NET Framework retains features from the previous versions and adds new features.</span></span> <span data-ttu-id="f388d-111">同じコンピューターに .NET Framework の複数のバージョンを同時に読み込むことができます。これは、以前のバージョンをアンインストールせずに、.NET Framework をインストールできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f388d-111">You can load multiple versions of the .NET Framework on a single computer at the same time, which means that you can install the .NET Framework without having to uninstall previous versions.</span></span> <span data-ttu-id="f388d-112">一般に、以前の .NET Framework のバージョンはアンインストールしないでください。使用するアプリケーションが特定のバージョンに依存しており、そのバージョンが削除されると破損してしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f388d-112">In general, you shouldn't uninstall previous versions of the .NET Framework, because an application you use may depend on a specific version and may break if that version is removed.</span></span>
>
> <span data-ttu-id="f388d-113">.NET Framework のバージョンと CLR のバージョンの間には違いがあります。</span><span class="sxs-lookup"><span data-stu-id="f388d-113">There is a difference between the .NET Framework version and the CLR version:</span></span>
>
> - <span data-ttu-id="f388d-114">.NET Framework は、.NET Framework のクラス ライブラリを構成するアセンブリのセットに基づいてバージョン管理されています。</span><span class="sxs-lookup"><span data-stu-id="f388d-114">The .NET Framework version is based on the set of assemblies that form the .NET Framework class library.</span></span> <span data-ttu-id="f388d-115">たとえば、.NET Framework のバージョンには、4.5、4.6.1、および 4.7.2 が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f388d-115">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span>
> - <span data-ttu-id="f388d-116">CLR は、.NET Framework アプリケーションが実行されているランタイムに基づいてバージョン管理されています。</span><span class="sxs-lookup"><span data-stu-id="f388d-116">The CLR version is based on the runtime on which .NET Framework applications execute.</span></span> <span data-ttu-id="f388d-117">1 つの CLR バージョンは、通常複数の NET Framework バージョンをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f388d-117">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="f388d-118">たとえば、CLR バージョン 4.0.30319.*xxxxx* (ここでの *xxxxx* は 42000 より小さい) は .NET Framework バージョン 4 から 4.5.2 をサポートしており、CLR バージョン 4.0.30319.42000 では .NET Framework 4.6 以降をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f388d-118">For example, CLR version 4.0.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2, where *xxxxx* is less than 42000, and CLR version 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span>
>
> <span data-ttu-id="f388d-119">バージョンの詳細については、「[.NET Framework のバージョンおよび依存関係](versions-and-dependencies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f388d-119">For more information about versions, see [.NET Framework versions and dependencies](versions-and-dependencies.md).</span></span>

<span data-ttu-id="f388d-120">レジストリには、コンピューターにインストールされている .NET Framework のバージョンの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f388d-120">The registry contains a list of the .NET Framework versions installed on a computer.</span></span> <span data-ttu-id="f388d-121">レジストリを確認するには、レジストリ エディターを使用するか、次のようにコードで照会します。</span><span class="sxs-lookup"><span data-stu-id="f388d-121">You can either use the Registry Editor to view the registry or query it with code:</span></span>

- <span data-ttu-id="f388d-122">.NET Framework の新しいバージョンを探す (4.5 以降):</span><span class="sxs-lookup"><span data-stu-id="f388d-122">Find newer .NET Framework versions (4.5 and later):</span></span>

  - [<span data-ttu-id="f388d-123">レジストリ エディターを使用し .NET Framework のバージョンを探す</span><span class="sxs-lookup"><span data-stu-id="f388d-123">Use the Registry Editor to find .NET Framework versions</span></span>](#net_b)
  - [<span data-ttu-id="f388d-124">コードを使用し .NET Framework のバージョンのレジストリを照会する</span><span class="sxs-lookup"><span data-stu-id="f388d-124">Use code to query the registry for .NET Framework versions</span></span>](#net_d)
  - [<span data-ttu-id="f388d-125">PowerShell を使用し .NET Framework のバージョンのレジストリを照会する</span><span class="sxs-lookup"><span data-stu-id="f388d-125">Use PowerShell to query the registry for .NET Framework versions</span></span>](#ps_a)

- <span data-ttu-id="f388d-126">.NET Framework の以前のバージョンを探す (1 から 4):</span><span class="sxs-lookup"><span data-stu-id="f388d-126">Find older .NET Framework versions (1 through 4):</span></span>

  - [<span data-ttu-id="f388d-127">レジストリ エディターを使用し .NET Framework のバージョンを探す</span><span class="sxs-lookup"><span data-stu-id="f388d-127">Use the Registry Editor to find .NET Framework versions</span></span>](#net_a)
  - [<span data-ttu-id="f388d-128">コードを使用し .NET Framework のバージョンのレジストリを照会する</span><span class="sxs-lookup"><span data-stu-id="f388d-128">Use code to query the registry for .NET Framework versions</span></span>](#net_c)

<span data-ttu-id="f388d-129">コンピューターにインストールされている CLR のバージョンの一覧を取得するには、次のツールまたはコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="f388d-129">To get a list of the CLR versions installed on a computer, use a tool or code:</span></span>

- [<span data-ttu-id="f388d-130">Clrver ツールを使用する</span><span class="sxs-lookup"><span data-stu-id="f388d-130">Use the Clrver tool</span></span>](#clr_a)
- [<span data-ttu-id="f388d-131">コードを使用して Environment クラスを照会する</span><span class="sxs-lookup"><span data-stu-id="f388d-131">Use code to query the Environment class</span></span>](#clr_b)

<span data-ttu-id="f388d-132">.NET Framework の各バージョン用にインストールされている更新プログラムの検出については、「[方法:インストールされている .NET Framework の更新プログラムを確認する](how-to-determine-which-net-framework-updates-are-installed.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f388d-132">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span>

## <a name="find-newer-net-framework-versions-45-and-later"></a><span data-ttu-id="f388d-133">.NET Framework の新しいバージョンを探す (4.5 以降)</span><span class="sxs-lookup"><span data-stu-id="f388d-133">Find newer .NET Framework versions (4.5 and later)</span></span>

<span data-ttu-id="f388d-134">レジストリ エディターを使用して、レジストリ内のバージョン情報を検索したり、プログラムでレジストリを照会したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f388d-134">You can use Registry Editor to find version information in the registry, or you can query the registry programmatically.</span></span>

<a name="net_b"></a>

### <a name="use-registry-editor"></a><span data-ttu-id="f388d-135">レジストリ エディターを使用する</span><span class="sxs-lookup"><span data-stu-id="f388d-135">Use Registry Editor</span></span>

1. <span data-ttu-id="f388d-136">**スタート** メニューの **[ファイル名を指定して実行]** を選択し、「*regedit*」と入力し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f388d-136">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

     <span data-ttu-id="f388d-137">regedit を実行するには、管理特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="f388d-137">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="f388d-138">レジストリ エディターで、次のサブキーを開きます。**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**</span><span class="sxs-lookup"><span data-stu-id="f388d-138">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span></span> <span data-ttu-id="f388d-139">**Full** サブキーが存在しない場合は、.NET Framework 4.5 以降はインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="f388d-139">If the **Full** subkey isn't present, then you don't have the .NET Framework 4.5 or later installed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f388d-140">レジストリの **NET Framework セットアップ** フォルダーの先頭はピリオドでは "*ありません*"。</span><span class="sxs-lookup"><span data-stu-id="f388d-140">The **NET Framework Setup** folder in the registry does *not* begin with a period.</span></span>

3. <span data-ttu-id="f388d-141">**Release** という DWORD のエントリを探します。</span><span class="sxs-lookup"><span data-stu-id="f388d-141">Check for a DWORD entry named **Release**.</span></span> <span data-ttu-id="f388d-142">それがある場合、.NET Framework 4.5 以降がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="f388d-142">If it exists, then you have .NET Framework 4.5 or later installed.</span></span> <span data-ttu-id="f388d-143">その値は、.NET Framework の特定のバージョンのリリース キーです。</span><span class="sxs-lookup"><span data-stu-id="f388d-143">Its value is a release key that corresponds to a particular version of the .NET Framework.</span></span> <span data-ttu-id="f388d-144">たとえば、次の図では、**Release** エントリの値は 378389 で、これは .NET Framework 4.5 のリリース キーです。</span><span class="sxs-lookup"><span data-stu-id="f388d-144">In the following figure, for example, the value of the **Release** entry is 378389, which is the release key for .NET Framework 4.5.</span></span>

   <span data-ttu-id="f388d-145">![.NET Framework 4.5 のレジストリ エントリ](./media/clr-installdir.png ".NET Framework 4.5 のレジストリ エントリ。")</span><span class="sxs-lookup"><span data-stu-id="f388d-145">![Registry entry for the .NET Framework 4.5](./media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span></span>

<span data-ttu-id="f388d-146">次の表は、.NET Framework 4.5 以降のバージョンに対する個々のオペレーティング システムでの **Release** DWORD 値の一覧です。</span><span class="sxs-lookup"><span data-stu-id="f388d-146">The following table lists the value of the **Release** DWORD on individual operating systems for .NET Framework 4.5 and later versions.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|<span data-ttu-id="f388d-147">.NET Framework のバージョン</span><span class="sxs-lookup"><span data-stu-id="f388d-147">.NET Framework version</span></span>|<span data-ttu-id="f388d-148">Release DWORD の値</span><span class="sxs-lookup"><span data-stu-id="f388d-148">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="f388d-149">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="f388d-149">.NET Framework 4.5</span></span>|<span data-ttu-id="f388d-150">すべての Windows オペレーティング システム:378389</span><span class="sxs-lookup"><span data-stu-id="f388d-150">All Windows operating systems: 378389</span></span>|
|<span data-ttu-id="f388d-151">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="f388d-151">.NET Framework 4.5.1</span></span>|<span data-ttu-id="f388d-152">Windows 8.1 および Windows Server 2012 R2:378675</span><span class="sxs-lookup"><span data-stu-id="f388d-152">On Windows 8.1 and Windows Server 2012 R2: 378675</span></span><br /><span data-ttu-id="f388d-153">他のすべての Windows オペレーティング システム:378758</span><span class="sxs-lookup"><span data-stu-id="f388d-153">On all other Windows operating systems: 378758</span></span>|
|<span data-ttu-id="f388d-154">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="f388d-154">.NET Framework 4.5.2</span></span>|<span data-ttu-id="f388d-155">すべての Windows オペレーティング システム:379893</span><span class="sxs-lookup"><span data-stu-id="f388d-155">All Windows operating systems: 379893</span></span>|
|<span data-ttu-id="f388d-156">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="f388d-156">.NET Framework 4.6</span></span>|<span data-ttu-id="f388d-157">Windows 10:393295</span><span class="sxs-lookup"><span data-stu-id="f388d-157">On Windows 10: 393295</span></span><br /><span data-ttu-id="f388d-158">他のすべての Windows オペレーティング システム:393297</span><span class="sxs-lookup"><span data-stu-id="f388d-158">On all other Windows operating systems: 393297</span></span>|
|<span data-ttu-id="f388d-159">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="f388d-159">.NET Framework 4.6.1</span></span>|<span data-ttu-id="f388d-160">Windows 10 November Update システム:394254</span><span class="sxs-lookup"><span data-stu-id="f388d-160">On Windows 10 November Update systems: 394254</span></span><br /><span data-ttu-id="f388d-161">他のすべての Windows オペレーティング システム (Windows 10 を含む):394271</span><span class="sxs-lookup"><span data-stu-id="f388d-161">On all other Windows operating systems (including Windows 10): 394271</span></span>|
|<span data-ttu-id="f388d-162">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="f388d-162">.NET Framework 4.6.2</span></span>|<span data-ttu-id="f388d-163">Windows 10 Anniversary Update および Windows Server 2016 の場合:394802</span><span class="sxs-lookup"><span data-stu-id="f388d-163">On Windows 10 Anniversary Update and Windows Server 2016: 394802</span></span><br /><span data-ttu-id="f388d-164">他のすべての Windows オペレーティング システム (他の Windows 10 オペレーティング システムを含む):394806</span><span class="sxs-lookup"><span data-stu-id="f388d-164">On all other Windows operating systems (including other Windows 10 operating systems): 394806</span></span>|
|<span data-ttu-id="f388d-165">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="f388d-165">.NET Framework 4.7</span></span>|<span data-ttu-id="f388d-166">Windows 10 Creators Update:460798</span><span class="sxs-lookup"><span data-stu-id="f388d-166">On Windows 10 Creators Update: 460798</span></span><br /><span data-ttu-id="f388d-167">他のすべての Windows オペレーティング システム (他の Windows 10 オペレーティング システムを含む):460805</span><span class="sxs-lookup"><span data-stu-id="f388d-167">On all other Windows operating systems (including other Windows 10 operating systems): 460805</span></span>|
|<span data-ttu-id="f388d-168">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="f388d-168">.NET Framework 4.7.1</span></span>|<span data-ttu-id="f388d-169">Windows 10 Fall Creators Update および Windows Server バージョン 1709:461308</span><span class="sxs-lookup"><span data-stu-id="f388d-169">On Windows 10 Fall Creators Update and Windows Server, version 1709: 461308</span></span><br/><span data-ttu-id="f388d-170">他のすべての Windows オペレーティング システム (他の Windows 10 オペレーティング システムを含む):461310</span><span class="sxs-lookup"><span data-stu-id="f388d-170">On all other Windows operating systems (including other Windows 10 operating systems): 461310</span></span>|
|<span data-ttu-id="f388d-171">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="f388d-171">.NET Framework 4.7.2</span></span>|<span data-ttu-id="f388d-172">Windows 10 April 2018 Update および Windows Server バージョン 1803:461808</span><span class="sxs-lookup"><span data-stu-id="f388d-172">On Windows 10 April 2018 Update and Windows Server, version 1803: 461808</span></span><br/><span data-ttu-id="f388d-173">Windows 10 April 2018 Update および Windows Server バージョン 1803 以外のすべての Windows オペレーティング システム:461814</span><span class="sxs-lookup"><span data-stu-id="f388d-173">On all Windows operating systems other than Windows 10 April 2018 Update and Windows Server, version 1803: 461814</span></span>|
|<span data-ttu-id="f388d-174">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="f388d-174">.NET Framework 4.8</span></span>|<span data-ttu-id="f388d-175">Windows 10 May 2019 Update および Windows 10 November 2019 Update:528040</span><span class="sxs-lookup"><span data-stu-id="f388d-175">On Windows 10 May 2019 Update and Windows 10 November 2019 Update: 528040</span></span><br/><span data-ttu-id="f388d-176">他のすべての Windows オペレーティング システム (他の Windows 10 オペレーティング システムを含む):528049</span><span class="sxs-lookup"><span data-stu-id="f388d-176">On all other Windows operating systems (including other Windows 10 operating systems): 528049</span></span>|

#### <a name="specific-version"></a><span data-ttu-id="f388d-177">特定のバージョン</span><span class="sxs-lookup"><span data-stu-id="f388d-177">Specific version</span></span>

<span data-ttu-id="f388d-178">*特定*のバージョンの .NET Framework が特定のバージョンの Windows オペレーティング システムにインストールされているかどうかを判断するには、**Release** DWORD 値が表に記載されている値と "*同じ*" であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f388d-178">To determine whether a *specific* version of the .NET Framework is installed on a particular version of the Windows operating system, test whether the **Release** DWORD value is *equal to* the value listed in the table.</span></span> <span data-ttu-id="f388d-179">たとえば、.NET Framework 4.6 が Windows 10 システム上に存在するかどうかを判断するには、**Release** 値が 393295 と "*同じ*" であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f388d-179">For example, to determine whether .NET Framework 4.6 is present on a Windows 10 system, test for the a **Release** value that is *equal to* 393295.</span></span>

#### <a name="minimum-version"></a><span data-ttu-id="f388d-180">最小バージョン</span><span class="sxs-lookup"><span data-stu-id="f388d-180">Minimum version</span></span>

<span data-ttu-id="f388d-181">.NET Framework の*最小*バージョンが存在するかどうかを判断するには、前の表から、そのバージョンの最小の**RELEASE** DWORD 値を使用します</span><span class="sxs-lookup"><span data-stu-id="f388d-181">To determine whether a *minimum* version of the .NET Framework is present, use the smallest **RELEASE** DWORD value for that version from the previous table.</span></span> <span data-ttu-id="f388d-182">(便宜上、次の表にも最小値が記載されています)。</span><span class="sxs-lookup"><span data-stu-id="f388d-182">(For convenience, the minimum values are also listed in the table that follows.)</span></span>

<span data-ttu-id="f388d-183">たとえば、アプリケーションが .NET Framework 4.8 以降のバージョンで実行されている場合、**RELEASE** DWORD 値が 528040 "*以上*" であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f388d-183">For example, if your application runs under .NET Framework 4.8 or a later version, test for a **RELEASE** DWORD value that is *greater than or equal to* 528040.</span></span>

|<span data-ttu-id="f388d-184">.NET Framework のバージョン</span><span class="sxs-lookup"><span data-stu-id="f388d-184">.NET Framework version</span></span>|<span data-ttu-id="f388d-185">Release DWORD の最小値</span><span class="sxs-lookup"><span data-stu-id="f388d-185">Minimum value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="f388d-186">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="f388d-186">.NET Framework 4.5</span></span>|<span data-ttu-id="f388d-187">378389</span><span class="sxs-lookup"><span data-stu-id="f388d-187">378389</span></span>|
|<span data-ttu-id="f388d-188">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="f388d-188">.NET Framework 4.5.1</span></span>|<span data-ttu-id="f388d-189">378675</span><span class="sxs-lookup"><span data-stu-id="f388d-189">378675</span></span>|
|<span data-ttu-id="f388d-190">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="f388d-190">.NET Framework 4.5.2</span></span>|<span data-ttu-id="f388d-191">379893</span><span class="sxs-lookup"><span data-stu-id="f388d-191">379893</span></span>|
|<span data-ttu-id="f388d-192">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="f388d-192">.NET Framework 4.6</span></span>|<span data-ttu-id="f388d-193">393295</span><span class="sxs-lookup"><span data-stu-id="f388d-193">393295</span></span>|
|<span data-ttu-id="f388d-194">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="f388d-194">.NET Framework 4.6.1</span></span>|<span data-ttu-id="f388d-195">394254</span><span class="sxs-lookup"><span data-stu-id="f388d-195">394254</span></span>|
|<span data-ttu-id="f388d-196">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="f388d-196">.NET Framework 4.6.2</span></span>|<span data-ttu-id="f388d-197">394802</span><span class="sxs-lookup"><span data-stu-id="f388d-197">394802</span></span>|
|<span data-ttu-id="f388d-198">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="f388d-198">.NET Framework 4.7</span></span>|<span data-ttu-id="f388d-199">460798</span><span class="sxs-lookup"><span data-stu-id="f388d-199">460798</span></span>|
|<span data-ttu-id="f388d-200">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="f388d-200">.NET Framework 4.7.1</span></span>|<span data-ttu-id="f388d-201">461308</span><span class="sxs-lookup"><span data-stu-id="f388d-201">461308</span></span>|
|<span data-ttu-id="f388d-202">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="f388d-202">.NET Framework 4.7.2</span></span>|<span data-ttu-id="f388d-203">461808</span><span class="sxs-lookup"><span data-stu-id="f388d-203">461808</span></span>|
|<span data-ttu-id="f388d-204">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="f388d-204">.NET Framework 4.8</span></span>|<span data-ttu-id="f388d-205">528040</span><span class="sxs-lookup"><span data-stu-id="f388d-205">528040</span></span>|

#### <a name="multiple-versions"></a><span data-ttu-id="f388d-206">複数のバージョン</span><span class="sxs-lookup"><span data-stu-id="f388d-206">Multiple versions</span></span>

<span data-ttu-id="f388d-207">複数のバージョンを確認するには、まず、値が最新の .NET Framework バージョン用の小さい DWORD 値 "*以上*" であることを確認してから、その値と、それよりも以前のバージョン用の小さい DWORD 値を順番に比較します。</span><span class="sxs-lookup"><span data-stu-id="f388d-207">To test for multiple versions, begin by testing for a value that is *greater than or equal to* the smaller DWORD value for the latest .NET Framework version, and then compare the value with the smaller DWORD value for each successive earlier version.</span></span> <span data-ttu-id="f388d-208">たとえば、アプリケーションに .NET Framework 4.7 以降が必要で、存在する .NET Framework の特定のバージョンを確認する場合は、461808 (.NET Framework 4.7.2 用の小さい DWORD 値) "*以上*" の **RELEASE** DWORD 値であることの確認から始めます。</span><span class="sxs-lookup"><span data-stu-id="f388d-208">For example, if your application requires .NET Framework 4.7 or later and you want to determine the specific version of .NET Framework present, start by testing for a **RELEASE** DWORD value that is *great than or equal to* to 461808 (the smaller DWORD value for .NET Framework 4.7.2).</span></span> <span data-ttu-id="f388d-209">次に、**RELEASE** DWORD 値と、以降の各 .NET Framework バージョン用の小さい値と比較します。</span><span class="sxs-lookup"><span data-stu-id="f388d-209">Then compare the **RELEASE** DWORD value with the smaller value for each later .NET Framework version.</span></span>

<a name="net_d"></a>

### <a name="query-the-registry-using-code"></a><span data-ttu-id="f388d-210">コードを使用してレジストリのクエリを実行する</span><span class="sxs-lookup"><span data-stu-id="f388d-210">Query the registry using code</span></span>

1. <span data-ttu-id="f388d-211"><xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> メソッドと <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> メソッドを使用し、Windows レジストリの **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** サブキーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f388d-211">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey in the Windows registry.</span></span>

   <span data-ttu-id="f388d-212">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** サブキーに **Release** DWORD があるということは、コンピューターに .NET Framework 4.5 以降のバージョンがインストールされていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f388d-212">The existence of the **Release** DWORD entry in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey indicates that the .NET Framework 4.5 or a later version is installed on a computer.</span></span>

2. <span data-ttu-id="f388d-213">**Release** エントリの値を確認して、インストールされているバージョンを判断します。</span><span class="sxs-lookup"><span data-stu-id="f388d-213">Check the value of the **Release** entry to determine the installed version.</span></span> <span data-ttu-id="f388d-214">上位互換性があるかを確認するには、[.NET Framework のバージョンの表](#version_table)で示されている値以上の値があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f388d-214">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="f388d-215">次の例では、レジストリから **Release** の値を確認し、インストールされている .NET Framework 4.5 以降のバージョンを探しています。</span><span class="sxs-lookup"><span data-stu-id="f388d-215">The following example checks the value of the **Release** entry in the registry to find the .NET Framework 4.5 and later versions that are installed:</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="f388d-216">この例では、バージョンのチェックで推奨されている方法に従います。</span><span class="sxs-lookup"><span data-stu-id="f388d-216">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="f388d-217">**Release** エントリの値が、既知のリリース キー値*以上*かどうかを確認しています。</span><span class="sxs-lookup"><span data-stu-id="f388d-217">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="f388d-218">最新バージョンから最も古いバージョンの順にチェックします。</span><span class="sxs-lookup"><span data-stu-id="f388d-218">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a>

### <a name="use-powershell-to-check-for-a-minimum-required-version"></a><span data-ttu-id="f388d-219">PowerShell を使用して最低限必要なバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="f388d-219">Use PowerShell to check for a minimum-required version</span></span>

<span data-ttu-id="f388d-220">PowerShell コマンドを使用し、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** サブキーから **Release** エントリの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="f388d-220">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey.</span></span>

<span data-ttu-id="f388d-221">次の例では、**Release** エントリの値を確認して、.NET Framework 4.6.2 以降がインストールされているかどうかを判断しています。</span><span class="sxs-lookup"><span data-stu-id="f388d-221">The following examples check the value of the **Release** entry to determine whether the .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="f388d-222">このコードでは、インストールされていない場合は、`True` が返され、されている場合は `False` が返されます。</span><span class="sxs-lookup"><span data-stu-id="f388d-222">This code returns `True` if it's installed and `False` otherwise.</span></span>

```PowerShell
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

<span data-ttu-id="f388d-223">別の最低限必要な .NET Framework のバージョンを確認するには、例の `394802` を [.NET Framework バージョン一覧](#version_table)の値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f388d-223">To check for a different minimum-required .NET Framework version, replace `394802` in the example with a value from the [.NET Framework version table](#version_table).</span></span> <span data-ttu-id="f388d-224">そのバージョンに対して示されている最小値を使用します。</span><span class="sxs-lookup"><span data-stu-id="f388d-224">Use the smallest value shown for that version.</span></span>

## <a name="find-older-net-framework-versions-1-through-4"></a><span data-ttu-id="f388d-225">.NET Framework の以前のバージョンを探す (1 から 4)</span><span class="sxs-lookup"><span data-stu-id="f388d-225">Find older .NET Framework versions (1 through 4)</span></span>

<a name="net_a"></a>

### <a name="use-registry-editor-older-framework-versions"></a><span data-ttu-id="f388d-226">レジストリ エディターを使用する (古いバージョンのフレームワーク)</span><span class="sxs-lookup"><span data-stu-id="f388d-226">Use Registry Editor (older framework versions)</span></span>

1. <span data-ttu-id="f388d-227">**スタート** メニューの **[ファイル名を指定して実行]** を選択し、「*regedit*」と入力し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f388d-227">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

    <span data-ttu-id="f388d-228">regedit を実行するには、管理特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="f388d-228">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="f388d-229">レジストリ エディターで、次のサブキーを開きます。**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span><span class="sxs-lookup"><span data-stu-id="f388d-229">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span></span>

    - <span data-ttu-id="f388d-230">.NET Framework バージョン 1.1 から 3.5 では、インストールされている各バージョンは **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** サブキーの下にサブキーとして列挙されます。</span><span class="sxs-lookup"><span data-stu-id="f388d-230">For .NET Framework versions 1.1 through 3.5, each installed version is listed as a subkey under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** subkey.</span></span> <span data-ttu-id="f388d-231">たとえば、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5** です。</span><span class="sxs-lookup"><span data-stu-id="f388d-231">For example, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span></span> <span data-ttu-id="f388d-232">バージョン番号は、バージョン サブキーの **Version** エントリに値として格納されています。</span><span class="sxs-lookup"><span data-stu-id="f388d-232">The version number is stored as a value in the version subkey's **Version** entry.</span></span>

    - <span data-ttu-id="f388d-233">.NET Framework 4 では、**Version** エントリは、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** サブキー、**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** サブキーまたは両サブキーの下にあります。</span><span class="sxs-lookup"><span data-stu-id="f388d-233">For .NET Framework 4, the **Version** entry is under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** subkey, the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f388d-234">レジストリの **NET Framework セットアップ** フォルダーの先頭はピリオドではありません。</span><span class="sxs-lookup"><span data-stu-id="f388d-234">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="f388d-235">次の図では、.NET Framework 3.5 のサブキーとその **Version** エントリを示しています。</span><span class="sxs-lookup"><span data-stu-id="f388d-235">The following figure shows the subkey and its **Version** entry for the .NET Framework 3.5.</span></span>

    <span data-ttu-id="f388d-236">![.NET Framework 3.5 のレジストリ エントリ。](./media/net-4-and-earlier.png ".NET Framework 3.5 以前のバージョン")</span><span class="sxs-lookup"><span data-stu-id="f388d-236">![The registry entry for the .NET Framework 3.5.](./media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

<a name="net_c"></a>

### <a name="query-the-registry-using-code-older-framework-versions"></a><span data-ttu-id="f388d-237">コードを使用してレジストリのクエリを実行する (以前のバージョンのフレームワーク)</span><span class="sxs-lookup"><span data-stu-id="f388d-237">Query the registry using code (older framework versions)</span></span>

<span data-ttu-id="f388d-238"><xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> クラスを使用して、Windows レジストリの **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** サブキーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f388d-238">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** subkey in the Windows registry.</span></span>

<span data-ttu-id="f388d-239">次の例では、インストールされている .NET Framework のバージョン 1 から 4 が検索されています。</span><span class="sxs-lookup"><span data-stu-id="f388d-239">The following example finds the .NET Framework 1 through 4 versions that are installed:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a><span data-ttu-id="f388d-240">CLR のバージョンを探す</span><span class="sxs-lookup"><span data-stu-id="f388d-240">Find CLR versions</span></span>

<a name="clr_a"></a>

### <a name="use-clrverexe"></a><span data-ttu-id="f388d-241">Clrver.exe を使用する</span><span class="sxs-lookup"><span data-stu-id="f388d-241">Use Clrver.exe</span></span>

<span data-ttu-id="f388d-242">[CLR バージョン ツール (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) を使用して、コンピューターにインストールされている CLR のバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="f388d-242">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer:</span></span>

- <span data-ttu-id="f388d-243">[Visual Studio 用開発者コマンド プロンプト](../tools/developer-command-prompt-for-vs.md)で「`clrver`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f388d-243">From a [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), enter `clrver`.</span></span>

    <span data-ttu-id="f388d-244">出力例</span><span class="sxs-lookup"><span data-stu-id="f388d-244">Sample output:</span></span>

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a>

### <a name="use-the-environment-class"></a><span data-ttu-id="f388d-245">Environment クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="f388d-245">Use the Environment class</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f388d-246">.NET Framework 4.5 以降のバージョンでは、CLR のバージョンの検出に <xref:System.Environment.Version%2A?displayProperty=nameWithType> プロパティを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="f388d-246">For the .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="f388d-247">代わりに、「[コードで .NET Framework バージョン 4.5 以降を探す](#net_d)」の説明に従い、レジストリを照会します。</span><span class="sxs-lookup"><span data-stu-id="f388d-247">Instead, query the registry as described in [Find .NET Framework versions 4.5 and later with code](#net_d).</span></span>

1. <span data-ttu-id="f388d-248"><xref:System.Environment.Version?displayProperty=nameWithType> プロパティを照会し、<xref:System.Version> オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="f388d-248">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span>

    <span data-ttu-id="f388d-249">返された `System.Version` オブジェクトは、現在コードを実行しているランタイムのバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="f388d-249">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="f388d-250">コンピューターにインストールされている可能性のある、アセンブリのバージョンやランタイムのその他のバージョンは返されません。</span><span class="sxs-lookup"><span data-stu-id="f388d-250">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

    <span data-ttu-id="f388d-251">.NET Framework バージョン 4、4.5、4.5.1、4.5.2 の場合は、返される <xref:System.Version> オブジェクトの文字列表現は 4.0.30319.*xxxxx* という形式です。この *xxxxx* は 42000 より小さいものになります。</span><span class="sxs-lookup"><span data-stu-id="f388d-251">For the .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*, where *xxxxx* is less than 42000.</span></span> <span data-ttu-id="f388d-252">.NET Framework 4.6 以降のバージョンの場合は、4.0.30319.42000 という形式です。</span><span class="sxs-lookup"><span data-stu-id="f388d-252">For the .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>

2. <span data-ttu-id="f388d-253">`Version` オブジェクトを取得したら、次のように照会します。</span><span class="sxs-lookup"><span data-stu-id="f388d-253">After you have the `Version` object, query it as follows:</span></span>

   - <span data-ttu-id="f388d-254">メジャー リリース識別子 (たとえば、バージョン 4.0 の場合の *4*) には、<xref:System.Version.Major%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="f388d-254">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="f388d-255">マイナー リリース識別子 (たとえば、バージョン 4.0 の場合の *0*) には、<xref:System.Version.Minor%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="f388d-255">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="f388d-256">バージョンの完全な文字列 (たとえば、*4.0.30319.18010*) には、<xref:System.Version.ToString%2A?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f388d-256">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f388d-257">このメソッドでは、コードを実行しているランタイムのバージョンを示す値が 1 つ返されます。</span><span class="sxs-lookup"><span data-stu-id="f388d-257">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="f388d-258">コンピューターにインストールされている可能性のあるアセンブリ バージョンやその他のランタイム バージョンは返されません。</span><span class="sxs-lookup"><span data-stu-id="f388d-258">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>

<span data-ttu-id="f388d-259">次の例では、<xref:System.Environment.Version%2A?displayProperty=nameWithType> プロパティを使用して CLR バージョンの情報を取得しています。</span><span class="sxs-lookup"><span data-stu-id="f388d-259">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="f388d-260">関連項目</span><span class="sxs-lookup"><span data-stu-id="f388d-260">See also</span></span>

- [<span data-ttu-id="f388d-261">方法: インストールされている .NET Framework の更新プログラムを確認する</span><span class="sxs-lookup"><span data-stu-id="f388d-261">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="f388d-262">開発者向けの .NET Framework のインストール</span><span class="sxs-lookup"><span data-stu-id="f388d-262">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="f388d-263">.NET Framework のバージョンおよび依存関係</span><span class="sxs-lookup"><span data-stu-id="f388d-263">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)
