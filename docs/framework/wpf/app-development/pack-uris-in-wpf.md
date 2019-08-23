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
ms.openlocfilehash: ad928fb223ce22c65bb86a78c7d4cd006651a2d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950753"
---
# <a name="pack-uris-in-wpf"></a><span data-ttu-id="3c845-102">WPF におけるパッケージの URI</span><span class="sxs-lookup"><span data-stu-id="3c845-102">Pack URIs in WPF</span></span>

<span data-ttu-id="3c845-103">Windows Presentation Foundation (WPF) では[!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] 、を使用して、次のようなさまざまな方法でファイルを識別し、読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="3c845-103">In Windows Presentation Foundation (WPF), [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] are used to identify and load files in many ways, including the following:</span></span>

- <span data-ttu-id="3c845-104">アプリケーションを[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]初めて起動するときに表示するを指定します。</span><span class="sxs-lookup"><span data-stu-id="3c845-104">Specifying the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] to show when an application first starts.</span></span>

- <span data-ttu-id="3c845-105">イメージの読み込み。</span><span class="sxs-lookup"><span data-stu-id="3c845-105">Loading images.</span></span>

- <span data-ttu-id="3c845-106">ページへの移動。</span><span class="sxs-lookup"><span data-stu-id="3c845-106">Navigating to pages.</span></span>

- <span data-ttu-id="3c845-107">実行可能でないデータ ファイルの読み込み。</span><span class="sxs-lookup"><span data-stu-id="3c845-107">Loading non-executable data files.</span></span>

<span data-ttu-id="3c845-108">さらに[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 、を使用して、次のようなさまざまな場所からファイルを識別し、読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="3c845-108">Furthermore, [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] can be used to identify and load files from a variety of locations, including the following:</span></span>

- <span data-ttu-id="3c845-109">現在のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="3c845-109">The current assembly.</span></span>

- <span data-ttu-id="3c845-110">参照アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="3c845-110">A referenced assembly.</span></span>

- <span data-ttu-id="3c845-111">アセンブリに対して相対的な位置。</span><span class="sxs-lookup"><span data-stu-id="3c845-111">A location relative to an assembly.</span></span>

- <span data-ttu-id="3c845-112">アプリケーションの起点サイト。</span><span class="sxs-lookup"><span data-stu-id="3c845-112">The application's site of origin.</span></span>

<span data-ttu-id="3c845-113">これらの場所からこれらの種類のファイルを識別して読み込むための一貫[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]したメカニズムを提供するため、では、*パック URI スキーム*の拡張性を活用しています。</span><span class="sxs-lookup"><span data-stu-id="3c845-113">To provide a consistent mechanism for identifying and loading these types of files from these locations, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] leverages the extensibility of the *pack URI scheme*.</span></span> <span data-ttu-id="3c845-114">このトピックでは、スキームの概要について説明し、 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]さまざまなシナリオでパックを作成する方法について説明します。また、両方[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]のマークアップからパックを使用する方法を説明する前に、絶対と相対[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]および[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]解決方法について説明します。コードを記述します。</span><span class="sxs-lookup"><span data-stu-id="3c845-114">This topic provides an overview of the scheme, covers how to construct pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for a variety of scenarios, discusses absolute and relative [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] and [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] resolution, before showing how to use pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] from both markup and code.</span></span>

<a name="The_Pack_URI_Scheme"></a>

## <a name="the-pack-uri-scheme"></a><span data-ttu-id="3c845-115">パック URI スキーム</span><span class="sxs-lookup"><span data-stu-id="3c845-115">The Pack URI Scheme</span></span>

<span data-ttu-id="3c845-116">パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]スキームは、コンテンツを整理および識別するためのモデルを記述する[Open パッケージング規則](https://go.microsoft.com/fwlink/?LinkID=71255)(OPC) 仕様によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="3c845-116">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme is used by the [Open Packaging Conventions](https://go.microsoft.com/fwlink/?LinkID=71255) (OPC) specification, which describes a model for organizing and identifying content.</span></span> <span data-ttu-id="3c845-117">このモデルの主要な要素はパッケージとパーツで、*パッケージ*は1つ以上の論理*部分*の論理コンテナーです。</span><span class="sxs-lookup"><span data-stu-id="3c845-117">The key elements of this model are packages and parts, where a *package* is a logical container for one or more logical *parts*.</span></span> <span data-ttu-id="3c845-118">この概念を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="3c845-118">The following figure illustrates this concept.</span></span>

![パッケージとパーツのダイアグラム](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)

<span data-ttu-id="3c845-120">パーツを識別するために、OPC 仕様では RFC 2396 (Uniform Resource Identifier (URI)) の拡張性を活用しています。汎用構文) パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]スキームを定義します。</span><span class="sxs-lookup"><span data-stu-id="3c845-120">To identify parts, the OPC specification leverages the extensibility of RFC 2396 (Uniform Resource Identifiers (URI): Generic Syntax) to define the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme.</span></span>

<span data-ttu-id="3c845-121">によっ[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]て指定されるスキームは、そのプレフィックスによって定義されます。 http、ftp、および file は、よく知られている例です。</span><span class="sxs-lookup"><span data-stu-id="3c845-121">The scheme that is specified by a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is defined by its prefix; http, ftp, and file are well-known examples.</span></span> <span data-ttu-id="3c845-122">パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]スキームは、スキームとして "pack" を使用し、authority と path という2つのコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c845-122">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme uses "pack" as its scheme, and contains two components: authority and path.</span></span> <span data-ttu-id="3c845-123">パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]の形式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3c845-123">The following is the format for a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>

<span data-ttu-id="3c845-124">pack://*authority*/*パス*</span><span class="sxs-lookup"><span data-stu-id="3c845-124">pack://*authority*/*path*</span></span>

