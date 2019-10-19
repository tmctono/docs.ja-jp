---
title: WPF におけるパッケージの URI
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: 59c72d9ae12a014a8c47cb3b2852b337b173446c
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72580616"
---
# <a name="pack-uris-in-wpf"></a><span data-ttu-id="32897-102">WPF におけるパッケージの URI</span><span class="sxs-lookup"><span data-stu-id="32897-102">Pack URIs in WPF</span></span>

<span data-ttu-id="32897-103">Windows Presentation Foundation (WPF) では、次のようなさまざまな方法でファイルを識別し、読み込むために uniform resource identifier (Uri) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="32897-103">In Windows Presentation Foundation (WPF), uniform resource identifiers (URIs) are used to identify and load files in many ways, including the following:</span></span>

- <span data-ttu-id="32897-104">アプリケーションを初めて起動するときに表示する [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] を指定します。</span><span class="sxs-lookup"><span data-stu-id="32897-104">Specifying the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] to show when an application first starts.</span></span>

- <span data-ttu-id="32897-105">イメージの読み込み。</span><span class="sxs-lookup"><span data-stu-id="32897-105">Loading images.</span></span>

- <span data-ttu-id="32897-106">ページへの移動。</span><span class="sxs-lookup"><span data-stu-id="32897-106">Navigating to pages.</span></span>

- <span data-ttu-id="32897-107">実行可能でないデータ ファイルの読み込み。</span><span class="sxs-lookup"><span data-stu-id="32897-107">Loading non-executable data files.</span></span>

<span data-ttu-id="32897-108">さらに、Uri を使用して、次のようなさまざまな場所からファイルを識別し、読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="32897-108">Furthermore, URIs can be used to identify and load files from a variety of locations, including the following:</span></span>

- <span data-ttu-id="32897-109">現在のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="32897-109">The current assembly.</span></span>

- <span data-ttu-id="32897-110">参照アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="32897-110">A referenced assembly.</span></span>

- <span data-ttu-id="32897-111">アセンブリに対して相対的な位置。</span><span class="sxs-lookup"><span data-stu-id="32897-111">A location relative to an assembly.</span></span>

- <span data-ttu-id="32897-112">アプリケーションの起点サイト。</span><span class="sxs-lookup"><span data-stu-id="32897-112">The application's site of origin.</span></span>

<span data-ttu-id="32897-113">これらの場所からこれらの種類のファイルを識別し、読み込むための一貫したメカニズムを提供するために、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] は、*パック URI スキーム*の機能拡張を活用します。</span><span class="sxs-lookup"><span data-stu-id="32897-113">To provide a consistent mechanism for identifying and loading these types of files from these locations, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] leverages the extensibility of the *pack URI scheme*.</span></span> <span data-ttu-id="32897-114">このトピックでは、スキームの概要について説明します。また、マークアップとコードの両方からパック Uri を使用する方法を説明する前に、さまざまなシナリオ用のパック Uri を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="32897-114">This topic provides an overview of the scheme, covers how to construct pack URIs for a variety of scenarios, discusses absolute and relative URIs and URI resolution, before showing how to use pack URIs from both markup and code.</span></span>

<a name="The_Pack_URI_Scheme"></a>

## <a name="the-pack-uri-scheme"></a><span data-ttu-id="32897-115">パック URI スキーム</span><span class="sxs-lookup"><span data-stu-id="32897-115">The Pack URI Scheme</span></span>

