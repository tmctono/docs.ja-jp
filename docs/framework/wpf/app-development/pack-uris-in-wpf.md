---
title: パック URI
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: a98c97a4aa95fb956a2ca6d417e009a281a938b6
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124482"
---
# <a name="pack-uris-in-wpf"></a><span data-ttu-id="16231-102">WPF におけるパッケージの URI</span><span class="sxs-lookup"><span data-stu-id="16231-102">Pack URIs in WPF</span></span>

<span data-ttu-id="16231-103">Windows Presentation Foundation (WPF) では、Uniform Resource Identifier (URI) は、次のようなさまざまな用途でファイルを識別し、読み込むために使用されます。</span><span class="sxs-lookup"><span data-stu-id="16231-103">In Windows Presentation Foundation (WPF), uniform resource identifiers (URIs) are used to identify and load files in many ways, including the following:</span></span>

- <span data-ttu-id="16231-104">アプリケーションが初めて起動するときに表示する [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] の指定。</span><span class="sxs-lookup"><span data-stu-id="16231-104">Specifying the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] to show when an application first starts.</span></span>

- <span data-ttu-id="16231-105">イメージの読み込み。</span><span class="sxs-lookup"><span data-stu-id="16231-105">Loading images.</span></span>

- <span data-ttu-id="16231-106">ページへの移動。</span><span class="sxs-lookup"><span data-stu-id="16231-106">Navigating to pages.</span></span>

- <span data-ttu-id="16231-107">実行可能でないデータ ファイルの読み込み。</span><span class="sxs-lookup"><span data-stu-id="16231-107">Loading non-executable data files.</span></span>

<span data-ttu-id="16231-108">さらに、URI は、次のようなさまざまな場所からファイルを識別し、読み込むために使用できます。</span><span class="sxs-lookup"><span data-stu-id="16231-108">Furthermore, URIs can be used to identify and load files from a variety of locations, including the following:</span></span>

- <span data-ttu-id="16231-109">現在のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="16231-109">The current assembly.</span></span>

- <span data-ttu-id="16231-110">参照アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="16231-110">A referenced assembly.</span></span>

- <span data-ttu-id="16231-111">アセンブリに対して相対的な位置。</span><span class="sxs-lookup"><span data-stu-id="16231-111">A location relative to an assembly.</span></span>

- <span data-ttu-id="16231-112">アプリケーションの起点サイト。</span><span class="sxs-lookup"><span data-stu-id="16231-112">The application's site of origin.</span></span>

<span data-ttu-id="16231-113">これらの位置からこれらの種類のファイルを識別し、読み込むための一貫性のあるメカニズムを提供するために、WPF では "*パック URI スキーム*" の拡張性が利用されます。</span><span class="sxs-lookup"><span data-stu-id="16231-113">To provide a consistent mechanism for identifying and loading these types of files from these locations, WPF leverages the extensibility of the *pack URI scheme*.</span></span> <span data-ttu-id="16231-114">このトピックでは、このスキームの概要を説明し、さまざまなシナリオに応じたパック URI を構築する方法を述べ、絶対および相対 URI と URI の解決について説明した後、マークアップとコードの両方からパック URI を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="16231-114">This topic provides an overview of the scheme, covers how to construct pack URIs for a variety of scenarios, discusses absolute and relative URIs and URI resolution, before showing how to use pack URIs from both markup and code.</span></span>

<a name="The_Pack_URI_Scheme"></a>

## <a name="the-pack-uri-scheme"></a><span data-ttu-id="16231-115">パック URI スキーム</span><span class="sxs-lookup"><span data-stu-id="16231-115">The Pack URI Scheme</span></span>