<span data-ttu-id="3c845-125">*Authority*は、パーツが含まれているパッケージの種類を指定し、*パス*はパッケージ内のパーツの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c845-125">The *authority* specifies the type of package that a part is contained by, while the *path* specifies the location of a part within a package.</span></span>

<span data-ttu-id="3c845-126">この概念を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="3c845-126">This concept is illustrated by the following figure:</span></span>

![パッケージ、権限、およびパスの間のリレーションシップ](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)

<span data-ttu-id="3c845-128">パッケージとパーツは、アプリケーションとファイルに似ています。つまり、アプリケーション (パッケージ) は、次のような 1 つ以上のファイル (パーツ) を含むことができます。</span><span class="sxs-lookup"><span data-stu-id="3c845-128">Packages and parts are analogous to applications and files, where an application (package) can include one or more files (parts), including:</span></span>

- <span data-ttu-id="3c845-129">ローカル アセンブリにコンパイルされるリソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="3c845-129">Resource files that are compiled into the local assembly.</span></span>

- <span data-ttu-id="3c845-130">参照センブリにコンパイルされるリソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="3c845-130">Resource files that are compiled into a referenced assembly.</span></span>

- <span data-ttu-id="3c845-131">参照元センブリにコンパイルされるリソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="3c845-131">Resource files that are compiled into a referencing assembly.</span></span>

- <span data-ttu-id="3c845-132">コンテンツ ファイル。</span><span class="sxs-lookup"><span data-stu-id="3c845-132">Content files.</span></span>

- <span data-ttu-id="3c845-133">起点サイト ファイル。</span><span class="sxs-lookup"><span data-stu-id="3c845-133">Site of origin files.</span></span>

<span data-ttu-id="3c845-134">これらの種類のファイルにアクセス[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]するために、では application:///と siteoforigin:///の2つの機関がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3c845-134">To access these types of files, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] supports two authorities: application:/// and siteoforigin:///.</span></span> <span data-ttu-id="3c845-135">application:/// オーソリティは、リソース ファイルやコンテンツ ファイルなど、コンパイル時に既知のアプリケーション データ ファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="3c845-135">The application:/// authority identifies application data files that are known at compile time, including resource and content files.</span></span> <span data-ttu-id="3c845-136">siteoforigin:/// オーソリティは、起点サイト ファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="3c845-136">The siteoforigin:/// authority identifies site of origin files.</span></span> <span data-ttu-id="3c845-137">各オーソリティのスコープを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="3c845-137">The scope of each authority is shown in the following figure.</span></span>

![Pack URI のダイアグラム](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)

> [!NOTE]
> <span data-ttu-id="3c845-139">パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]の機関コンポーネントは、パッケージを指す[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]埋め込みで、RFC 2396 に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c845-139">The authority component of a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is an embedded [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that points to a package and must conform to RFC 2396.</span></span> <span data-ttu-id="3c845-140">さらに、"/" 文字は "," 文字に置き換える必要があり、"%" や "?" などの予約文字はエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c845-140">Additionally, the "/" character must be replaced with the "," character, and reserved characters such as "%" and "?" must be escaped.</span></span> <span data-ttu-id="3c845-141">詳細については、OPC を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c845-141">See the OPC for details.</span></span>