<span data-ttu-id="32897-116">パッケージ URI スキームは、コンテンツを整理および識別するためのモデルを記述する[Open パッケージング規則](https://go.microsoft.com/fwlink/?LinkID=71255)(OPC) 仕様によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="32897-116">The pack URI scheme is used by the [Open Packaging Conventions](https://go.microsoft.com/fwlink/?LinkID=71255) (OPC) specification, which describes a model for organizing and identifying content.</span></span> <span data-ttu-id="32897-117">このモデルの主要な要素はパッケージとパーツで、*パッケージ*は1つ以上の論理*部分*の論理コンテナーです。</span><span class="sxs-lookup"><span data-stu-id="32897-117">The key elements of this model are packages and parts, where a *package* is a logical container for one or more logical *parts*.</span></span> <span data-ttu-id="32897-118">この概念を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="32897-118">The following figure illustrates this concept.</span></span>

![パッケージとパーツのダイアグラム](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)

<span data-ttu-id="32897-120">パーツを識別するために、OPC 仕様は、RFC 2396 (Uniform Resource Identifier (URI): Generic 構文) の機能拡張を利用して、パック URI スキームを定義します。</span><span class="sxs-lookup"><span data-stu-id="32897-120">To identify parts, the OPC specification leverages the extensibility of RFC 2396 (Uniform Resource Identifiers (URI): Generic Syntax) to define the pack URI scheme.</span></span>

<span data-ttu-id="32897-121">URI によって指定されるスキームは、そのプレフィックスによって定義されます。http、ftp、および file は、よく知られている例です。</span><span class="sxs-lookup"><span data-stu-id="32897-121">The scheme that is specified by a URI is defined by its prefix; http, ftp, and file are well-known examples.</span></span> <span data-ttu-id="32897-122">パック URI スキームでは、スキームとして "pack" が使用され、authority と path の2つのコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="32897-122">The pack URI scheme uses "pack" as its scheme, and contains two components: authority and path.</span></span> <span data-ttu-id="32897-123">パック URI の形式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="32897-123">The following is the format for a pack URI.</span></span>

<span data-ttu-id="32897-124">pack://*authority* /*パス*</span><span class="sxs-lookup"><span data-stu-id="32897-124">pack://*authority*/*path*</span></span>

<span data-ttu-id="32897-125">*Authority*は、パーツが含まれているパッケージの種類を指定し、*パス*はパッケージ内のパーツの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="32897-125">The *authority* specifies the type of package that a part is contained by, while the *path* specifies the location of a part within a package.</span></span>

<span data-ttu-id="32897-126">この概念を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="32897-126">This concept is illustrated by the following figure:</span></span>

![パッケージ、権限、およびパスの間のリレーションシップ](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)

<span data-ttu-id="32897-128">パッケージとパーツは、アプリケーションとファイルに似ています。つまり、アプリケーション (パッケージ) は、次のような 1 つ以上のファイル (パーツ) を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="32897-128">Packages and parts are analogous to applications and files, where an application (package) can include one or more files (parts), including:</span></span>

- <span data-ttu-id="32897-129">ローカル アセンブリにコンパイルされるリソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="32897-129">Resource files that are compiled into the local assembly.</span></span>

- <span data-ttu-id="32897-130">参照センブリにコンパイルされるリソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="32897-130">Resource files that are compiled into a referenced assembly.</span></span>

- <span data-ttu-id="32897-131">参照元センブリにコンパイルされるリソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="32897-131">Resource files that are compiled into a referencing assembly.</span></span>

- <span data-ttu-id="32897-132">コンテンツ ファイル。</span><span class="sxs-lookup"><span data-stu-id="32897-132">Content files.</span></span>

- <span data-ttu-id="32897-133">起点サイト ファイル。</span><span class="sxs-lookup"><span data-stu-id="32897-133">Site of origin files.</span></span>

<span data-ttu-id="32897-134">これらの種類のファイルにアクセスするために [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] では、application:///と siteoforigin:///の2つの機関がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="32897-134">To access these types of files, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] supports two authorities: application:/// and siteoforigin:///.</span></span> <span data-ttu-id="32897-135">application:/// オーソリティは、リソース ファイルやコンテンツ ファイルなど、コンパイル時に既知のアプリケーション データ ファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="32897-135">The application:/// authority identifies application data files that are known at compile time, including resource and content files.</span></span> <span data-ttu-id="32897-136">siteoforigin:/// オーソリティは、起点サイト ファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="32897-136">The siteoforigin:/// authority identifies site of origin files.</span></span> <span data-ttu-id="32897-137">各オーソリティのスコープを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="32897-137">The scope of each authority is shown in the following figure.</span></span>

![Pack URI のダイアグラム](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)

> [!NOTE]
> <span data-ttu-id="32897-139">パック URI の機関コンポーネントは、パッケージを指す埋め込み URI であり、RFC 2396 に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="32897-139">The authority component of a pack URI is an embedded URI that points to a package and must conform to RFC 2396.</span></span> <span data-ttu-id="32897-140">さらに、"/" 文字は "," 文字に置き換える必要があり、"%" や "?" などの予約文字はエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32897-140">Additionally, the "/" character must be replaced with the "," character, and reserved characters such as "%" and "?" must be escaped.</span></span> <span data-ttu-id="32897-141">詳細については、OPC を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32897-141">See the OPC for details.</span></span>

<span data-ttu-id="32897-142">以下のセクションでは、これらの2つの機関を使用して、リソース、コンテンツ、および起点サイトファイルを識別するための適切なパスと共に、パック Uri を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="32897-142">The following sections explain how to construct pack URIs using these two authorities in conjunction with the appropriate paths for identifying resource, content, and site of origin files.</span></span>

<a name="Resource_File_Pack_URIs___Local_Assembly"></a>

## <a name="resource-file-pack-uris"></a><span data-ttu-id="32897-143">リソース ファイルのパック URI</span><span class="sxs-lookup"><span data-stu-id="32897-143">Resource File Pack URIs</span></span>

<span data-ttu-id="32897-144">リソースファイルは MSBuild `Resource` 項目として構成され、アセンブリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="32897-144">Resource files are configured as MSBuild `Resource` items and are compiled into assemblies.</span></span> <span data-ttu-id="32897-145">WPF は、ローカルアセンブリにコンパイルされるか、ローカルアセンブリから参照されるアセンブリにコンパイルされるリソースファイルを識別するために使用できる、パック Uri の構築をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="32897-145">WPF supports the construction of pack URIs that can be used to identify resource files that are either compiled into the local assembly or compiled into an assembly that is referenced from the local assembly.</span></span>

<a name="Local_Assembly_Resource_File"></a>

### <a name="local-assembly-resource-file"></a><span data-ttu-id="32897-146">ローカル アセンブリ リソース ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-146">Local Assembly Resource File</span></span>

<span data-ttu-id="32897-147">ローカルアセンブリにコンパイルされるリソースファイルのパック URI は、次の権限とパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="32897-147">The pack URI for a resource file that is compiled into the local assembly uses the following authority and path:</span></span>

- <span data-ttu-id="32897-148">**オーソリティ**: application:///。</span><span class="sxs-lookup"><span data-stu-id="32897-148">**Authority**: application:///.</span></span>

- <span data-ttu-id="32897-149">**パス**: ローカル アセンブリのプロジェクト フォルダーのルートに対して相対的なパスを含むリソース ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="32897-149">**Path**: The name of the resource file, including its path, relative to the local assembly project folder root.</span></span>

<span data-ttu-id="32897-150">次の例は、ローカルアセンブリのプロジェクトフォルダーのルートにある [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] リソースファイルのパック URI を示しています。</span><span class="sxs-lookup"><span data-stu-id="32897-150">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the local assembly's project folder.</span></span>

`pack://application:,,,/ResourceFile.xaml`

<span data-ttu-id="32897-151">次の例は、ローカルアセンブリのプロジェクトフォルダーのサブフォルダーにある、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] リソースファイルのパック URI を示しています。</span><span class="sxs-lookup"><span data-stu-id="32897-151">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the local assembly's project folder.</span></span>

`pack://application:,,,/Subfolder/ResourceFile.xaml`

<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>