<span data-ttu-id="16231-116">パック URI スキームは、[Open Packaging Conventions](https://www.ecma-international.org/publications/standards/Ecma-376.htm) (OPC) 仕様によって使用されます。この仕様は、コンテンツを編成し、識別するためのモデルを規定しています。</span><span class="sxs-lookup"><span data-stu-id="16231-116">The pack URI scheme is used by the [Open Packaging Conventions](https://www.ecma-international.org/publications/standards/Ecma-376.htm) (OPC) specification, which describes a model for organizing and identifying content.</span></span> <span data-ttu-id="16231-117">このモデルの主な要素は、パッケージとパーツであり、"*パッケージ*" は、1 つ以上の論理 "*パーツ*" の論理的なコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="16231-117">The key elements of this model are packages and parts, where a *package* is a logical container for one or more logical *parts*.</span></span> <span data-ttu-id="16231-118">この概念を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="16231-118">The following figure illustrates this concept.</span></span>

![パッケージとパーツのダイアグラム](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)

<span data-ttu-id="16231-120">パーツを識別するために、OPC 仕様では、RFC 2396 (Uniform Resource Identifier (URI): 一般構文) の拡張性を利用して、パック URI スキームが定義されます。</span><span class="sxs-lookup"><span data-stu-id="16231-120">To identify parts, the OPC specification leverages the extensibility of RFC 2396 (Uniform Resource Identifiers (URI): Generic Syntax) to define the pack URI scheme.</span></span>

<span data-ttu-id="16231-121">URI によって指定されるスキームは、そのプレフィックスによって定義されます。http、ftp、および file は、よく知られている例です。</span><span class="sxs-lookup"><span data-stu-id="16231-121">The scheme that is specified by a URI is defined by its prefix; http, ftp, and file are well-known examples.</span></span> <span data-ttu-id="16231-122">パック URI スキームでは、スキームとして "pack" が使用され、オーソリティとパスの 2 つのコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="16231-122">The pack URI scheme uses "pack" as its scheme, and contains two components: authority and path.</span></span> <span data-ttu-id="16231-123">パック URI の形式は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="16231-123">The following is the format for a pack URI.</span></span>

<span data-ttu-id="16231-124">pack://*authority*/*path*</span><span class="sxs-lookup"><span data-stu-id="16231-124">pack://*authority*/*path*</span></span>

<span data-ttu-id="16231-125">*authority* は、パーツが含まれるパッケージの種類を指定し、*path* は、パッケージ内のパーツの位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="16231-125">The *authority* specifies the type of package that a part is contained by, while the *path* specifies the location of a part within a package.</span></span>

<span data-ttu-id="16231-126">この概念を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="16231-126">This concept is illustrated by the following figure:</span></span>

![パッケージ、権限、およびパスの間のリレーションシップ](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)

<span data-ttu-id="16231-128">パッケージとパーツは、アプリケーションとファイルに似ています。つまり、アプリケーション (パッケージ) は、次のような 1 つ以上のファイル (パーツ) を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="16231-128">Packages and parts are analogous to applications and files, where an application (package) can include one or more files (parts), including:</span></span>

- <span data-ttu-id="16231-129">ローカル アセンブリにコンパイルされるリソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="16231-129">Resource files that are compiled into the local assembly.</span></span>

- <span data-ttu-id="16231-130">参照センブリにコンパイルされるリソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="16231-130">Resource files that are compiled into a referenced assembly.</span></span>

- <span data-ttu-id="16231-131">参照元センブリにコンパイルされるリソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="16231-131">Resource files that are compiled into a referencing assembly.</span></span>

- <span data-ttu-id="16231-132">コンテンツ ファイル。</span><span class="sxs-lookup"><span data-stu-id="16231-132">Content files.</span></span>

- <span data-ttu-id="16231-133">起点サイト ファイル。</span><span class="sxs-lookup"><span data-stu-id="16231-133">Site of origin files.</span></span>

<span data-ttu-id="16231-134">これらの種類のファイルにアクセスするために、WPF では、application:/// と siteoforigin:/// という 2 つのオーソリティがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="16231-134">To access these types of files, WPF supports two authorities: application:/// and siteoforigin:///.</span></span> <span data-ttu-id="16231-135">application:/// オーソリティは、リソース ファイルやコンテンツ ファイルなど、コンパイル時に既知のアプリケーション データ ファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="16231-135">The application:/// authority identifies application data files that are known at compile time, including resource and content files.</span></span> <span data-ttu-id="16231-136">siteoforigin:/// オーソリティは、起点サイト ファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="16231-136">The siteoforigin:/// authority identifies site of origin files.</span></span> <span data-ttu-id="16231-137">各オーソリティのスコープを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="16231-137">The scope of each authority is shown in the following figure.</span></span>

![Pack URI のダイアグラム](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)

> [!NOTE]
> <span data-ttu-id="16231-139">パック URI のオーソリティ コンポーネントは、パッケージを指す埋め込み URI であり、RFC 2396 に準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16231-139">The authority component of a pack URI is an embedded URI that points to a package and must conform to RFC 2396.</span></span> <span data-ttu-id="16231-140">さらに、"/" 文字は "," 文字に置き換える必要があり、"%" や "?" などの予約文字はエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16231-140">Additionally, the "/" character must be replaced with the "," character, and reserved characters such as "%" and "?" must be escaped.</span></span> <span data-ttu-id="16231-141">詳細については、OPC を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16231-141">See the OPC for details.</span></span>

<span data-ttu-id="16231-142">以下のセクションでは、この 2 つのオーソリティと、リソース ファイル、コンテンツ ファイル、および起点サイト ファイルを識別する適切なパスとを組み合わせてパック URI を構築する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="16231-142">The following sections explain how to construct pack URIs using these two authorities in conjunction with the appropriate paths for identifying resource, content, and site of origin files.</span></span>

<a name="Resource_File_Pack_URIs___Local_Assembly"></a>

## <a name="resource-file-pack-uris"></a><span data-ttu-id="16231-143">リソース ファイルのパック URI</span><span class="sxs-lookup"><span data-stu-id="16231-143">Resource File Pack URIs</span></span>

<span data-ttu-id="16231-144">リソース ファイルは、MSBuild の`Resource` 項目として構成され、アセンブリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="16231-144">Resource files are configured as MSBuild `Resource` items and are compiled into assemblies.</span></span> <span data-ttu-id="16231-145">WPF では、ローカル アセンブリにコンパイルされるか、ローカル アセンブリから参照されるアセンブリにコンパイルされるリソース ファイルを識別するために使用できるパック URI の構築がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="16231-145">WPF supports the construction of pack URIs that can be used to identify resource files that are either compiled into the local assembly or compiled into an assembly that is referenced from the local assembly.</span></span>

<a name="Local_Assembly_Resource_File"></a>

### <a name="local-assembly-resource-file"></a><span data-ttu-id="16231-146">ローカル アセンブリ リソース ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-146">Local Assembly Resource File</span></span>

<span data-ttu-id="16231-147">ローカル アセンブリにコンパイルされるリソース ファイルのパック URI では、次のオーソリティとパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="16231-147">The pack URI for a resource file that is compiled into the local assembly uses the following authority and path:</span></span>

- <span data-ttu-id="16231-148">**オーソリティ**: application:///。</span><span class="sxs-lookup"><span data-stu-id="16231-148">**Authority**: application:///.</span></span>

- <span data-ttu-id="16231-149">**パス**:ローカル アセンブリのプロジェクト フォルダーのルートに対して相対的なパスを含むリソース ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="16231-149">**Path**: The name of the resource file, including its path, relative to the local assembly project folder root.</span></span>

<span data-ttu-id="16231-150">次の例では、ローカル アセンブリのプロジェクト フォルダーのルートにある [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] リソース ファイルのパック URI を示します。</span><span class="sxs-lookup"><span data-stu-id="16231-150">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the local assembly's project folder.</span></span>

`pack://application:,,,/ResourceFile.xaml`

<span data-ttu-id="16231-151">次の例では、ローカル アセンブリのプロジェクト フォルダーのサブフォルダーにある [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] リソース ファイルのパック URI を示します。</span><span class="sxs-lookup"><span data-stu-id="16231-151">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the local assembly's project folder.</span></span>

`pack://application:,,,/Subfolder/ResourceFile.xaml`

<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>

### <a name="referenced-assembly-resource-file"></a><span data-ttu-id="16231-152">参照アセンブリ リソース ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-152">Referenced Assembly Resource File</span></span>

<span data-ttu-id="16231-153">参照アセンブリにコンパイルされるリソース ファイルのパック URI では、次のオーソリティとパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="16231-153">The pack URI for a resource file that is compiled into a referenced assembly uses the following authority and path:</span></span>

- <span data-ttu-id="16231-154">**オーソリティ**: application:///。</span><span class="sxs-lookup"><span data-stu-id="16231-154">**Authority**: application:///.</span></span>

- <span data-ttu-id="16231-155">**パス**:参照アセンブリにコンパイルされるリソース ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="16231-155">**Path**: The name of a resource file that is compiled into a referenced assembly.</span></span> <span data-ttu-id="16231-156">パスは、次の書式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="16231-156">The path must conform to the following format:</span></span>

  <span data-ttu-id="16231-157">*AssemblyShortName*{ *;Version*]{ *;PublicKey*];component/*Path*</span><span class="sxs-lookup"><span data-stu-id="16231-157">*AssemblyShortName*{*;Version*]{*;PublicKey*];component/*Path*</span></span>

  - <span data-ttu-id="16231-158">**AssemblyShortName**: 参照アセンブリの短い名前。</span><span class="sxs-lookup"><span data-stu-id="16231-158">**AssemblyShortName**: the short name for the referenced assembly.</span></span>

  - <span data-ttu-id="16231-159">**;Version** (省略可能): リソース ファイルを含む参照アセンブリのバージョン。</span><span class="sxs-lookup"><span data-stu-id="16231-159">**;Version** [optional]: the version of the referenced assembly that contains the resource file.</span></span> <span data-ttu-id="16231-160">これは、同じ短い名前を持つ 2 つ以上の参照アセンブリが読み込まれるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="16231-160">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>

  - <span data-ttu-id="16231-161">**;PublicKey** (省略可能): 参照アセンブリの署名に使用された公開鍵。</span><span class="sxs-lookup"><span data-stu-id="16231-161">**;PublicKey** [optional]: the public key that was used to sign the referenced assembly.</span></span> <span data-ttu-id="16231-162">これは、同じ短い名前を持つ 2 つ以上の参照アセンブリが読み込まれるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="16231-162">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>

  - <span data-ttu-id="16231-163">**;component**: 参照されるアセンブリが、ローカル アセンブリから参照されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="16231-163">**;component**: specifies that the assembly being referred to is referenced from the local assembly.</span></span>

  - <span data-ttu-id="16231-164">**/Path**: 参照アセンブリのプロジェクト フォルダーのルートに対して相対的なパスを含むリソース ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="16231-164">**/Path**: the name of the resource file, including its path, relative to the root of the referenced assembly's project folder.</span></span>

<span data-ttu-id="16231-165">次の例では、参照アセンブリのプロジェクト フォルダーのルートにある [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] リソース ファイルのパック URI を示します。</span><span class="sxs-lookup"><span data-stu-id="16231-165">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the referenced assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`

<span data-ttu-id="16231-166">次の例では、参照アセンブリのプロジェクト フォルダーのサブフォルダーにある [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] リソース ファイルのパック URI を示します。</span><span class="sxs-lookup"><span data-stu-id="16231-166">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the referenced assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`

<span data-ttu-id="16231-167">次の例では、バージョン固有の参照アセンブリのプロジェクト フォルダーのルートにある [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] リソース ファイルのパック URI を示します。</span><span class="sxs-lookup"><span data-stu-id="16231-167">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root folder of a referenced, version-specific assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`

<span data-ttu-id="16231-168">参照アセンブリ リソース ファイルのパック URI 構文は、application:/// オーソリティでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="16231-168">Note that the pack URI syntax for referenced assembly resource files can be used only with the application:/// authority.</span></span> <span data-ttu-id="16231-169">たとえば、WPF では、次はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="16231-169">For example, the following is not supported in WPF.</span></span>

`pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`

<a name="Content_File_Pack_URIs"></a>

## <a name="content-file-pack-uris"></a><span data-ttu-id="16231-170">コンテンツ ファイルのパック URI</span><span class="sxs-lookup"><span data-stu-id="16231-170">Content File Pack URIs</span></span>

<span data-ttu-id="16231-171">コンテンツ ファイルのパック URI では、次のオーソリティとパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="16231-171">The pack URI for a content file uses the following authority and path:</span></span>

- <span data-ttu-id="16231-172">**オーソリティ**: application:///。</span><span class="sxs-lookup"><span data-stu-id="16231-172">**Authority**: application:///.</span></span>

- <span data-ttu-id="16231-173">**パス**:アプリケーションのメインの実行可能アセンブリのファイル システム位置に対して相対的なパスを含む、コンテンツ ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="16231-173">**Path**: The name of the content file, including its path relative to the file system location of the application's main executable assembly.</span></span>

<span data-ttu-id="16231-174">次の例では、実行可能アセンブリと同じフォルダーにある [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] コンテンツ ファイルのパック URI を示します。</span><span class="sxs-lookup"><span data-stu-id="16231-174">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in the same folder as the executable assembly.</span></span>

`pack://application:,,,/ContentFile.xaml`

<span data-ttu-id="16231-175">次の例では、アプリケーションの実行可能アセンブリに対して相対的なサブフォルダーにある [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] コンテンツ ファイルのパック URI を示します。</span><span class="sxs-lookup"><span data-stu-id="16231-175">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in a subfolder that is relative to the application's executable assembly.</span></span>

`pack://application:,,,/Subfolder/ContentFile.xaml`

> [!NOTE]
> <span data-ttu-id="16231-176">HTML コンテンツ ファイルにナビゲートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="16231-176">HTML content files cannot be navigated to.</span></span> <span data-ttu-id="16231-177">URI スキームでは、起点サイトにある HTML ファイルへのナビゲーションのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="16231-177">The URI scheme only supports navigation to HTML files that are located at the site of origin.</span></span>

<a name="The_siteoforigin_____Authority"></a>

## <a name="site-of-origin-pack-uris"></a><span data-ttu-id="16231-178">起点サイトのパック URI</span><span class="sxs-lookup"><span data-stu-id="16231-178">Site of Origin Pack URIs</span></span>

<span data-ttu-id="16231-179">起点サイト ファイルのパック URI では、次のオーソリティとパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="16231-179">The pack URI for a site of origin file uses the following authority and path:</span></span>

- <span data-ttu-id="16231-180">**オーソリティ**: siteoforigin:///。</span><span class="sxs-lookup"><span data-stu-id="16231-180">**Authority**: siteoforigin:///.</span></span>

- <span data-ttu-id="16231-181">**パス**:実行可能アセンブリの起動元の位置に対して相対的なパスを含む起点サイト ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="16231-181">**Path**: The name of the site of origin file, including its path relative to the location from which the executable assembly was launched.</span></span>

<span data-ttu-id="16231-182">次の例では、実行可能アセンブリの起動元の位置に格納された [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 起点サイト ファイルのパック URI を示します。</span><span class="sxs-lookup"><span data-stu-id="16231-182">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in the location from which the executable assembly is launched.</span></span>

`pack://siteoforigin:,,,/SiteOfOriginFile.xaml`

<span data-ttu-id="16231-183">次の例では、アプリケーションの実行可能アセンブリの起動元の位置に対して相対的なサブフォルダーに格納された [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 起点サイト ファイルのパック URI を示します。</span><span class="sxs-lookup"><span data-stu-id="16231-183">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in subfolder that is relative to the location from which the application's executable assembly is launched.</span></span>

`pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`

<a name="Page_Files"></a>

## <a name="page-files"></a><span data-ttu-id="16231-184">ページ ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-184">Page Files</span></span>

<span data-ttu-id="16231-185">MSBuild の `Page` 項目として構成される XAML ファイルは、リソース ファイルと同じようにアセンブリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="16231-185">XAML files that are configured as MSBuild `Page` items are compiled into assemblies in the same way as resource files.</span></span> <span data-ttu-id="16231-186">したがって、MSBuild の`Page` 項目は、リソース ファイルのパック URI を使用して識別できます。</span><span class="sxs-lookup"><span data-stu-id="16231-186">Consequently, MSBuild `Page` items can be identified using pack URIs for resource files.</span></span>

<span data-ttu-id="16231-187">一般に MSBuild の `Page` 項目として構成される [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルの種類は、次のいずれかをルート要素として持ちます。</span><span class="sxs-lookup"><span data-stu-id="16231-187">The types of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that are commonly configured as MSBuild`Page` items have one of the following as their root element:</span></span>

- <xref:System.Windows.Window?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Page?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>

- <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>

- <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>

- <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>

<a name="Absolute_vs_Relative_Pack_URIs"></a>

## <a name="absolute-vs-relative-pack-uris"></a><span data-ttu-id="16231-188">絶対および相対パック URI</span><span class="sxs-lookup"><span data-stu-id="16231-188">Absolute vs. Relative Pack URIs</span></span>

<span data-ttu-id="16231-189">完全修飾されたパック URI は、スキーム、オーソリティ、およびパスを含み、絶対パック URI とみなされます。</span><span class="sxs-lookup"><span data-stu-id="16231-189">A fully qualified pack URI includes the scheme, the authority, and the path, and it is considered an absolute pack URI.</span></span> <span data-ttu-id="16231-190">開発者にとっての簡便さを考慮して、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 要素では、一般に、パスのみを含む相対パック URI で適切な属性を設定できます。</span><span class="sxs-lookup"><span data-stu-id="16231-190">As a simplification for developers, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements typically allow you to set appropriate attributes with a relative pack URI, which includes only the path.</span></span>

<span data-ttu-id="16231-191">たとえば、ローカル アセンブリ内のリソース ファイルに対する次のような絶対パック URI を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="16231-191">For example, consider the following absolute pack URI for a resource file in the local assembly.</span></span>

`pack://application:,,,/ResourceFile.xaml`

<span data-ttu-id="16231-192">このリソース ファイルを参照する相対パック URI は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="16231-192">The relative pack URI that refers to this resource file would be the following.</span></span>

`/ResourceFile.xaml`

> [!NOTE]
> <span data-ttu-id="16231-193">起点サイト ファイルはアセンブリに関連付けられていないため、絶対パック URI でのみ参照できます。</span><span class="sxs-lookup"><span data-stu-id="16231-193">Because site of origin files are not associated with assemblies, they can only be referred to with absolute pack URIs.</span></span>

<span data-ttu-id="16231-194">既定では、相対パック URI は、参照を含んでいるマークアップまたはコードの位置に対して相対的とみなされます。</span><span class="sxs-lookup"><span data-stu-id="16231-194">By default, a relative pack URI is considered relative to the location of the markup or code that contains the reference.</span></span> <span data-ttu-id="16231-195">ただし、先頭にバック スラッシュが使用された場合、相対パック URI 参照は、アプリケーションのルートに対して相対的とみなされます。</span><span class="sxs-lookup"><span data-stu-id="16231-195">If a leading backslash is used, however, the relative pack URI reference is then considered relative to the root of the application.</span></span> <span data-ttu-id="16231-196">たとえば、次のようなプロジェクト構造を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="16231-196">For example, consider the following project structure.</span></span>

`App.xaml`

`Page2.xaml`

`\SubFolder`

`+ Page1.xaml`

`+ Page2.xaml`

<span data-ttu-id="16231-197">Page1.xaml に、*Root*\SubFolder\Page2.xaml を参照する URI が含まれる場合、参照で次のような相対パック URI を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="16231-197">If Page1.xaml contains a URI that references *Root*\SubFolder\Page2.xaml, the reference can use the following relative pack URI.</span></span>

`Page2.xaml`

<span data-ttu-id="16231-198">Page1.xaml に、*Root*\Page2.xaml を参照する URI が含まれる場合、参照で次のような相対パック URI を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="16231-198">If Page1.xaml contains a URI that references *Root*\Page2.xaml, the reference can use the following relative pack URI.</span></span>

`/Page2.xaml`

<a name="Pack_URI_Resolution"></a>

## <a name="pack-uri-resolution"></a><span data-ttu-id="16231-199">パック URI の解決</span><span class="sxs-lookup"><span data-stu-id="16231-199">Pack URI Resolution</span></span>

<span data-ttu-id="16231-200">パック URI の書式では、異なる種類のファイルのパック URI が同じに見えることがあります。</span><span class="sxs-lookup"><span data-stu-id="16231-200">The format of pack URIs makes it possible for pack URIs for different types of files to look the same.</span></span> <span data-ttu-id="16231-201">たとえば、次のような絶対パック URI を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="16231-201">For example, consider the following absolute pack URI.</span></span>

`pack://application:,,,/ResourceOrContentFile.xaml`

<span data-ttu-id="16231-202">この絶対パック URI では、ローカル アセンブリ内のリソース ファイルまたはコンテンツ ファイルが参照されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="16231-202">This absolute pack URI could refer to either a resource file in the local assembly or a content file.</span></span> <span data-ttu-id="16231-203">次の相対 URI も同様です。</span><span class="sxs-lookup"><span data-stu-id="16231-203">The same is true for the following relative URI.</span></span>

`/ResourceOrContentFile.xaml`

<span data-ttu-id="16231-204">パック URI で参照されているファイルの種類を判断するため、WPF では、次のヒューリスティックを使用して、ローカル アセンブリ内のリソース ファイルとコンテンツ ファイルの URI が解決されます。</span><span class="sxs-lookup"><span data-stu-id="16231-204">In order to determine the type of file that a pack URI refers to, WPF resolves URIs for resource files in local assemblies and content files by using the following heuristics:</span></span>

1. <span data-ttu-id="16231-205">アセンブリ メタデータに、パック URI に一致する <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 属性があるかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="16231-205">Probe the assembly metadata for an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute that matches the pack URI.</span></span>

2. <span data-ttu-id="16231-206"><xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 属性が見つかった場合、パック URI ではコンテンツ ファイルが参照されています。</span><span class="sxs-lookup"><span data-stu-id="16231-206">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is found, the path of the pack URI refers to a content file.</span></span>

3. <span data-ttu-id="16231-207"><xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 属性が見つからなかった場合は、ローカル アセンブリにコンパイルされる設定リソース ファイルを調べます。</span><span class="sxs-lookup"><span data-stu-id="16231-207">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is not found, probe the set resource files that are compiled into the local assembly.</span></span>

4. <span data-ttu-id="16231-208">パック URI のパスに一致するリソース ファイルが見つかった場合、パック URI のパスではリソース ファイルが参照されています。</span><span class="sxs-lookup"><span data-stu-id="16231-208">If a resource file that matches the path of the pack URI is found, the path of the pack URI refers to a resource file.</span></span>

5. <span data-ttu-id="16231-209">リソースが見つからなかった場合、内部で作成された <xref:System.Uri> は無効です。</span><span class="sxs-lookup"><span data-stu-id="16231-209">If the resource is not found, the internally created <xref:System.Uri> is invalid.</span></span>

<span data-ttu-id="16231-210">URI 解決は、次を参照する URI には適用されません。</span><span class="sxs-lookup"><span data-stu-id="16231-210">URI resolution does not apply for URIs that refer to the following:</span></span>

- <span data-ttu-id="16231-211">参照アセンブリ内のコンテンツ ファイル: この種類のファイルは、WPF ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="16231-211">Content files in referenced assemblies: these file types are not supported by WPF.</span></span>

- <span data-ttu-id="16231-212">参照アセンブリ内の埋め込みファイル: これらは参照アセンブリの名前と `;component` サフィックスの両方を含むため、これらを示す URI は一意です。</span><span class="sxs-lookup"><span data-stu-id="16231-212">Embedded files in referenced assemblies: URIs that identify them are unique because they include both the name of the referenced assembly and the `;component` suffix.</span></span>

- <span data-ttu-id="16231-213">起点サイト ファイル: これらは siteoforigin:/// オーソリティを含むパック URI によって識別できる唯一のファイルであるため、これらを示す URI は一意です。</span><span class="sxs-lookup"><span data-stu-id="16231-213">Site of origin files: URIs that identify them are unique because they are the only files that can be identified by pack URIs that contain the siteoforigin:/// authority.</span></span>

<span data-ttu-id="16231-214">パック URI の解決によってもたらされる単純化の 1 つは、コードがリソース ファイルやコンテンツ ファイルの位置にあまり依存しなくなることです。</span><span class="sxs-lookup"><span data-stu-id="16231-214">One simplification that pack URI resolution allows is for code to be somewhat independent of the locations of resource and content files.</span></span> <span data-ttu-id="16231-215">たとえば、ローカル アセンブリ内のリソース ファイルがコンテンツ ファイルに再構成される場合、リソースのパック URI は同じままであり、パック URI を使用するコードも変わりません。</span><span class="sxs-lookup"><span data-stu-id="16231-215">For example, if you have a resource file in the local assembly that is reconfigured to be a content file, the pack URI for the resource remains the same, as does the code that uses the pack URI.</span></span>

<a name="Programming_with_Pack_URIs"></a>

## <a name="programming-with-pack-uris"></a><span data-ttu-id="16231-216">パック URI を使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="16231-216">Programming with Pack URIs</span></span>

<span data-ttu-id="16231-217">多くの WPF クラスでは、次のように、パック URI で設定できるプロパティが実装されます。</span><span class="sxs-lookup"><span data-stu-id="16231-217">Many WPF classes implement properties that can be set with pack URIs, including:</span></span>

- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>

<span data-ttu-id="16231-218">これらのプロパティは、マークアップとコードのどちらからでも設定できます。</span><span class="sxs-lookup"><span data-stu-id="16231-218">These properties can be set from both markup and code.</span></span> <span data-ttu-id="16231-219">このセクションでは、両方の基本構造について説明してから、一般的なシナリオの例を示します。</span><span class="sxs-lookup"><span data-stu-id="16231-219">This section demonstrates the basic constructions for both and then shows examples of common scenarios.</span></span>

<a name="Using_Pack_URIs_in_Markup"></a>

### <a name="using-pack-uris-in-markup"></a><span data-ttu-id="16231-220">マークアップでのパック URI の使用</span><span class="sxs-lookup"><span data-stu-id="16231-220">Using Pack URIs in Markup</span></span>

<span data-ttu-id="16231-221">パック URI は、マークアップでは、属性の要素にパック URI を設定することによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="16231-221">A pack URI is specified in markup by setting the element of an attribute with the pack URI.</span></span> <span data-ttu-id="16231-222">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="16231-222">For example:</span></span>

`<element attribute="pack://application:,,,/File.xaml" />`

<span data-ttu-id="16231-223">表 1 では、マークアップで指定できるさまざまな絶対パック URI を示します。</span><span class="sxs-lookup"><span data-stu-id="16231-223">Table 1 illustrates the various absolute pack URIs that you can specify in markup.</span></span>

<span data-ttu-id="16231-224">表 1:マークアップでの絶対パック URI</span><span class="sxs-lookup"><span data-stu-id="16231-224">Table 1: Absolute Pack URIs in Markup</span></span>

|<span data-ttu-id="16231-225">ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-225">File</span></span>|<span data-ttu-id="16231-226">絶対パック URI</span><span class="sxs-lookup"><span data-stu-id="16231-226">Absolute pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="16231-227">リソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="16231-227">Resource file - local assembly</span></span>|`"pack://application:,,,/ResourceFile.xaml"`|
|<span data-ttu-id="16231-228">サブフォルダー内のリソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="16231-228">Resource file in subfolder - local assembly</span></span>|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="16231-229">リソース ファイル - 参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="16231-229">Resource file - referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|
|<span data-ttu-id="16231-230">参照アセンブリのサブフォルダー内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-230">Resource file in subfolder of referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="16231-231">バージョン管理された参照アセンブリ内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-231">Resource file in versioned referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|
|<span data-ttu-id="16231-232">コンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-232">Content file</span></span>|`"pack://application:,,,/ContentFile.xaml"`|
|<span data-ttu-id="16231-233">サブフォルダー内のコンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-233">Content file in subfolder</span></span>|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|
|<span data-ttu-id="16231-234">起点サイト ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-234">Site of origin file</span></span>|`"pack://siteoforigin:,,,/SOOFile.xaml"`|
|<span data-ttu-id="16231-235">サブフォルダー内の起点サイト ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-235">Site of origin file in subfolder</span></span>|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|

<span data-ttu-id="16231-236">表 2 では、マークアップで指定できるさまざまな相対パック URI を示します。</span><span class="sxs-lookup"><span data-stu-id="16231-236">Table 2 illustrates the various relative pack URIs that you can specify in markup.</span></span>

<span data-ttu-id="16231-237">表 2:マークアップでの相対パック URI</span><span class="sxs-lookup"><span data-stu-id="16231-237">Table 2: Relative Pack URIs in Markup</span></span>

|<span data-ttu-id="16231-238">ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-238">File</span></span>|<span data-ttu-id="16231-239">相対パック URI</span><span class="sxs-lookup"><span data-stu-id="16231-239">Relative pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="16231-240">ローカル アセンブリ内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-240">Resource file in local assembly</span></span>|`"/ResourceFile.xaml"`|
|<span data-ttu-id="16231-241">ローカル アセンブリのサブフォルダー内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-241">Resource file in subfolder of local assembly</span></span>|`"/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="16231-242">参照アセンブリ内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-242">Resource file in referenced assembly</span></span>|`"/ReferencedAssembly;component/ResourceFile.xaml"`|
|<span data-ttu-id="16231-243">参照アセンブリのサブフォルダー内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-243">Resource file in subfolder of referenced assembly</span></span>|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="16231-244">コンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-244">Content file</span></span>|`"/ContentFile.xaml"`|
|<span data-ttu-id="16231-245">サブフォルダー内のコンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-245">Content file in subfolder</span></span>|`"/Subfolder/ContentFile.xaml"`|

<a name="Using_Pack_URIs_in_Code"></a>

### <a name="using-pack-uris-in-code"></a><span data-ttu-id="16231-246">コードでのパック URI の使用</span><span class="sxs-lookup"><span data-stu-id="16231-246">Using Pack URIs in Code</span></span>

<span data-ttu-id="16231-247">コードでパック URI を指定するには、<xref:System.Uri> クラスをインスタンス化して、コンストラクターのパラメーターとしてパック URI を渡します。</span><span class="sxs-lookup"><span data-stu-id="16231-247">You specify a pack URI in code by instantiating the <xref:System.Uri> class and passing the pack URI as a parameter to the constructor.</span></span> <span data-ttu-id="16231-248">このコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16231-248">This is demonstrated in the following example.</span></span>

```csharp
Uri uri = new Uri("pack://application:,,,/File.xaml");
```

<span data-ttu-id="16231-249">既定では、<xref:System.Uri> クラスではパック URI は絶対とみなされます。</span><span class="sxs-lookup"><span data-stu-id="16231-249">By default, the <xref:System.Uri> class considers pack URIs to be absolute.</span></span> <span data-ttu-id="16231-250">そのため、相対パック URI で <xref:System.Uri> クラスのインスタンスが作成されると、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="16231-250">Consequently, an exception is raised when an instance of the <xref:System.Uri> class is created with a relative pack URI.</span></span>

```csharp
Uri uri = new Uri("/File.xaml");
```

<span data-ttu-id="16231-251">幸いにも、<xref:System.Uri> クラス コンストラクターの <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> オーバーロードでは、<xref:System.UriKind> 型のパラメーターを受け入れるため、パック URI が絶対か相対かを指定できます。</span><span class="sxs-lookup"><span data-stu-id="16231-251">Fortunately, the <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> overload of the <xref:System.Uri> class constructor accepts a parameter of type <xref:System.UriKind> to allow you to specify whether a pack URI is either absolute or relative.</span></span>

```csharp
// Absolute URI (default)
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);
// Relative URI
Uri relativeUri = new Uri("/File.xaml",
                        UriKind.Relative);
```

<span data-ttu-id="16231-252">提供されたパック URI がどちらであるかわかっているときには、<xref:System.UriKind.Absolute> または <xref:System.UriKind.Relative> のみを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16231-252">You should specify only <xref:System.UriKind.Absolute> or <xref:System.UriKind.Relative> when you are certain that the provided pack URI is one or the other.</span></span> <span data-ttu-id="16231-253">ユーザーが実行時にパック URI を入力するときなど、使用されるパック URI の種類がわからない場合は、代わりに <xref:System.UriKind.RelativeOrAbsolute> を使用します。</span><span class="sxs-lookup"><span data-stu-id="16231-253">If you don't know the type of pack URI that is used, such as when a user enters a pack URI at run time, use <xref:System.UriKind.RelativeOrAbsolute> instead.</span></span>

```csharp
// Relative or Absolute URI provided by user via a text box
TextBox userProvidedUriTextBox = new TextBox();
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);
```

<span data-ttu-id="16231-254">表 3 では、<xref:System.Uri?displayProperty=nameWithType> を使用してコードで指定できるさまざまな相対パック URI を示します。</span><span class="sxs-lookup"><span data-stu-id="16231-254">Table 3 illustrates the various relative pack URIs that you can specify in code by using <xref:System.Uri?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="16231-255">表 3:コードでの絶対パック URI</span><span class="sxs-lookup"><span data-stu-id="16231-255">Table 3: Absolute Pack URIs in Code</span></span>

|<span data-ttu-id="16231-256">ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-256">File</span></span>|<span data-ttu-id="16231-257">絶対パック URI</span><span class="sxs-lookup"><span data-stu-id="16231-257">Absolute pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="16231-258">リソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="16231-258">Resource file - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="16231-259">サブフォルダー内のリソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="16231-259">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="16231-260">リソース ファイル - 参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="16231-260">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="16231-261">参照アセンブリのサブフォルダー内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-261">Resource file in subfolder of referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="16231-262">バージョン管理された参照アセンブリ内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-262">Resource file in versioned referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="16231-263">コンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-263">Content file</span></span>|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="16231-264">サブフォルダー内のコンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-264">Content file in subfolder</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="16231-265">起点サイト ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-265">Site of origin file</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="16231-266">サブフォルダー内の起点サイト ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-266">Site of origin file in subfolder</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|

<span data-ttu-id="16231-267">表 4 では、<xref:System.Uri?displayProperty=nameWithType> を使用してコードで指定できるさまざまな相対パック URI を示します。</span><span class="sxs-lookup"><span data-stu-id="16231-267">Table 4 illustrates the various relative pack URIs that you can specify in code using <xref:System.Uri?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="16231-268">表 4:コードでの相対パック URI</span><span class="sxs-lookup"><span data-stu-id="16231-268">Table 4: Relative Pack URIs in Code</span></span>

|<span data-ttu-id="16231-269">ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-269">File</span></span>|<span data-ttu-id="16231-270">相対パック URI</span><span class="sxs-lookup"><span data-stu-id="16231-270">Relative pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="16231-271">リソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="16231-271">Resource file - local assembly</span></span>|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="16231-272">サブフォルダー内のリソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="16231-272">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="16231-273">リソース ファイル - 参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="16231-273">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="16231-274">サブフォルダー内のリソース ファイル - 参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="16231-274">Resource file in subfolder - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="16231-275">コンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-275">Content file</span></span>|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="16231-276">サブフォルダー内のコンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-276">Content file in subfolder</span></span>|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|

<a name="Common_Pack_URI_Scenarios"></a>

### <a name="common-pack-uri-scenarios"></a><span data-ttu-id="16231-277">一般的なパック URI のシナリオ</span><span class="sxs-lookup"><span data-stu-id="16231-277">Common Pack URI Scenarios</span></span>

<span data-ttu-id="16231-278">以前のセクションでは、パック URI を構築して、リソース ファイル、コンテンツ ファイル、および起点サイト ファイルを識別する方法を説明しました。</span><span class="sxs-lookup"><span data-stu-id="16231-278">The preceding sections have discussed how to construct pack URIs to identify resource, content, and site of origin files.</span></span> <span data-ttu-id="16231-279">WPF では、このような構築はさまざまな方法で使用されますが、以下のセクションでは、いくつかの一般的な用途について説明します。</span><span class="sxs-lookup"><span data-stu-id="16231-279">In WPF, these constructions are used in a variety of ways, and the following sections cover several common usages.</span></span>

<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>

#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a><span data-ttu-id="16231-280">アプリケーションの起動時に表示する UI の指定</span><span class="sxs-lookup"><span data-stu-id="16231-280">Specifying the UI to Show When an Application Starts</span></span>

<span data-ttu-id="16231-281"><xref:System.Windows.Application.StartupUri%2A> では、WPF アプリケーションの起動時に表示する最初の [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] を指定します。</span><span class="sxs-lookup"><span data-stu-id="16231-281"><xref:System.Windows.Application.StartupUri%2A> specifies the first [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to show when a WPF application is launched.</span></span> <span data-ttu-id="16231-282">スタンドアロン アプリケーションの場合、次の例に示されているように、[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] としてウィンドウを使用できます。</span><span class="sxs-lookup"><span data-stu-id="16231-282">For standalone applications, the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] can be a window, as shown in the following example.</span></span>

[!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]

<span data-ttu-id="16231-283">スタンドアロン アプリケーションと XAML ブラウザー アプリケーション (XBAP) では、次の例に示されているように、最初の UI としてページを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="16231-283">Standalone applications and XAML browser applications (XBAPs) can also specify a page as the initial UI, as shown in the following example.</span></span>

[!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]

<span data-ttu-id="16231-284">アプリケーションがスタンドアロン アプリケーションであり、ページが <xref:System.Windows.Application.StartupUri%2A> で指定されている場合、WPF は <xref:System.Windows.Navigation.NavigationWindow> を開いて、ページをホストします。</span><span class="sxs-lookup"><span data-stu-id="16231-284">If the application is a standalone application and a page is specified with <xref:System.Windows.Application.StartupUri%2A>, WPF opens a <xref:System.Windows.Navigation.NavigationWindow> to host the page.</span></span> <span data-ttu-id="16231-285">XBAP の場合、ページはホスト ブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="16231-285">For XBAPs, the page is shown in the host browser.</span></span>

<a name="Navigating_to_a_Page"></a>

#### <a name="navigating-to-a-page"></a><span data-ttu-id="16231-286">ページへのナビゲート</span><span class="sxs-lookup"><span data-stu-id="16231-286">Navigating to a Page</span></span>

<span data-ttu-id="16231-287">次の例は、ページにナビゲートする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="16231-287">The following example shows how to navigate to a page.</span></span>

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

<span data-ttu-id="16231-288">WPF でのさまざまなナビゲートの方法については、「[ナビゲーションの概要](navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16231-288">For more information on the various ways to navigate in WPF, see [Navigation Overview](navigation-overview.md).</span></span>

<a name="Specifying_a_Window_Icon"></a>

#### <a name="specifying-a-window-icon"></a><span data-ttu-id="16231-289">ウィンドウ アイコンの指定</span><span class="sxs-lookup"><span data-stu-id="16231-289">Specifying a Window Icon</span></span>

<span data-ttu-id="16231-290">次の例は、URI を使用してウィンドウのアイコンを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="16231-290">The following example shows how to use a URI to specify a window's icon.</span></span>

[!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]

<span data-ttu-id="16231-291">詳細については、「<xref:System.Windows.Window.Icon%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16231-291">For more information, see <xref:System.Windows.Window.Icon%2A>.</span></span>

<a name="Loading_Image__Audio__and_Video_Files"></a>

#### <a name="loading-image-audio-and-video-files"></a><span data-ttu-id="16231-292">イメージ ファイル、オーディオ ファイル、およびビデオ ファイルの読み込み</span><span class="sxs-lookup"><span data-stu-id="16231-292">Loading Image, Audio, and Video Files</span></span>

<span data-ttu-id="16231-293">WPF では、アプリケーションはさまざまな種類のメディアを使用でき、次の例に示されているように、そのすべてをパック URI で示して、読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="16231-293">WPF allows applications to use a wide variety of media types, all of which can be identified and loaded with pack URIs, as shown in the following examples.</span></span>

[!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]

[!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]

[!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]

<span data-ttu-id="16231-294">メディア コンテンツの操作方法の詳細については、「[グラフィックスとマルチ メディア](../graphics-multimedia/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16231-294">For more information on working with media content, see [Graphics and Multimedia](../graphics-multimedia/index.md).</span></span>

<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>

#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a><span data-ttu-id="16231-295">起点サイトからのリソース ディクショナリの読み込み</span><span class="sxs-lookup"><span data-stu-id="16231-295">Loading a Resource Dictionary from the Site of Origin</span></span>

<span data-ttu-id="16231-296">リソース ディクショナリ (<xref:System.Windows.ResourceDictionary>) を使用して、アプリケーションのテーマをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="16231-296">Resource dictionaries (<xref:System.Windows.ResourceDictionary>) can be used to support application themes.</span></span> <span data-ttu-id="16231-297">テーマを作成し、管理する方法の 1 つは、複数のテーマをリソース ディクショナリとして作成して、アプリケーションの起点サイトに配置することです。</span><span class="sxs-lookup"><span data-stu-id="16231-297">One way to create and manage themes is to create multiple themes as resource dictionaries that are located at an application's site of origin.</span></span> <span data-ttu-id="16231-298">これにより、アプリケーションを再コンパイルして再配置しなくても、テーマの追加と交信が可能です。</span><span class="sxs-lookup"><span data-stu-id="16231-298">This allows themes to be added and updated without recompiling and redeploying an application.</span></span> <span data-ttu-id="16231-299">これらのリソース ディクショナリは、次の例に示されているように、パック URI を使用して示し、読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="16231-299">These resource dictionaries can be identified and loaded using pack URIs, which is shown in the following example.</span></span>

[!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]

<span data-ttu-id="16231-300">WPF でのテーマの概要については、「[スタイルとテンプレート](../../../desktop-wpf/fundamentals/styles-templates-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16231-300">For an overview of themes in WPF, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="16231-301">関連項目</span><span class="sxs-lookup"><span data-stu-id="16231-301">See also</span></span>

- [<span data-ttu-id="16231-302">WPF アプリケーションのリソース ファイル、コンテンツ ファイル、およびデータ ファイル</span><span class="sxs-lookup"><span data-stu-id="16231-302">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