<span data-ttu-id="3c845-142">以下のセクションでは、これらの[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 2 つの機関を使用して、リソース、コンテンツ、および起点サイトファイルを識別するための適切なパスと共にパックを構築する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c845-142">The following sections explain how to construct pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] using these two authorities in conjunction with the appropriate paths for identifying resource, content, and site of origin files.</span></span>

<a name="Resource_File_Pack_URIs___Local_Assembly"></a>

## <a name="resource-file-pack-uris"></a><span data-ttu-id="3c845-143">リソース ファイルのパック URI</span><span class="sxs-lookup"><span data-stu-id="3c845-143">Resource File Pack URIs</span></span>

<span data-ttu-id="3c845-144">リソースファイルは MSBuild `Resource`項目として構成され、アセンブリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="3c845-144">Resource files are configured as MSBuild `Resource` items and are compiled into assemblies.</span></span> <span data-ttu-id="3c845-145">WPF は、ローカルアセンブリにコンパイルされるか、ローカルアセンブリから参照されるアセンブリにコンパイルされるリソースファイルを識別するために使用できる、パック Uri の構築をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3c845-145">WPF supports the construction of pack URIs that can be used to identify resource files that are either compiled into the local assembly or compiled into an assembly that is referenced from the local assembly.</span></span>

<a name="Local_Assembly_Resource_File"></a>

### <a name="local-assembly-resource-file"></a><span data-ttu-id="3c845-146">ローカル アセンブリ リソース ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-146">Local Assembly Resource File</span></span>

<span data-ttu-id="3c845-147">ローカルアセンブリ[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]にコンパイルされるリソースファイルのパックは、次の権限とパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c845-147">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a resource file that is compiled into the local assembly uses the following authority and path:</span></span>

- <span data-ttu-id="3c845-148">**オーソリティ**: application:///。</span><span class="sxs-lookup"><span data-stu-id="3c845-148">**Authority**: application:///.</span></span>

- <span data-ttu-id="3c845-149">**パス**:ローカルアセンブリプロジェクトフォルダーのルートに対する相対パスを含む、リソースファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="3c845-149">**Path**: The name of the resource file, including its path, relative to the local assembly project folder root.</span></span>

<span data-ttu-id="3c845-150">次の例は、ローカル[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]アセンブリの[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロジェクトフォルダーのルートにあるリソースファイルのパックを示しています。</span><span class="sxs-lookup"><span data-stu-id="3c845-150">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the local assembly's project folder.</span></span>

`pack://application:,,,/ResourceFile.xaml`

<span data-ttu-id="3c845-151">次の例は、ローカル[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]アセンブリの[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロジェクトフォルダーのサブフォルダーにあるリソースファイルのパックを示しています。</span><span class="sxs-lookup"><span data-stu-id="3c845-151">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the local assembly's project folder.</span></span>

`pack://application:,,,/Subfolder/ResourceFile.xaml`

<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>

### <a name="referenced-assembly-resource-file"></a><span data-ttu-id="3c845-152">参照アセンブリ リソース ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-152">Referenced Assembly Resource File</span></span>

<span data-ttu-id="3c845-153">参照アセンブリ[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]にコンパイルされるリソースファイルのパックは、次の権限とパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c845-153">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a resource file that is compiled into a referenced assembly uses the following authority and path:</span></span>

- <span data-ttu-id="3c845-154">**オーソリティ**: application:///。</span><span class="sxs-lookup"><span data-stu-id="3c845-154">**Authority**: application:///.</span></span>

- <span data-ttu-id="3c845-155">**パス**:参照アセンブリにコンパイルされるリソースファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="3c845-155">**Path**: The name of a resource file that is compiled into a referenced assembly.</span></span> <span data-ttu-id="3c845-156">パスは、次の書式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c845-156">The path must conform to the following format:</span></span>

  <span data-ttu-id="3c845-157">*Assemblyshortname*{ *;バージョン*] { *;PublicKey*]、コンポーネント/*パス*</span><span class="sxs-lookup"><span data-stu-id="3c845-157">*AssemblyShortName*{*;Version*]{*;PublicKey*];component/*Path*</span></span>

  - <span data-ttu-id="3c845-158">**AssemblyShortName**: 参照アセンブリの短い名前。</span><span class="sxs-lookup"><span data-stu-id="3c845-158">**AssemblyShortName**: the short name for the referenced assembly.</span></span>

  - <span data-ttu-id="3c845-159">**;Version** (省略可能): リソース ファイルを含む参照アセンブリのバージョン。</span><span class="sxs-lookup"><span data-stu-id="3c845-159">**;Version** [optional]: the version of the referenced assembly that contains the resource file.</span></span> <span data-ttu-id="3c845-160">これは、同じ短い名前を持つ 2 つ以上の参照アセンブリが読み込まれるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3c845-160">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>

  - <span data-ttu-id="3c845-161">**;PublicKey** (省略可能): 参照アセンブリの署名に使用された公開鍵。</span><span class="sxs-lookup"><span data-stu-id="3c845-161">**;PublicKey** [optional]: the public key that was used to sign the referenced assembly.</span></span> <span data-ttu-id="3c845-162">これは、同じ短い名前を持つ 2 つ以上の参照アセンブリが読み込まれるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="3c845-162">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>

  - <span data-ttu-id="3c845-163">**;component**: 参照されるアセンブリが、ローカル アセンブリから参照されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="3c845-163">**;component**: specifies that the assembly being referred to is referenced from the local assembly.</span></span>

  - <span data-ttu-id="3c845-164">**/Path**: 参照アセンブリのプロジェクト フォルダーのルートに対して相対的なパスを含むリソース ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="3c845-164">**/Path**: the name of the resource file, including its path, relative to the root of the referenced assembly's project folder.</span></span>

<span data-ttu-id="3c845-165">次の例は、参照[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]アセンブリの[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロジェクトフォルダーのルートにあるリソースファイルのパックを示しています。</span><span class="sxs-lookup"><span data-stu-id="3c845-165">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the referenced assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`

<span data-ttu-id="3c845-166">次の例は、参照[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]アセンブリの[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]プロジェクトフォルダーのサブフォルダーにあるリソースファイルのパックを示しています。</span><span class="sxs-lookup"><span data-stu-id="3c845-166">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the referenced assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`

<span data-ttu-id="3c845-167">次の例は、参照[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]され[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ているバージョン固有のアセンブリのプロジェクトフォルダーのルートフォルダーにあるリソースファイルのパックを示しています。</span><span class="sxs-lookup"><span data-stu-id="3c845-167">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root folder of a referenced, version-specific assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`

<span data-ttu-id="3c845-168">参照されるアセンブリ[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]リソースファイルのパック構文は、application:///authority でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3c845-168">Note that the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] syntax for referenced assembly resource files can be used only with the application:/// authority.</span></span> <span data-ttu-id="3c845-169">たとえば、次のはで[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3c845-169">For example, the following is not supported in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span>

`pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`

<a name="Content_File_Pack_URIs"></a>

## <a name="content-file-pack-uris"></a><span data-ttu-id="3c845-170">コンテンツ ファイルのパック URI</span><span class="sxs-lookup"><span data-stu-id="3c845-170">Content File Pack URIs</span></span>

<span data-ttu-id="3c845-171">コンテンツファイル[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]のパックは、次の証明機関とパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c845-171">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a content file uses the following authority and path:</span></span>

- <span data-ttu-id="3c845-172">**オーソリティ**: application:///。</span><span class="sxs-lookup"><span data-stu-id="3c845-172">**Authority**: application:///.</span></span>

- <span data-ttu-id="3c845-173">**パス**:アプリケーションのメインの実行可能アセンブリのファイルシステムの場所を基準としたパスを含む、コンテンツファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="3c845-173">**Path**: The name of the content file, including its path relative to the file system location of the application's main executable assembly.</span></span>

<span data-ttu-id="3c845-174">次の例は、実行[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]可能アセンブリ[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]と同じフォルダーにあるコンテンツファイルのパックを示しています。</span><span class="sxs-lookup"><span data-stu-id="3c845-174">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in the same folder as the executable assembly.</span></span>

`pack://application:,,,/ContentFile.xaml`

<span data-ttu-id="3c845-175">次の例は、アプリケーション[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]の実行[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]可能アセンブリに対して相対的なサブフォルダーにあるコンテンツファイルのパックを示しています。</span><span class="sxs-lookup"><span data-stu-id="3c845-175">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in a subfolder that is relative to the application's executable assembly.</span></span>

`pack://application:,,,/Subfolder/ContentFile.xaml`

> [!NOTE]
> <span data-ttu-id="3c845-176">HTML コンテンツファイルに移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="3c845-176">HTML content files cannot be navigated to.</span></span> <span data-ttu-id="3c845-177">スキーム[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]では、起点サイトにある HTML ファイルへの移動のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3c845-177">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme only supports navigation to HTML files that are located at the site of origin.</span></span>

<a name="The_siteoforigin_____Authority"></a>

## <a name="site-of-origin-pack-uris"></a><span data-ttu-id="3c845-178">起点サイトのパック URI</span><span class="sxs-lookup"><span data-stu-id="3c845-178">Site of Origin Pack URIs</span></span>

<span data-ttu-id="3c845-179">起点サイト[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]ファイルのパックは、次の権限とパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c845-179">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a site of origin file uses the following authority and path:</span></span>

- <span data-ttu-id="3c845-180">**オーソリティ**: siteoforigin:///。</span><span class="sxs-lookup"><span data-stu-id="3c845-180">**Authority**: siteoforigin:///.</span></span>

- <span data-ttu-id="3c845-181">**パス**:起点サイトファイルの名前。実行可能アセンブリが起動された場所を基準とした相対パスを含みます。</span><span class="sxs-lookup"><span data-stu-id="3c845-181">**Path**: The name of the site of origin file, including its path relative to the location from which the executable assembly was launched.</span></span>

<span data-ttu-id="3c845-182">次の例は、実行[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]可能アセンブリ[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]の起動元の場所に格納されている、起点サイトファイルのパックを示しています。</span><span class="sxs-lookup"><span data-stu-id="3c845-182">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in the location from which the executable assembly is launched.</span></span>

`pack://siteoforigin:,,,/SiteOfOriginFile.xaml`

<span data-ttu-id="3c845-183">次の例は、アプリケーション[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]の実行[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]可能アセンブリの起動元の場所を基準としたサブフォルダーに格納されている、起点サイトファイルのパックを示しています。</span><span class="sxs-lookup"><span data-stu-id="3c845-183">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in subfolder that is relative to the location from which the application's executable assembly is launched.</span></span>

`pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`

<a name="Page_Files"></a>

## <a name="page-files"></a><span data-ttu-id="3c845-184">ページ ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-184">Page Files</span></span>

<span data-ttu-id="3c845-185">MSBuild `Page`項目として構成されている XAML ファイルは、リソースファイルと同じ方法でアセンブリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="3c845-185">XAML files that are configured as MSBuild `Page` items are compiled into assemblies in the same way as resource files.</span></span> <span data-ttu-id="3c845-186">そのため、 `Page`リソースファイルのパック uri を使用して MSBuild 項目を識別できます。</span><span class="sxs-lookup"><span data-stu-id="3c845-186">Consequently, MSBuild `Page` items can be identified using pack URIs for resource files.</span></span>

<span data-ttu-id="3c845-187">通常、MSBuild [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] `Page`項目として構成されるファイルの種類は、次のいずれかのルート要素となります。</span><span class="sxs-lookup"><span data-stu-id="3c845-187">The types of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that are commonly configured as MSBuild`Page` items have one of the following as their root element:</span></span>

- <xref:System.Windows.Window?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Page?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>

- <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>

- <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>

- <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>

<a name="Absolute_vs_Relative_Pack_URIs"></a>

## <a name="absolute-vs-relative-pack-uris"></a><span data-ttu-id="3c845-188">絶対および相対パック URI</span><span class="sxs-lookup"><span data-stu-id="3c845-188">Absolute vs. Relative Pack URIs</span></span>

<span data-ttu-id="3c845-189">完全修飾パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]には、スキーム、権限、およびパスが含まれており、これは絶対パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]と見なされます。</span><span class="sxs-lookup"><span data-stu-id="3c845-189">A fully qualified pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] includes the scheme, the authority, and the path, and it is considered an absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span> <span data-ttu-id="3c845-190">開発者のための簡略化[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]として、要素を使用すると、通常は[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]パスのみを含む、相対パックを使用して適切な属性を設定できます。</span><span class="sxs-lookup"><span data-stu-id="3c845-190">As a simplification for developers, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements typically allow you to set appropriate attributes with a relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], which includes only the path.</span></span>

<span data-ttu-id="3c845-191">たとえば、ローカルアセンブリ内のリソースファイル[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]に対する次の絶対パックを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="3c845-191">For example, consider the following absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a resource file in the local assembly.</span></span>

`pack://application:,,,/ResourceFile.xaml`

<span data-ttu-id="3c845-192">このリソースファイル[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]を参照する相対パックは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3c845-192">The relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that refers to this resource file would be the following.</span></span>

`/ResourceFile.xaml`

> [!NOTE]
> <span data-ttu-id="3c845-193">起点サイトファイルはアセンブリに関連付けられていないため、絶対パック[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]でのみ参照できます。</span><span class="sxs-lookup"><span data-stu-id="3c845-193">Because site of origin files are not associated with assemblies, they can only be referred to with absolute pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)].</span></span>