### <a name="referenced-assembly-resource-file"></a><span data-ttu-id="32897-152">参照アセンブリ リソース ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-152">Referenced Assembly Resource File</span></span>

<span data-ttu-id="32897-153">参照アセンブリにコンパイルされるリソースファイルのパック URI は、次の権限とパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="32897-153">The pack URI for a resource file that is compiled into a referenced assembly uses the following authority and path:</span></span>

- <span data-ttu-id="32897-154">**オーソリティ**: application:///。</span><span class="sxs-lookup"><span data-stu-id="32897-154">**Authority**: application:///.</span></span>

- <span data-ttu-id="32897-155">**パス**: 参照アセンブリにコンパイルされるリソース ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="32897-155">**Path**: The name of a resource file that is compiled into a referenced assembly.</span></span> <span data-ttu-id="32897-156">パスは、次の書式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="32897-156">The path must conform to the following format:</span></span>

  <span data-ttu-id="32897-157">*Assemblyshortname*{ *;バージョン*] { *;PublicKey*]、コンポーネント/*パス*</span><span class="sxs-lookup"><span data-stu-id="32897-157">*AssemblyShortName*{*;Version*]{*;PublicKey*];component/*Path*</span></span>

  - <span data-ttu-id="32897-158">**AssemblyShortName**: 参照アセンブリの短い名前。</span><span class="sxs-lookup"><span data-stu-id="32897-158">**AssemblyShortName**: the short name for the referenced assembly.</span></span>

  - <span data-ttu-id="32897-159">**;Version** (省略可能): リソース ファイルを含む参照アセンブリのバージョン。</span><span class="sxs-lookup"><span data-stu-id="32897-159">**;Version** [optional]: the version of the referenced assembly that contains the resource file.</span></span> <span data-ttu-id="32897-160">これは、同じ短い名前を持つ 2 つ以上の参照アセンブリが読み込まれるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="32897-160">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>

  - <span data-ttu-id="32897-161">**;PublicKey** (省略可能): 参照アセンブリの署名に使用された公開鍵。</span><span class="sxs-lookup"><span data-stu-id="32897-161">**;PublicKey** [optional]: the public key that was used to sign the referenced assembly.</span></span> <span data-ttu-id="32897-162">これは、同じ短い名前を持つ 2 つ以上の参照アセンブリが読み込まれるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="32897-162">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>

  - <span data-ttu-id="32897-163">**;component**: 参照されるアセンブリが、ローカル アセンブリから参照されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="32897-163">**;component**: specifies that the assembly being referred to is referenced from the local assembly.</span></span>

  - <span data-ttu-id="32897-164">**/Path**: 参照アセンブリのプロジェクト フォルダーのルートに対して相対的なパスを含むリソース ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="32897-164">**/Path**: the name of the resource file, including its path, relative to the root of the referenced assembly's project folder.</span></span>

<span data-ttu-id="32897-165">次の例は、参照アセンブリのプロジェクトフォルダーのルートにある [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] リソースファイルのパック URI を示しています。</span><span class="sxs-lookup"><span data-stu-id="32897-165">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the referenced assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`

<span data-ttu-id="32897-166">次の例は、参照アセンブリのプロジェクトフォルダーのサブフォルダーにある、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] リソースファイルのパック URI を示しています。</span><span class="sxs-lookup"><span data-stu-id="32897-166">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the referenced assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`

<span data-ttu-id="32897-167">次の例では、バージョン固有の参照アセンブリのプロジェクトフォルダーのルートフォルダーにある [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] リソースファイルのパック URI を示しています。</span><span class="sxs-lookup"><span data-stu-id="32897-167">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root folder of a referenced, version-specific assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`

<span data-ttu-id="32897-168">参照されるアセンブリリソースファイルのパック URI 構文は、application:///authority でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="32897-168">Note that the pack URI syntax for referenced assembly resource files can be used only with the application:/// authority.</span></span> <span data-ttu-id="32897-169">たとえば、次のは [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="32897-169">For example, the following is not supported in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span>

`pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`

<a name="Content_File_Pack_URIs"></a>

## <a name="content-file-pack-uris"></a><span data-ttu-id="32897-170">コンテンツ ファイルのパック URI</span><span class="sxs-lookup"><span data-stu-id="32897-170">Content File Pack URIs</span></span>

<span data-ttu-id="32897-171">コンテンツファイルのパック URI は、次の証明機関とパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="32897-171">The pack URI for a content file uses the following authority and path:</span></span>

- <span data-ttu-id="32897-172">**オーソリティ**: application:///。</span><span class="sxs-lookup"><span data-stu-id="32897-172">**Authority**: application:///.</span></span>

- <span data-ttu-id="32897-173">**パス**: アプリケーションのメインの実行可能アセンブリのファイル システム位置に対して相対的なパスを含む、コンテンツ ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="32897-173">**Path**: The name of the content file, including its path relative to the file system location of the application's main executable assembly.</span></span>

<span data-ttu-id="32897-174">次の例は、実行可能アセンブリと同じフォルダーにある [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] コンテンツファイルのパック URI を示しています。</span><span class="sxs-lookup"><span data-stu-id="32897-174">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in the same folder as the executable assembly.</span></span>

`pack://application:,,,/ContentFile.xaml`

<span data-ttu-id="32897-175">次の例は、アプリケーションの実行可能アセンブリに対して相対的なサブフォルダーにある [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] コンテンツファイルのパック URI を示しています。</span><span class="sxs-lookup"><span data-stu-id="32897-175">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in a subfolder that is relative to the application's executable assembly.</span></span>

`pack://application:,,,/Subfolder/ContentFile.xaml`

