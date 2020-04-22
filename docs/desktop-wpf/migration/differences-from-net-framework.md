---
title: .NET フレームワークと .NET コアの違い
description: Windows プレゼンテーション ファンデーション (WPF) と .NET コア WPF の .NET フレームワーク実装の違いについて説明します。 アプリを移行する際には、これらの非互換性を考慮する必要があります。
author: thraka
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 341e576f17c522fbcbb9c417176e9d4a13ab1b18
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021839"
---
# <a name="differences-in-wpf"></a><span data-ttu-id="4ee8a-104">WPF の違い</span><span class="sxs-lookup"><span data-stu-id="4ee8a-104">Differences in WPF</span></span>

<span data-ttu-id="4ee8a-105">この資料では、.NET コアと .NET Framework の Windows プレゼンテーション ファンデーション (WPF) の違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-105">This article describes the differences between Windows Presentation Foundation (WPF) on .NET Core and .NET Framework.</span></span> <span data-ttu-id="4ee8a-106">.NET Core の WPF は、元の WPF から .NET Framework ソース コードをフォークされた[オープン ソース フレームワーク](https://github.com/dotnet/wpf)です。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-106">WPF for .NET Core is an [open-source framework](https://github.com/dotnet/wpf) forked from the original WPF for .NET Framework source code.</span></span>

<span data-ttu-id="4ee8a-107">.NET Framework には、.NET Core でサポートされていない機能がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-107">There are a few features of .NET Framework that .NET Core doesn't support.</span></span> <span data-ttu-id="4ee8a-108">サポートされていないテクノロジの詳細については、「 [.NET Framework テクノロジは .NET Core では使用できません](../../core/porting/net-framework-tech-unavailable.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-108">For more information on unsupported technologies, see [.NET Framework technologies unavailable on .NET Core](../../core/porting/net-framework-tech-unavailable.md).</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a><span data-ttu-id="4ee8a-109">SDK スタイルのプロジェクト</span><span class="sxs-lookup"><span data-stu-id="4ee8a-109">SDK-style projects</span></span>

<span data-ttu-id="4ee8a-110">.NET Core では、SDK スタイルのプロジェクト ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-110">.NET Core uses SDK-style project files.</span></span> <span data-ttu-id="4ee8a-111">これらのプロジェクト ファイルは、Visual Studio によって管理される従来の .NET Framework プロジェクト ファイルとは異なります。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-111">These project files are different from the traditional .NET Framework project files managed by Visual Studio.</span></span> <span data-ttu-id="4ee8a-112">.NET Framework WPF アプリを .NET Core に移行するには、プロジェクトを変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-112">To migrate your .NET Framework WPF apps to .NET Core, you must convert your projects.</span></span> <span data-ttu-id="4ee8a-113">詳細については、「 [.NET Core 3.0 への WPF アプリの移行](convert-project-from-net-framework.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-113">For more information, see [Migrate WPF apps to .NET Core 3.0](convert-project-from-net-framework.md).</span></span>

## <a name="nuget-package-references"></a><span data-ttu-id="4ee8a-114">NuGet パッケージのリファレンス</span><span class="sxs-lookup"><span data-stu-id="4ee8a-114">NuGet package references</span></span>

<span data-ttu-id="4ee8a-115">.NET Framework アプリが、その NuGet 依存関係を*packages.config*ファイルに[`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files)一覧表示する場合は、次の形式に移行します。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-115">If your .NET Framework app lists its NuGet dependencies in a *packages.config* file, migrate to the [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) format:</span></span>

1. <span data-ttu-id="4ee8a-116">Visual Studio で、[**ソリューション エクスプローラー** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-116">In Visual Studio, open the **Solution Explorer** pane.</span></span>
1. <span data-ttu-id="4ee8a-117">WPF プロジェクトで、[**パッケージ.config パッケージ.config** > **をパッケージ参照に移行**する] を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-117">In your WPF project, right-click **packages.config** > **Migrate packages.config to PackageReference**.</span></span>

![パッケージリファレンスへのアップグレード](media/differences-from-net-framework/package-reference-migration.png)

<span data-ttu-id="4ee8a-119">計算された最上位レベルの NuGet 依存関係を示すダイアログが表示され、他のどの NuGet パッケージを最上位レベルに昇格するかを確認します。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-119">A dialog will appear showing calculated top-level NuGet dependencies and asking which other NuGet packages should be promoted to top level.</span></span> <span data-ttu-id="4ee8a-120">**[OK] を**選択すると *、packages.config*ファイルがプロジェクト`<PackageReference>`から削除され、要素がプロジェクト ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-120">Select **OK** and the *packages.config* file will be removed from the project and `<PackageReference>` elements will be added to the project file.</span></span>

<span data-ttu-id="4ee8a-121">プロジェクトで を`<PackageReference>`使用する場合、パッケージは*Packages*フォルダーにローカルに保存されません。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-121">When your project uses `<PackageReference>`, packages aren't stored locally in a *Packages* folder, they're stored globally.</span></span> <span data-ttu-id="4ee8a-122">プロジェクト ファイルを開き`<Analyzer>`*、Packages*フォルダーを参照している要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-122">Open the project file and remove any `<Analyzer>` elements that referred to the *Packages* folder.</span></span> <span data-ttu-id="4ee8a-123">これらのアナライザーは、NuGet パッケージ参照に自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-123">These analyzers are automatically included with the NuGet package references.</span></span>

## <a name="code-access-security"></a><span data-ttu-id="4ee8a-124">コード アクセス セキュリティ</span><span class="sxs-lookup"><span data-stu-id="4ee8a-124">Code Access Security</span></span>

<span data-ttu-id="4ee8a-125">コード アクセス セキュリティ (CAS) は、.NET コアまたは .NET コアの WPF ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-125">Code Access Security (CAS) is not supported by .NET Core or WPF for .NET Core.</span></span> <span data-ttu-id="4ee8a-126">CAS 関連のすべての機能は、完全信頼の前提で処理されます。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-126">All CAS-related functionality is treated under the assumption of full-trust.</span></span> <span data-ttu-id="4ee8a-127">.NET コアの WPF は、CAS 関連のコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-127">WPF for .NET Core removes CAS-related code.</span></span> <span data-ttu-id="4ee8a-128">これらの型への呼び出しが成功するために、これらの型のパブリック API サーフェスは依然として存在します。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-128">The public API surface of these types still exists to ensure that calls into these types succeed.</span></span>

<span data-ttu-id="4ee8a-129">パブリックに定義された CAS 関連の型は、WPF アセンブリからコア .NET ライブラリ アセンブリに移動されました。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-129">Publicly defined CAS-related types were moved out of the WPF assemblies and into the Core .NET library assemblies.</span></span> <span data-ttu-id="4ee8a-130">WPF アセンブリは、移動された型の新しい場所に設定された型転送を持っています。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-130">The WPF assemblies have type-forwarding set to the new location of the moved types.</span></span>

| <span data-ttu-id="4ee8a-131">ソース アセンブリ</span><span class="sxs-lookup"><span data-stu-id="4ee8a-131">Source assembly</span></span> | <span data-ttu-id="4ee8a-132">ターゲット アセンブリ</span><span class="sxs-lookup"><span data-stu-id="4ee8a-132">Target assembly</span></span> | <span data-ttu-id="4ee8a-133">Type</span><span class="sxs-lookup"><span data-stu-id="4ee8a-133">Type</span></span>                |
| --------------- | --------------- | ------------------- |
| <span data-ttu-id="4ee8a-134">*WindowsBase.dll*</span><span class="sxs-lookup"><span data-stu-id="4ee8a-134">*WindowsBase.dll*</span></span> | <span data-ttu-id="4ee8a-135">*アクセス許可.dll*</span><span class="sxs-lookup"><span data-stu-id="4ee8a-135">*System.Security.Permissions.dll*</span></span> | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| <span data-ttu-id="4ee8a-136">*System.Xaml.dll*</span><span class="sxs-lookup"><span data-stu-id="4ee8a-136">*System.Xaml.dll*</span></span> | <span data-ttu-id="4ee8a-137">*アクセス許可.dll*</span><span class="sxs-lookup"><span data-stu-id="4ee8a-137">*System.Security.Permissions.dll*</span></span> | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| <span data-ttu-id="4ee8a-138">*System.Xaml.dll*</span><span class="sxs-lookup"><span data-stu-id="4ee8a-138">*System.Xaml.dll*</span></span> | <span data-ttu-id="4ee8a-139">*システム.Windows.エクステンション.dll*</span><span class="sxs-lookup"><span data-stu-id="4ee8a-139">*System.Windows.Extension.dll*</span></span>    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> <span data-ttu-id="4ee8a-140">移植摩擦を最小限に抑えるために、以下のプロパティに関連する情報を保存および取得する機能は`XamlAccessLevel`、このタイプに保持されていました。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-140">In order to minimize porting friction, the functionality for storing and retrieving information related to the following properties was retained in the `XamlAccessLevel` type.</span></span>
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a><span data-ttu-id="4ee8a-141">次のステップ</span><span class="sxs-lookup"><span data-stu-id="4ee8a-141">Next steps</span></span>

- [<span data-ttu-id="4ee8a-142">.NET Framework WPF アプリを .NET Core に移植する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ee8a-142">Learn how to port a .NET Framework WPF app to .NET Core.</span></span>](convert-project-from-net-framework.md)