<span data-ttu-id="3c845-194">既定では、相対パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]は、参照を含むマークアップまたはコードの位置を基準として相対的に見なされます。</span><span class="sxs-lookup"><span data-stu-id="3c845-194">By default, a relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is considered relative to the location of the markup or code that contains the reference.</span></span> <span data-ttu-id="3c845-195">ただし、先頭に円記号が使用されている[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]場合、相対パック参照は、アプリケーションのルートを基準として相対的に考慮されます。</span><span class="sxs-lookup"><span data-stu-id="3c845-195">If a leading backslash is used, however, the relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] reference is then considered relative to the root of the application.</span></span> <span data-ttu-id="3c845-196">たとえば、次のようなプロジェクト構造を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="3c845-196">For example, consider the following project structure.</span></span>

`App.xaml`

`Page2.xaml`

`\SubFolder`

`+ Page1.xaml`

`+ Page2.xaml`

<span data-ttu-id="3c845-197">Page1 にルート \SubFolder\Page2.xaml を参照[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]するが含まれている場合、参照は次の相対[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]パックを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3c845-197">If Page1.xaml contains a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that references *Root*\SubFolder\Page2.xaml, the reference can use the following relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>

`Page2.xaml`

<span data-ttu-id="3c845-198">Page1 がルートページを参照[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]するを含んでいる場合、参照は次の相対パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3c845-198">If Page1.xaml contains a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that references *Root*\Page2.xaml, the reference can use the following relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>