> [!NOTE]
> <span data-ttu-id="32897-176">HTML コンテンツファイルに移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="32897-176">HTML content files cannot be navigated to.</span></span> <span data-ttu-id="32897-177">URI スキームでは、起点サイトにある HTML ファイルへの移動のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="32897-177">The URI scheme only supports navigation to HTML files that are located at the site of origin.</span></span>

<a name="The_siteoforigin_____Authority"></a>

## <a name="site-of-origin-pack-uris"></a><span data-ttu-id="32897-178">起点サイトのパック URI</span><span class="sxs-lookup"><span data-stu-id="32897-178">Site of Origin Pack URIs</span></span>

<span data-ttu-id="32897-179">起点サイトファイルのパック URI は、次の権限とパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="32897-179">The pack URI for a site of origin file uses the following authority and path:</span></span>

- <span data-ttu-id="32897-180">**オーソリティ**: siteoforigin:///。</span><span class="sxs-lookup"><span data-stu-id="32897-180">**Authority**: siteoforigin:///.</span></span>

- <span data-ttu-id="32897-181">**パス**: 実行可能アセンブリの起動元の位置に対して相対的なパスを含む起点サイト ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="32897-181">**Path**: The name of the site of origin file, including its path relative to the location from which the executable assembly was launched.</span></span>

<span data-ttu-id="32897-182">次の例は、実行可能アセンブリの起動元の場所に格納されている元の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] サイトのパッケージ URI を示しています。</span><span class="sxs-lookup"><span data-stu-id="32897-182">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in the location from which the executable assembly is launched.</span></span>

`pack://siteoforigin:,,,/SiteOfOriginFile.xaml`

<span data-ttu-id="32897-183">次の例は、アプリケーションの実行可能アセンブリの起動元の場所を基準としたサブフォルダーに格納されている、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] サイトの起点サイトファイルのパック URI を示しています。</span><span class="sxs-lookup"><span data-stu-id="32897-183">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in subfolder that is relative to the location from which the application's executable assembly is launched.</span></span>

`pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`

<a name="Page_Files"></a>

## <a name="page-files"></a><span data-ttu-id="32897-184">ページ ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-184">Page Files</span></span>

<span data-ttu-id="32897-185">MSBuild `Page` 項目として構成された XAML ファイルは、リソースファイルと同じ方法でアセンブリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="32897-185">XAML files that are configured as MSBuild `Page` items are compiled into assemblies in the same way as resource files.</span></span> <span data-ttu-id="32897-186">そのため、リソースファイルのパック Uri を使用して、MSBuild `Page` 項目を識別できます。</span><span class="sxs-lookup"><span data-stu-id="32897-186">Consequently, MSBuild `Page` items can be identified using pack URIs for resource files.</span></span>

<span data-ttu-id="32897-187">通常、MSBuild `Page` 項目として構成される [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルの種類は、次のいずれかのルート要素となります。</span><span class="sxs-lookup"><span data-stu-id="32897-187">The types of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that are commonly configured as MSBuild`Page` items have one of the following as their root element:</span></span>

- <xref:System.Windows.Window?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Page?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>

- <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>

- <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>

- <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>

<a name="Absolute_vs_Relative_Pack_URIs"></a>

## <a name="absolute-vs-relative-pack-uris"></a><span data-ttu-id="32897-188">絶対パック Uri と相対パッケージ Uri</span><span class="sxs-lookup"><span data-stu-id="32897-188">Absolute vs. Relative Pack URIs</span></span>

<span data-ttu-id="32897-189">完全修飾パック URI には、スキーム、権限、およびパスが含まれており、これは絶対パック URI と見なされます。</span><span class="sxs-lookup"><span data-stu-id="32897-189">A fully qualified pack URI includes the scheme, the authority, and the path, and it is considered an absolute pack URI.</span></span> <span data-ttu-id="32897-190">開発者のための単純化として、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] の要素では、通常、パスのみを含む、相対パック URI を使用して適切な属性を設定できます。</span><span class="sxs-lookup"><span data-stu-id="32897-190">As a simplification for developers, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements typically allow you to set appropriate attributes with a relative pack URI, which includes only the path.</span></span>

<span data-ttu-id="32897-191">たとえば、ローカルアセンブリ内のリソースファイルの次の絶対パック URI について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="32897-191">For example, consider the following absolute pack URI for a resource file in the local assembly.</span></span>

`pack://application:,,,/ResourceFile.xaml`

<span data-ttu-id="32897-192">このリソースファイルを参照する相対パック URI は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="32897-192">The relative pack URI that refers to this resource file would be the following.</span></span>

`/ResourceFile.xaml`

> [!NOTE]
> <span data-ttu-id="32897-193">起点サイトファイルはアセンブリに関連付けられていないため、絶対パック Uri でのみ参照できます。</span><span class="sxs-lookup"><span data-stu-id="32897-193">Because site of origin files are not associated with assemblies, they can only be referred to with absolute pack URIs.</span></span>

<span data-ttu-id="32897-194">既定では、相対パック URI は、参照を含むマークアップまたはコードの位置を基準として相対的に見なされます。</span><span class="sxs-lookup"><span data-stu-id="32897-194">By default, a relative pack URI is considered relative to the location of the markup or code that contains the reference.</span></span> <span data-ttu-id="32897-195">ただし、先頭に円記号が使用されている場合、相対パック URI 参照は、アプリケーションのルートを基準として相対的に考慮されます。</span><span class="sxs-lookup"><span data-stu-id="32897-195">If a leading backslash is used, however, the relative pack URI reference is then considered relative to the root of the application.</span></span> <span data-ttu-id="32897-196">たとえば、次のようなプロジェクト構造を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="32897-196">For example, consider the following project structure.</span></span>

`App.xaml`

`Page2.xaml`

`\SubFolder`

`+ Page1.xaml`

`+ Page2.xaml`