`/Page2.xaml`

<a name="Pack_URI_Resolution"></a>

## <a name="pack-uri-resolution"></a><span data-ttu-id="3c845-199">パック URI の解決</span><span class="sxs-lookup"><span data-stu-id="3c845-199">Pack URI Resolution</span></span>

<span data-ttu-id="3c845-200">パック[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]の形式を使用すると、さまざま[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]な種類のファイルのパックを同じように表示できます。</span><span class="sxs-lookup"><span data-stu-id="3c845-200">The format of pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] makes it possible for pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for different types of files to look the same.</span></span> <span data-ttu-id="3c845-201">たとえば、次のような絶対パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="3c845-201">For example, consider the following absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>

`pack://application:,,,/ResourceOrContentFile.xaml`

<span data-ttu-id="3c845-202">この絶対パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]は、ローカルアセンブリまたはコンテンツファイル内のリソースファイルを参照できます。</span><span class="sxs-lookup"><span data-stu-id="3c845-202">This absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] could refer to either a resource file in the local assembly or a content file.</span></span> <span data-ttu-id="3c845-203">これは、次の相対[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="3c845-203">The same is true for the following relative [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>

`/ResourceOrContentFile.xaml`

<span data-ttu-id="3c845-204">では、パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]が参照するファイルの種類を特定するために、次のヒューリスティックを使用して、 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]ローカルアセンブリおよびコンテンツファイル内のリソースファイルが解決[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]されます。</span><span class="sxs-lookup"><span data-stu-id="3c845-204">In order to determine the type of file that a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] refers to, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] resolves [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for resource files in local assemblies and content files by using the following heuristics:</span></span>

1. <span data-ttu-id="3c845-205"><xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> パッケージ[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]に一致する属性のアセンブリメタデータをプローブします。</span><span class="sxs-lookup"><span data-stu-id="3c845-205">Probe the assembly metadata for an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute that matches the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>

2. <span data-ttu-id="3c845-206">属性が見つかった場合、パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]のパスはコンテンツファイルを参照します。 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute></span><span class="sxs-lookup"><span data-stu-id="3c845-206">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is found, the path of the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] refers to a content file.</span></span>

3. <span data-ttu-id="3c845-207"><xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>属性が見つからない場合は、ローカルアセンブリにコンパイルされる set リソースファイルを調べます。</span><span class="sxs-lookup"><span data-stu-id="3c845-207">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is not found, probe the set resource files that are compiled into the local assembly.</span></span>

4. <span data-ttu-id="3c845-208">パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]のパスに一致するリソースファイルが見つかった場合、パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]のパスはリソースファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="3c845-208">If a resource file that matches the path of the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is found, the path of the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] refers to a resource file.</span></span>

5. <span data-ttu-id="3c845-209">リソースが見つからない場合は、内部で作成<xref:System.Uri>されたが無効です。</span><span class="sxs-lookup"><span data-stu-id="3c845-209">If the resource is not found, the internally created <xref:System.Uri> is invalid.</span></span>

[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]<span data-ttu-id="3c845-210">次を参照するに[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]は、解決策が適用されません。</span><span class="sxs-lookup"><span data-stu-id="3c845-210">resolution does not apply for [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that refer to the following:</span></span>

- <span data-ttu-id="3c845-211">参照アセンブリ内のコンテンツファイル: これらのファイルの種類は[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]、ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3c845-211">Content files in referenced assemblies: these file types are not supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span>

- <span data-ttu-id="3c845-212">参照されたアセンブリ内[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]の埋め込みファイル: 参照されるアセンブリの名前`;component`とサフィックスの両方が含まれているため、一意であることを識別します。</span><span class="sxs-lookup"><span data-stu-id="3c845-212">Embedded files in referenced assemblies: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that identify them are unique because they include both the name of the referenced assembly and the `;component` suffix.</span></span>

- <span data-ttu-id="3c845-213">起点サイトファイル: siteoforigin:/// [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]機関を含むパック[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]によって識別できる唯一のファイルであるため、一意であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="3c845-213">Site of origin files: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that identify them are unique because they are the only files that can be identified by pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that contain the siteoforigin:/// authority.</span></span>

<span data-ttu-id="3c845-214">パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]の解決方法の1つとして、コードがリソースファイルとコンテンツファイルの場所から多少独立していることが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="3c845-214">One simplification that pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] resolution allows is for code to be somewhat independent of the locations of resource and content files.</span></span> <span data-ttu-id="3c845-215">たとえば、ローカルアセンブリ内にコンテンツファイルとして再構成されたリソースファイルがある場合、そのパック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]を使用するコードと同じように、リソースのパックは変わりません。</span><span class="sxs-lookup"><span data-stu-id="3c845-215">For example, if you have a resource file in the local assembly that is reconfigured to be a content file, the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for the resource remains the same, as does the code that uses the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>

<a name="Programming_with_Pack_URIs"></a>

## <a name="programming-with-pack-uris"></a><span data-ttu-id="3c845-216">パック URI を使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="3c845-216">Programming with Pack URIs</span></span>

<span data-ttu-id="3c845-217">多く[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]のクラスには、次のような[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]パックで設定できるプロパティが実装されています。</span><span class="sxs-lookup"><span data-stu-id="3c845-217">Many [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] classes implement properties that can be set with pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], including:</span></span>

- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>

<span data-ttu-id="3c845-218">これらのプロパティは、マークアップとコードのどちらからでも設定できます。</span><span class="sxs-lookup"><span data-stu-id="3c845-218">These properties can be set from both markup and code.</span></span> <span data-ttu-id="3c845-219">このセクションでは、両方の基本構造について説明してから、一般的なシナリオの例を示します。</span><span class="sxs-lookup"><span data-stu-id="3c845-219">This section demonstrates the basic constructions for both and then shows examples of common scenarios.</span></span>

<a name="Using_Pack_URIs_in_Markup"></a>

### <a name="using-pack-uris-in-markup"></a><span data-ttu-id="3c845-220">マークアップでのパック URI の使用</span><span class="sxs-lookup"><span data-stu-id="3c845-220">Using Pack URIs in Markup</span></span>

<span data-ttu-id="3c845-221">パックをマークアップで指定するに[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]は、パッケージの属性の要素を設定します。[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c845-221">A pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is specified in markup by setting the element of an attribute with the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span> <span data-ttu-id="3c845-222">例:</span><span class="sxs-lookup"><span data-stu-id="3c845-222">For example:</span></span>

`<element attribute="pack://application:,,,/File.xaml" />`

<span data-ttu-id="3c845-223">表1は、マークアップで[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]指定できるさまざまな絶対パックを示しています。</span><span class="sxs-lookup"><span data-stu-id="3c845-223">Table 1 illustrates the various absolute pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in markup.</span></span>

<span data-ttu-id="3c845-224">表 1:マークアップでの絶対パック Uri</span><span class="sxs-lookup"><span data-stu-id="3c845-224">Table 1: Absolute Pack URIs in Markup</span></span>

|<span data-ttu-id="3c845-225">ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-225">File</span></span>|<span data-ttu-id="3c845-226">絶対パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c845-226">Absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="3c845-227">リソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="3c845-227">Resource file - local assembly</span></span>|`"pack://application:,,,/ResourceFile.xaml"`|
|<span data-ttu-id="3c845-228">サブフォルダー内のリソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="3c845-228">Resource file in subfolder - local assembly</span></span>|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="3c845-229">リソース ファイル - 参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="3c845-229">Resource file - referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|
|<span data-ttu-id="3c845-230">参照アセンブリのサブフォルダー内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-230">Resource file in subfolder of referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="3c845-231">バージョン管理された参照アセンブリ内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-231">Resource file in versioned referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|
|<span data-ttu-id="3c845-232">コンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-232">Content file</span></span>|`"pack://application:,,,/ContentFile.xaml"`|
|<span data-ttu-id="3c845-233">サブフォルダー内のコンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-233">Content file in subfolder</span></span>|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|
|<span data-ttu-id="3c845-234">起点サイト ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-234">Site of origin file</span></span>|`"pack://siteoforigin:,,,/SOOFile.xaml"`|
|<span data-ttu-id="3c845-235">サブフォルダー内の起点サイト ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-235">Site of origin file in subfolder</span></span>|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|

<span data-ttu-id="3c845-236">表2は、マークアップで[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]指定できるさまざまな相対パックを示しています。</span><span class="sxs-lookup"><span data-stu-id="3c845-236">Table 2 illustrates the various relative pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in markup.</span></span>

<span data-ttu-id="3c845-237">表 2:マークアップでの相対パック Uri</span><span class="sxs-lookup"><span data-stu-id="3c845-237">Table 2: Relative Pack URIs in Markup</span></span>

|<span data-ttu-id="3c845-238">ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-238">File</span></span>|<span data-ttu-id="3c845-239">相対パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c845-239">Relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="3c845-240">ローカル アセンブリ内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-240">Resource file in local assembly</span></span>|`"/ResourceFile.xaml"`|
|<span data-ttu-id="3c845-241">ローカル アセンブリのサブフォルダー内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-241">Resource file in subfolder of local assembly</span></span>|`"/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="3c845-242">参照アセンブリ内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-242">Resource file in referenced assembly</span></span>|`"/ReferencedAssembly;component/ResourceFile.xaml"`|
|<span data-ttu-id="3c845-243">参照アセンブリのサブフォルダー内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-243">Resource file in subfolder of referenced assembly</span></span>|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="3c845-244">コンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-244">Content file</span></span>|`"/ContentFile.xaml"`|
|<span data-ttu-id="3c845-245">サブフォルダー内のコンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-245">Content file in subfolder</span></span>|`"/Subfolder/ContentFile.xaml"`|

<a name="Using_Pack_URIs_in_Code"></a>

### <a name="using-pack-uris-in-code"></a><span data-ttu-id="3c845-246">コードでのパック URI の使用</span><span class="sxs-lookup"><span data-stu-id="3c845-246">Using Pack URIs in Code</span></span>

<span data-ttu-id="3c845-247">コードでパック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]を指定するには、 <xref:System.Uri>クラスをインスタンス化し[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 、そのパックをパラメーターとしてコンストラクターに渡します。</span><span class="sxs-lookup"><span data-stu-id="3c845-247">You specify a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] in code by instantiating the <xref:System.Uri> class and passing the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] as a parameter to the constructor.</span></span> <span data-ttu-id="3c845-248">このコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3c845-248">This is demonstrated in the following example.</span></span>