<span data-ttu-id="32897-197">Page1 に*ルート*\SubFolder\Page2.xaml を参照する uri が含まれている場合、参照は次の相対パック URI を使用できます。</span><span class="sxs-lookup"><span data-stu-id="32897-197">If Page1.xaml contains a URI that references *Root*\SubFolder\Page2.xaml, the reference can use the following relative pack URI.</span></span>

`Page2.xaml`

<span data-ttu-id="32897-198">Page1 に、*ルート*の url が含まれている場合、この参照では、次の相対パック uri を使用できます。</span><span class="sxs-lookup"><span data-stu-id="32897-198">If Page1.xaml contains a URI that references *Root*\Page2.xaml, the reference can use the following relative pack URI.</span></span>

`/Page2.xaml`

<a name="Pack_URI_Resolution"></a>

## <a name="pack-uri-resolution"></a><span data-ttu-id="32897-199">パック URI の解決</span><span class="sxs-lookup"><span data-stu-id="32897-199">Pack URI Resolution</span></span>

<span data-ttu-id="32897-200">パック Uri の形式により、さまざまな種類のファイルのパック Uri を同じように表示できます。</span><span class="sxs-lookup"><span data-stu-id="32897-200">The format of pack URIs makes it possible for pack URIs for different types of files to look the same.</span></span> <span data-ttu-id="32897-201">たとえば、次の絶対パック URI を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="32897-201">For example, consider the following absolute pack URI.</span></span>

`pack://application:,,,/ResourceOrContentFile.xaml`

<span data-ttu-id="32897-202">この絶対パック URI は、ローカルアセンブリまたはコンテンツファイル内のリソースファイルを参照できます。</span><span class="sxs-lookup"><span data-stu-id="32897-202">This absolute pack URI could refer to either a resource file in the local assembly or a content file.</span></span> <span data-ttu-id="32897-203">これは、次の相対 URI にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="32897-203">The same is true for the following relative URI.</span></span>

`/ResourceOrContentFile.xaml`

<span data-ttu-id="32897-204">パック URI が参照するファイルの種類を特定するために、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] は次のヒューリスティックを使用して、ローカルアセンブリおよびコンテンツファイル内のリソースファイルの Uri を解決します。</span><span class="sxs-lookup"><span data-stu-id="32897-204">In order to determine the type of file that a pack URI refers to, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] resolves URIs for resource files in local assemblies and content files by using the following heuristics:</span></span>

1. <span data-ttu-id="32897-205">パッケージの URI に一致する <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 属性のアセンブリメタデータをプローブします。</span><span class="sxs-lookup"><span data-stu-id="32897-205">Probe the assembly metadata for an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute that matches the pack URI.</span></span>

2. <span data-ttu-id="32897-206">@No__t_0 属性が見つかった場合、パック URI のパスはコンテンツファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="32897-206">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is found, the path of the pack URI refers to a content file.</span></span>

3. <span data-ttu-id="32897-207">@No__t_0 属性が見つからない場合は、ローカルアセンブリにコンパイルされる set リソースファイルを調べます。</span><span class="sxs-lookup"><span data-stu-id="32897-207">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is not found, probe the set resource files that are compiled into the local assembly.</span></span>

4. <span data-ttu-id="32897-208">パック URI のパスに一致するリソースファイルが見つかった場合、パック URI のパスはリソースファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="32897-208">If a resource file that matches the path of the pack URI is found, the path of the pack URI refers to a resource file.</span></span>

5. <span data-ttu-id="32897-209">リソースが見つからない場合、内部で作成された <xref:System.Uri> は無効です。</span><span class="sxs-lookup"><span data-stu-id="32897-209">If the resource is not found, the internally created <xref:System.Uri> is invalid.</span></span>

<span data-ttu-id="32897-210">URI 解決は、次を参照する Uri には適用されません。</span><span class="sxs-lookup"><span data-stu-id="32897-210">URI resolution does not apply for URIs that refer to the following:</span></span>

- <span data-ttu-id="32897-211">参照アセンブリ内のコンテンツファイル: これらのファイルの種類は、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="32897-211">Content files in referenced assemblies: these file types are not supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span>

- <span data-ttu-id="32897-212">参照アセンブリ内の埋め込みファイル: 参照されるアセンブリの名前と `;component` サフィックスの両方が含まれているため、それらを識別する Uri は一意です。</span><span class="sxs-lookup"><span data-stu-id="32897-212">Embedded files in referenced assemblies: URIs that identify them are unique because they include both the name of the referenced assembly and the `;component` suffix.</span></span>

- <span data-ttu-id="32897-213">起点サイトファイル: siteoforigin:///機関を含むパック Uri によって識別できる唯一のファイルであるため、それらを識別する Uri は一意です。</span><span class="sxs-lookup"><span data-stu-id="32897-213">Site of origin files: URIs that identify them are unique because they are the only files that can be identified by pack URIs that contain the siteoforigin:/// authority.</span></span>

<span data-ttu-id="32897-214">パッケージ URI 解決が可能な1つの単純化は、コードがリソースファイルとコンテンツファイルの場所から多少独立していることです。</span><span class="sxs-lookup"><span data-stu-id="32897-214">One simplification that pack URI resolution allows is for code to be somewhat independent of the locations of resource and content files.</span></span> <span data-ttu-id="32897-215">たとえば、ローカルアセンブリ内のリソースファイルがコンテンツファイルとして再構成されている場合、そのリソースのパック URI は、パック URI を使用するコードと同じように変わりません。</span><span class="sxs-lookup"><span data-stu-id="32897-215">For example, if you have a resource file in the local assembly that is reconfigured to be a content file, the pack URI for the resource remains the same, as does the code that uses the pack URI.</span></span>

<a name="Programming_with_Pack_URIs"></a>

## <a name="programming-with-pack-uris"></a><span data-ttu-id="32897-216">パック URI を使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="32897-216">Programming with Pack URIs</span></span>