```csharp
Uri uri = new Uri("pack://application:,,,/File.xaml");
```

<span data-ttu-id="3c845-249">既定では、 <xref:System.Uri>クラスはパック[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]を絶対値と見なします。</span><span class="sxs-lookup"><span data-stu-id="3c845-249">By default, the <xref:System.Uri> class considers pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] to be absolute.</span></span> <span data-ttu-id="3c845-250">その結果、 <xref:System.Uri>クラスのインスタンスが相対パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]を使用して作成されると、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="3c845-250">Consequently, an exception is raised when an instance of the <xref:System.Uri> class is created with a relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>

```csharp
Uri uri = new Uri("/File.xaml");
```

<span data-ttu-id="3c845-251">幸いにも<xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> 、 <xref:System.Uri>クラスコンストラクターのオーバーロードは、型<xref:System.UriKind>のパラメーターを受け取り、パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]が絶対か相対かを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3c845-251">Fortunately, the <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> overload of the <xref:System.Uri> class constructor accepts a parameter of type <xref:System.UriKind> to allow you to specify whether a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is either absolute or relative.</span></span>

```csharp
// Absolute URI (default)
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);
// Relative URI
Uri relativeUri = new Uri("/File.xaml",
                        UriKind.Relative);
```

<span data-ttu-id="3c845-252">指定された<xref:System.UriKind.Absolute>パック<xref:System.UriKind.Relative> [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]がいずれかであることがわかっている場合にのみ、またはを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c845-252">You should specify only <xref:System.UriKind.Absolute> or <xref:System.UriKind.Relative> when you are certain that the provided pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is one or the other.</span></span> <span data-ttu-id="3c845-253">実行時にユーザーがパック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]を入力したときなど、使用されているパックの種類がわからない場合<xref:System.UriKind.RelativeOrAbsolute>は、代わりにを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c845-253">If you don't know the type of pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that is used, such as when a user enters a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] at run time, use <xref:System.UriKind.RelativeOrAbsolute> instead.</span></span>

```csharp
// Relative or Absolute URI provided by user via a text box
TextBox userProvidedUriTextBox = new TextBox();
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);
```

<span data-ttu-id="3c845-254">表3は、を使用[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] <xref:System.Uri?displayProperty=nameWithType>してコードで指定できるさまざまな相対パックを示しています。</span><span class="sxs-lookup"><span data-stu-id="3c845-254">Table 3 illustrates the various relative pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in code by using <xref:System.Uri?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="3c845-255">表 3:コード内の絶対パック Uri</span><span class="sxs-lookup"><span data-stu-id="3c845-255">Table 3: Absolute Pack URIs in Code</span></span>

|<span data-ttu-id="3c845-256">ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-256">File</span></span>|<span data-ttu-id="3c845-257">絶対パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c845-257">Absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="3c845-258">リソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="3c845-258">Resource file - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="3c845-259">サブフォルダー内のリソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="3c845-259">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="3c845-260">リソース ファイル - 参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="3c845-260">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="3c845-261">参照アセンブリのサブフォルダー内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-261">Resource file in subfolder of referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="3c845-262">バージョン管理された参照アセンブリ内のリソース ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-262">Resource file in versioned referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="3c845-263">コンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-263">Content file</span></span>|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="3c845-264">サブフォルダー内のコンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-264">Content file in subfolder</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="3c845-265">起点サイト ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-265">Site of origin file</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="3c845-266">サブフォルダー内の起点サイト ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-266">Site of origin file in subfolder</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|

<span data-ttu-id="3c845-267">表4は、を使用し[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]てコードで指定できるさまざまな<xref:System.Uri?displayProperty=nameWithType>相対パックを示しています。</span><span class="sxs-lookup"><span data-stu-id="3c845-267">Table 4 illustrates the various relative pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in code using <xref:System.Uri?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="3c845-268">表 4:コード内の相対パック Uri</span><span class="sxs-lookup"><span data-stu-id="3c845-268">Table 4: Relative Pack URIs in Code</span></span>

|<span data-ttu-id="3c845-269">ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-269">File</span></span>|<span data-ttu-id="3c845-270">相対パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c845-270">Relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="3c845-271">リソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="3c845-271">Resource file - local assembly</span></span>|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="3c845-272">サブフォルダー内のリソース ファイル - ローカル アセンブリ</span><span class="sxs-lookup"><span data-stu-id="3c845-272">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="3c845-273">リソース ファイル - 参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="3c845-273">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="3c845-274">サブフォルダー内のリソース ファイル - 参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="3c845-274">Resource file in subfolder - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="3c845-275">コンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-275">Content file</span></span>|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="3c845-276">サブフォルダー内のコンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-276">Content file in subfolder</span></span>|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|

<a name="Common_Pack_URI_Scenarios"></a>

### <a name="common-pack-uri-scenarios"></a><span data-ttu-id="3c845-277">一般的なパック URI のシナリオ</span><span class="sxs-lookup"><span data-stu-id="3c845-277">Common Pack URI Scenarios</span></span>

<span data-ttu-id="3c845-278">前のセクションでは、リソース、コンテンツ[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 、および起点サイトファイルを識別するためにパックを構築する方法について説明しました。</span><span class="sxs-lookup"><span data-stu-id="3c845-278">The preceding sections have discussed how to construct pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] to identify resource, content, and site of origin files.</span></span> <span data-ttu-id="3c845-279">で[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]は、これらの構造はさまざまな方法で使用されます。次のセクションでは、いくつかの一般的な使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c845-279">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], these constructions are used in a variety of ways, and the following sections cover several common usages.</span></span>

<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>

#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a><span data-ttu-id="3c845-280">アプリケーションの起動時に表示する UI の指定</span><span class="sxs-lookup"><span data-stu-id="3c845-280">Specifying the UI to Show When an Application Starts</span></span>

<span data-ttu-id="3c845-281"><xref:System.Windows.Application.StartupUri%2A>アプリケーションが起動[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]されたときに表示する最初のを指定します。 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c845-281"><xref:System.Windows.Application.StartupUri%2A> specifies the first [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to show when a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application is launched.</span></span> <span data-ttu-id="3c845-282">スタンドアロンアプリケーションの場合[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]は、次の例に示すように、をウィンドウにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3c845-282">For standalone applications, the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] can be a window, as shown in the following example.</span></span>

[!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]

<span data-ttu-id="3c845-283">スタンドアロンアプリケーション[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]とでは、次の例に示すように、初期 UI としてページを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c845-283">Standalone applications and [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] can also specify a page as the initial UI, as shown in the following example.</span></span>

[!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]

<span data-ttu-id="3c845-284">アプリケーションがスタンドアロンアプリケーションであり、で<xref:System.Windows.Application.StartupUri%2A>ページが指定されている場合、 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]はを開き<xref:System.Windows.Navigation.NavigationWindow> 、ページをホストします。</span><span class="sxs-lookup"><span data-stu-id="3c845-284">If the application is a standalone application and a page is specified with <xref:System.Windows.Application.StartupUri%2A>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] opens a <xref:System.Windows.Navigation.NavigationWindow> to host the page.</span></span> <span data-ttu-id="3c845-285">の[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]場合、ページはホストブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c845-285">For [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], the page is shown in the host browser.</span></span>

<a name="Navigating_to_a_Page"></a>

#### <a name="navigating-to-a-page"></a><span data-ttu-id="3c845-286">ページへのナビゲート</span><span class="sxs-lookup"><span data-stu-id="3c845-286">Navigating to a Page</span></span>

<span data-ttu-id="3c845-287">次の例は、ページにナビゲートする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3c845-287">The following example shows how to navigate to a page.</span></span>

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

<span data-ttu-id="3c845-288">移動[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]するさまざまな方法の詳細については、「[ナビゲーションの概要](navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c845-288">For more information on the various ways to navigate in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], see [Navigation Overview](navigation-overview.md).</span></span>

<a name="Specifying_a_Window_Icon"></a>

#### <a name="specifying-a-window-icon"></a><span data-ttu-id="3c845-289">ウィンドウ アイコンの指定</span><span class="sxs-lookup"><span data-stu-id="3c845-289">Specifying a Window Icon</span></span>

<span data-ttu-id="3c845-290">次の例は、URI を使用してウィンドウのアイコンを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3c845-290">The following example shows how to use a URI to specify a window's icon.</span></span>

[!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]

<span data-ttu-id="3c845-291">詳細については、「 <xref:System.Windows.Window.Icon%2A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c845-291">For more information, see <xref:System.Windows.Window.Icon%2A>.</span></span>

<a name="Loading_Image__Audio__and_Video_Files"></a>

#### <a name="loading-image-audio-and-video-files"></a><span data-ttu-id="3c845-292">イメージ ファイル、オーディオ ファイル、およびビデオ ファイルの読み込み</span><span class="sxs-lookup"><span data-stu-id="3c845-292">Loading Image, Audio, and Video Files</span></span>

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="3c845-293">では、次の例に示すように、アプリケーションでさまざまな種類のメディアを使用し[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]て、そのすべてを特定し、パックで読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="3c845-293">allows applications to use a wide variety of media types, all of which can be identified and loaded with pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], as shown in the following examples.</span></span>

[!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]

[!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]

[!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]

<span data-ttu-id="3c845-294">メディアコンテンツの操作の詳細については、「[グラフィックスとマルチメディア](../graphics-multimedia/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c845-294">For more information on working with media content, see [Graphics and Multimedia](../graphics-multimedia/index.md).</span></span>

<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>

#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a><span data-ttu-id="3c845-295">起点サイトからのリソース ディクショナリの読み込み</span><span class="sxs-lookup"><span data-stu-id="3c845-295">Loading a Resource Dictionary from the Site of Origin</span></span>

<span data-ttu-id="3c845-296">リソースディクショナリ (<xref:System.Windows.ResourceDictionary>) は、アプリケーションテーマをサポートするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="3c845-296">Resource dictionaries (<xref:System.Windows.ResourceDictionary>) can be used to support application themes.</span></span> <span data-ttu-id="3c845-297">テーマを作成し、管理する方法の 1 つは、複数のテーマをリソース ディクショナリとして作成して、アプリケーションの起点サイトに配置することです。</span><span class="sxs-lookup"><span data-stu-id="3c845-297">One way to create and manage themes is to create multiple themes as resource dictionaries that are located at an application's site of origin.</span></span> <span data-ttu-id="3c845-298">これにより、アプリケーションを再コンパイルして再配置しなくても、テーマの追加と交信が可能です。</span><span class="sxs-lookup"><span data-stu-id="3c845-298">This allows themes to be added and updated without recompiling and redeploying an application.</span></span> <span data-ttu-id="3c845-299">これらのリソースディクショナリは、次の例に[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]示すように、pack を使用して識別および読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="3c845-299">These resource dictionaries can be identified and loaded using pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], which is shown in the following example.</span></span>

[!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]

<span data-ttu-id="3c845-300">のテーマ[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]の概要については、「[スタイルとテンプレート](../controls/styling-and-templating.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c845-300">For an overview of themes in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], see [Styling and Templating](../controls/styling-and-templating.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3c845-301">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c845-301">See also</span></span>

- [<span data-ttu-id="3c845-302">WPF アプリケーションのリソース ファイル、コンテンツ ファイル、およびデータ ファイル</span><span class="sxs-lookup"><span data-stu-id="3c845-302">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