<span data-ttu-id="32897-217">多くの [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] クラスには、次のようなパック Uri で設定できるプロパティが実装されています。</span><span class="sxs-lookup"><span data-stu-id="32897-217">Many [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] classes implement properties that can be set with pack URIs, including:</span></span>

- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>

<span data-ttu-id="32897-218">これらのプロパティは、マークアップとコードのどちらからでも設定できます。</span><span class="sxs-lookup"><span data-stu-id="32897-218">These properties can be set from both markup and code.</span></span> <span data-ttu-id="32897-219">このセクションでは、両方の基本構造について説明してから、一般的なシナリオの例を示します。</span><span class="sxs-lookup"><span data-stu-id="32897-219">This section demonstrates the basic constructions for both and then shows examples of common scenarios.</span></span>

<a name="Using_Pack_URIs_in_Markup"></a>

### <a name="using-pack-uris-in-markup"></a><span data-ttu-id="32897-220">マークアップでのパック URI の使用</span><span class="sxs-lookup"><span data-stu-id="32897-220">Using Pack URIs in Markup</span></span>

<span data-ttu-id="32897-221">パック URI をマークアップで指定するには、属性の要素にパック URI を設定します。</span><span class="sxs-lookup"><span data-stu-id="32897-221">A pack URI is specified in markup by setting the element of an attribute with the pack URI.</span></span> <span data-ttu-id="32897-222">(例:</span><span class="sxs-lookup"><span data-stu-id="32897-222">For example:</span></span>

`<element attribute="pack://application:,,,/File.xaml" />`

<span data-ttu-id="32897-223">表1は、マークアップで指定できるさまざまな絶対パック Uri を示しています。</span><span class="sxs-lookup"><span data-stu-id="32897-223">Table 1 illustrates the various absolute pack URIs that you can specify in markup.</span></span>

<span data-ttu-id="32897-224">表 1: マークアップでの絶対パック URI</span><span class="sxs-lookup"><span data-stu-id="32897-224">Table 1: Absolute Pack URIs in Markup</span></span>

|<span data-ttu-id="32897-225">ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-225">File</span></span>|<span data-ttu-id="32897-226">絶対パック URI</span><span class="sxs-lookup"><span data-stu-id="32897-226">Absolute pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="32897-227">リソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="32897-227">Resource file - local assembly</span></span>|`"pack://application:,,,/ResourceFile.xaml"`|
|<span data-ttu-id="32897-228">サブフォルダー内のリソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="32897-228">Resource file in subfolder - local assembly</span></span>|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="32897-229">リソース ファイル - 参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="32897-229">Resource file - referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|
|<span data-ttu-id="32897-230">参照アセンブリのサブフォルダー内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-230">Resource file in subfolder of referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="32897-231">バージョン管理された参照アセンブリ内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-231">Resource file in versioned referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|
|<span data-ttu-id="32897-232">コンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-232">Content file</span></span>|`"pack://application:,,,/ContentFile.xaml"`|
|<span data-ttu-id="32897-233">サブフォルダー内のコンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-233">Content file in subfolder</span></span>|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|
|<span data-ttu-id="32897-234">起点サイト ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-234">Site of origin file</span></span>|`"pack://siteoforigin:,,,/SOOFile.xaml"`|
|<span data-ttu-id="32897-235">サブフォルダー内の起点サイト ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-235">Site of origin file in subfolder</span></span>|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|

<span data-ttu-id="32897-236">表2は、マークアップで指定できるさまざまな相対パック Uri を示しています。</span><span class="sxs-lookup"><span data-stu-id="32897-236">Table 2 illustrates the various relative pack URIs that you can specify in markup.</span></span>

<span data-ttu-id="32897-237">表 2: マークアップでの相対パック URI</span><span class="sxs-lookup"><span data-stu-id="32897-237">Table 2: Relative Pack URIs in Markup</span></span>

|<span data-ttu-id="32897-238">ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-238">File</span></span>|<span data-ttu-id="32897-239">相対パック URI</span><span class="sxs-lookup"><span data-stu-id="32897-239">Relative pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="32897-240">ローカル アセンブリ内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-240">Resource file in local assembly</span></span>|`"/ResourceFile.xaml"`|
|<span data-ttu-id="32897-241">ローカル アセンブリのサブフォルダー内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-241">Resource file in subfolder of local assembly</span></span>|`"/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="32897-242">参照アセンブリ内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-242">Resource file in referenced assembly</span></span>|`"/ReferencedAssembly;component/ResourceFile.xaml"`|
|<span data-ttu-id="32897-243">参照アセンブリのサブフォルダー内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-243">Resource file in subfolder of referenced assembly</span></span>|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="32897-244">コンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-244">Content file</span></span>|`"/ContentFile.xaml"`|
|<span data-ttu-id="32897-245">サブフォルダー内のコンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-245">Content file in subfolder</span></span>|`"/Subfolder/ContentFile.xaml"`|

<a name="Using_Pack_URIs_in_Code"></a>

### <a name="using-pack-uris-in-code"></a><span data-ttu-id="32897-246">コードでのパック URI の使用</span><span class="sxs-lookup"><span data-stu-id="32897-246">Using Pack URIs in Code</span></span>

<span data-ttu-id="32897-247">コードでパック URI を指定するには、<xref:System.Uri> クラスをインスタンス化し、パック URI をパラメーターとしてコンストラクターに渡します。</span><span class="sxs-lookup"><span data-stu-id="32897-247">You specify a pack URI in code by instantiating the <xref:System.Uri> class and passing the pack URI as a parameter to the constructor.</span></span> <span data-ttu-id="32897-248">このコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="32897-248">This is demonstrated in the following example.</span></span>

```csharp
Uri uri = new Uri("pack://application:,,,/File.xaml");
```

<span data-ttu-id="32897-249">既定では、<xref:System.Uri> クラスは、パック Uri を絶対値と見なします。</span><span class="sxs-lookup"><span data-stu-id="32897-249">By default, the <xref:System.Uri> class considers pack URIs to be absolute.</span></span> <span data-ttu-id="32897-250">その結果、<xref:System.Uri> クラスのインスタンスが、相対パック URI を使用して作成されたときに例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="32897-250">Consequently, an exception is raised when an instance of the <xref:System.Uri> class is created with a relative pack URI.</span></span>

```csharp
Uri uri = new Uri("/File.xaml");
```

<span data-ttu-id="32897-251">幸いにも、<xref:System.Uri> クラスコンストラクターの <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> オーバーロードは <xref:System.UriKind> 型のパラメーターを受け取り、パック URI が絶対か相対かを指定できます。</span><span class="sxs-lookup"><span data-stu-id="32897-251">Fortunately, the <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> overload of the <xref:System.Uri> class constructor accepts a parameter of type <xref:System.UriKind> to allow you to specify whether a pack URI is either absolute or relative.</span></span>

```csharp
// Absolute URI (default)
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);
// Relative URI
Uri relativeUri = new Uri("/File.xaml",
                        UriKind.Relative);
```

<span data-ttu-id="32897-252">指定されたパック URI がいずれかであることが確実である場合は、<xref:System.UriKind.Absolute> または <xref:System.UriKind.Relative> のみを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32897-252">You should specify only <xref:System.UriKind.Absolute> or <xref:System.UriKind.Relative> when you are certain that the provided pack URI is one or the other.</span></span> <span data-ttu-id="32897-253">実行時にユーザーがパック URI を入力したときなど、使用されているパック URI の種類がわからない場合は、代わりに <xref:System.UriKind.RelativeOrAbsolute> を使用します。</span><span class="sxs-lookup"><span data-stu-id="32897-253">If you don't know the type of pack URI that is used, such as when a user enters a pack URI at run time, use <xref:System.UriKind.RelativeOrAbsolute> instead.</span></span>

```csharp
// Relative or Absolute URI provided by user via a text box
TextBox userProvidedUriTextBox = new TextBox();
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);
```

<span data-ttu-id="32897-254">表3は、<xref:System.Uri?displayProperty=nameWithType> を使用してコードで指定できる、さまざまな相対パック Uri を示しています。</span><span class="sxs-lookup"><span data-stu-id="32897-254">Table 3 illustrates the various relative pack URIs that you can specify in code by using <xref:System.Uri?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="32897-255">表 3: コードでの絶対パック URI</span><span class="sxs-lookup"><span data-stu-id="32897-255">Table 3: Absolute Pack URIs in Code</span></span>

|<span data-ttu-id="32897-256">ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-256">File</span></span>|<span data-ttu-id="32897-257">絶対パック URI</span><span class="sxs-lookup"><span data-stu-id="32897-257">Absolute pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="32897-258">リソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="32897-258">Resource file - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="32897-259">サブフォルダー内のリソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="32897-259">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="32897-260">リソース ファイル - 参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="32897-260">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="32897-261">参照アセンブリのサブフォルダー内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-261">Resource file in subfolder of referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="32897-262">バージョン管理された参照アセンブリ内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-262">Resource file in versioned referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="32897-263">コンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-263">Content file</span></span>|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="32897-264">サブフォルダー内のコンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-264">Content file in subfolder</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="32897-265">起点サイト ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-265">Site of origin file</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="32897-266">サブフォルダー内の起点サイト ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-266">Site of origin file in subfolder</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|

<span data-ttu-id="32897-267">表4は、<xref:System.Uri?displayProperty=nameWithType> を使用してコードで指定できる、さまざまな相対パック Uri を示しています。</span><span class="sxs-lookup"><span data-stu-id="32897-267">Table 4 illustrates the various relative pack URIs that you can specify in code using <xref:System.Uri?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="32897-268">表 4: コードでの相対パック URI</span><span class="sxs-lookup"><span data-stu-id="32897-268">Table 4: Relative Pack URIs in Code</span></span>

|<span data-ttu-id="32897-269">ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-269">File</span></span>|<span data-ttu-id="32897-270">相対パック URI</span><span class="sxs-lookup"><span data-stu-id="32897-270">Relative pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="32897-271">リソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="32897-271">Resource file - local assembly</span></span>|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="32897-272">サブフォルダー内のリソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="32897-272">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="32897-273">リソース ファイル - 参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="32897-273">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="32897-274">サブフォルダー内のリソース ファイル - 参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="32897-274">Resource file in subfolder - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="32897-275">コンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-275">Content file</span></span>|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="32897-276">サブフォルダー内のコンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-276">Content file in subfolder</span></span>|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|

<a name="Common_Pack_URI_Scenarios"></a>

### <a name="common-pack-uri-scenarios"></a><span data-ttu-id="32897-277">一般的なパック URI のシナリオ</span><span class="sxs-lookup"><span data-stu-id="32897-277">Common Pack URI Scenarios</span></span>

<span data-ttu-id="32897-278">前のセクションでは、リソース、コンテンツ、および起点サイトファイルを識別するために、パック Uri を作成する方法について説明しました。</span><span class="sxs-lookup"><span data-stu-id="32897-278">The preceding sections have discussed how to construct pack URIs to identify resource, content, and site of origin files.</span></span> <span data-ttu-id="32897-279">@No__t_0 では、これらの構造はさまざまな方法で使用されます。次のセクションでは、いくつかの一般的な使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="32897-279">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], these constructions are used in a variety of ways, and the following sections cover several common usages.</span></span>

<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>

#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a><span data-ttu-id="32897-280">アプリケーションの起動時に表示する UI の指定</span><span class="sxs-lookup"><span data-stu-id="32897-280">Specifying the UI to Show When an Application Starts</span></span>

<span data-ttu-id="32897-281"><xref:System.Windows.Application.StartupUri%2A> は、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] アプリケーションが起動されたときに表示する最初の [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] を指定します。</span><span class="sxs-lookup"><span data-stu-id="32897-281"><xref:System.Windows.Application.StartupUri%2A> specifies the first [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to show when a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application is launched.</span></span> <span data-ttu-id="32897-282">スタンドアロンアプリケーションの場合は、次の例に示すように、[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] をウィンドウにすることができます。</span><span class="sxs-lookup"><span data-stu-id="32897-282">For standalone applications, the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] can be a window, as shown in the following example.</span></span>

[!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]

<span data-ttu-id="32897-283">スタンドアロンアプリケーションと [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] では、次の例に示すように、最初の UI としてページを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="32897-283">Standalone applications and [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] can also specify a page as the initial UI, as shown in the following example.</span></span>

[!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]

<span data-ttu-id="32897-284">アプリケーションがスタンドアロンアプリケーションであり、<xref:System.Windows.Application.StartupUri%2A> でページが指定されている場合、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] はページをホストするための <xref:System.Windows.Navigation.NavigationWindow> を開きます。</span><span class="sxs-lookup"><span data-stu-id="32897-284">If the application is a standalone application and a page is specified with <xref:System.Windows.Application.StartupUri%2A>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] opens a <xref:System.Windows.Navigation.NavigationWindow> to host the page.</span></span> <span data-ttu-id="32897-285">@No__t_0 の場合、ページはホストブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="32897-285">For [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], the page is shown in the host browser.</span></span>

<a name="Navigating_to_a_Page"></a>

#### <a name="navigating-to-a-page"></a><span data-ttu-id="32897-286">ページへのナビゲート</span><span class="sxs-lookup"><span data-stu-id="32897-286">Navigating to a Page</span></span>

<span data-ttu-id="32897-287">次の例は、ページにナビゲートする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="32897-287">The following example shows how to navigate to a page.</span></span>

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

<span data-ttu-id="32897-288">@No__t_0 内で移動するさまざまな方法の詳細については、「[ナビゲーションの概要](navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32897-288">For more information on the various ways to navigate in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], see [Navigation Overview](navigation-overview.md).</span></span>

<a name="Specifying_a_Window_Icon"></a>

#### <a name="specifying-a-window-icon"></a><span data-ttu-id="32897-289">ウィンドウ アイコンの指定</span><span class="sxs-lookup"><span data-stu-id="32897-289">Specifying a Window Icon</span></span>

<span data-ttu-id="32897-290">次の例は、URI を使用してウィンドウのアイコンを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="32897-290">The following example shows how to use a URI to specify a window's icon.</span></span>

[!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]

<span data-ttu-id="32897-291">詳細については、「<xref:System.Windows.Window.Icon%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32897-291">For more information, see <xref:System.Windows.Window.Icon%2A>.</span></span>

<a name="Loading_Image__Audio__and_Video_Files"></a>

#### <a name="loading-image-audio-and-video-files"></a><span data-ttu-id="32897-292">イメージ ファイル、オーディオ ファイル、およびビデオ ファイルの読み込み</span><span class="sxs-lookup"><span data-stu-id="32897-292">Loading Image, Audio, and Video Files</span></span>

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="32897-293">では、次の例に示すように、アプリケーションでさまざまな種類のメディアを使用して、そのすべてを識別し、パック Uri で読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="32897-293">allows applications to use a wide variety of media types, all of which can be identified and loaded with pack URIs, as shown in the following examples.</span></span>

[!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]

[!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]

[!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]

<span data-ttu-id="32897-294">メディアコンテンツの操作の詳細については、「[グラフィックスとマルチメディア](../graphics-multimedia/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32897-294">For more information on working with media content, see [Graphics and Multimedia](../graphics-multimedia/index.md).</span></span>

<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>

#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a><span data-ttu-id="32897-295">起点サイトからのリソース ディクショナリの読み込み</span><span class="sxs-lookup"><span data-stu-id="32897-295">Loading a Resource Dictionary from the Site of Origin</span></span>

<span data-ttu-id="32897-296">リソースディクショナリ (<xref:System.Windows.ResourceDictionary>) は、アプリケーションテーマをサポートするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="32897-296">Resource dictionaries (<xref:System.Windows.ResourceDictionary>) can be used to support application themes.</span></span> <span data-ttu-id="32897-297">テーマを作成し、管理する方法の 1 つは、複数のテーマをリソース ディクショナリとして作成して、アプリケーションの起点サイトに配置することです。</span><span class="sxs-lookup"><span data-stu-id="32897-297">One way to create and manage themes is to create multiple themes as resource dictionaries that are located at an application's site of origin.</span></span> <span data-ttu-id="32897-298">これにより、アプリケーションを再コンパイルして再配置しなくても、テーマの追加と交信が可能です。</span><span class="sxs-lookup"><span data-stu-id="32897-298">This allows themes to be added and updated without recompiling and redeploying an application.</span></span> <span data-ttu-id="32897-299">これらのリソースディクショナリは、次の例に示すように、パック Uri を使用して識別および読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="32897-299">These resource dictionaries can be identified and loaded using pack URIs, which is shown in the following example.</span></span>

[!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]

<span data-ttu-id="32897-300">@No__t_0 のテーマの概要については、「[スタイルとテンプレート](../controls/styling-and-templating.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32897-300">For an overview of themes in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], see [Styling and Templating](../controls/styling-and-templating.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="32897-301">関連項目</span><span class="sxs-lookup"><span data-stu-id="32897-301">See also</span></span>

- [<span data-ttu-id="32897-302">WPF アプリケーションのリソース ファイル、コンテンツ ファイル、およびデータ ファイル</span><span class="sxs-lookup"><span data-stu-id="32897-302">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
