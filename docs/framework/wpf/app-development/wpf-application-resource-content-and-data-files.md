---
title: WPF アプリケーションのリソース ファイル、コンテンツ ファイル、およびデータ ファイル
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF application [WPF], files
- loose resources [WPF]
- content files [WPF]
- Site of Origin files [WPF]
- resource files [WPF]
- remote files [WPF]
- embedded resources [WPF]
- files [WPF]
- referencing application files [WPF]
- application development [WPF], files
- application management [WPF]
ms.assetid: 7ad2943b-3961-41d3-8fc6-1582d43f5d99
ms.openlocfilehash: 2bf815a5b34726b8316eea53786811abec00f5bb
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581727"
---
# <a name="wpf-application-resource-content-and-data-files"></a><span data-ttu-id="88197-102">WPF アプリケーションのリソース ファイル、コンテンツ ファイル、およびデータ ファイル</span><span class="sxs-lookup"><span data-stu-id="88197-102">WPF Application Resource, Content, and Data Files</span></span>
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] <span data-ttu-id="88197-103">アプリケーションは、多くの場合、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]、イメージ、ビデオ、オーディオなど、実行可能ではないデータを含むファイルに依存します。</span><span class="sxs-lookup"><span data-stu-id="88197-103">applications often depend on files that contain non-executable data, such as [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], images, video, and audio.</span></span> <span data-ttu-id="88197-104">Windows Presentation Foundation (WPF) では、これらの種類のデータファイル (アプリケーションデータファイルと呼ばれます) を構成、識別、および使用するための特別なサポートを提供しています。</span><span class="sxs-lookup"><span data-stu-id="88197-104">Windows Presentation Foundation (WPF) offers special support for configuring, identifying, and using these types of data files, which are called application data files.</span></span> <span data-ttu-id="88197-105">このサポートの中心となるのは、次のような特定のアプリケーション データ ファイルの種類のセットです。</span><span class="sxs-lookup"><span data-stu-id="88197-105">This support revolves around a specific set of application data file types, including:</span></span>  
  
- <span data-ttu-id="88197-106">**リソースファイル**: 実行可能ファイルまたはライブラリ [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] アセンブリのいずれかにコンパイルされるデータファイル。</span><span class="sxs-lookup"><span data-stu-id="88197-106">**Resource Files**: Data files that are compiled into either an executable or library [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] assembly.</span></span>  
  
- <span data-ttu-id="88197-107">**コンテンツファイル**: 実行可能ファイル [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] アセンブリに明示的に関連付けられているスタンドアロンデータファイル。</span><span class="sxs-lookup"><span data-stu-id="88197-107">**Content Files**: Standalone data files that have an explicit association with an executable [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] assembly.</span></span>  
  
- <span data-ttu-id="88197-108">**起点サイトファイル**: 実行可能ファイル [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] アセンブリに関連付けられていないスタンドアロンデータファイル。</span><span class="sxs-lookup"><span data-stu-id="88197-108">**Site of Origin Files**: Standalone data files that have no association with an executable [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] assembly.</span></span>  
  
 <span data-ttu-id="88197-109">これらの 3 種類のファイルの重要な違いは、リソース ファイルとコンテンツ ファイルはビルド時に認識されるという点です。アセンブリは、これらを明確に認識します。</span><span class="sxs-lookup"><span data-stu-id="88197-109">One important distinction to make between these three types of files is that resource files and content files are known at build time; an assembly has explicit knowledge of them.</span></span> <span data-ttu-id="88197-110">ただし、起点サイトファイルの場合、アセンブリについての情報がないか、またはパッケージ URI (uniform resource identifier) 参照によって暗黙的に認識されている可能性があります。後者の場合、参照されている起点サイトファイルが実際に存在する保証はありません。</span><span class="sxs-lookup"><span data-stu-id="88197-110">For site of origin files, however, an assembly may have no knowledge of them at all, or implicit knowledge through a pack uniform resource identifier (URI) reference; the case of the latter, there is no guarantee that the referenced site of origin file actually exists.</span></span>  
  
 <span data-ttu-id="88197-111">アプリケーションデータファイルを参照するために、Windows Presentation Foundation (WPF) は、パッケージ uri (uniform resource identifier) スキームを使用します。これについては、「 [wpf のパック uri](pack-uris-in-wpf.md)」で詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="88197-111">To reference application data files, Windows Presentation Foundation (WPF) uses the Pack uniform resource identifier (URI) Scheme, which is described in detail in [Pack URIs in WPF](pack-uris-in-wpf.md)).</span></span>  
  
 <span data-ttu-id="88197-112">このトピックでは、アプリケーション データ ファイルを構成および使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="88197-112">This topic describes how to configure and use application data files.</span></span>  

<a name="Resource_Files"></a>   
## <a name="resource-files"></a><span data-ttu-id="88197-113">リソース ファイル (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="88197-113">Resource Files</span></span>  
 <span data-ttu-id="88197-114">アプリケーション データ ファイルを常にアプリケーションで使用可能にするには、コンパイルしてアプリケーションのメイン実行可能アセンブリまたはその参照アセンブリの 1 つに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="88197-114">If an application data file must always be available to an application, the only way to guarantee availability is to compile it into an application's main executable assembly or one of its referenced assemblies.</span></span> <span data-ttu-id="88197-115">この種類のアプリケーションデータファイルは、*リソースファイル*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="88197-115">This type of application data file is known as a *resource file*.</span></span>  
  
 <span data-ttu-id="88197-116">リソース ファイルは、次のときに使用します。</span><span class="sxs-lookup"><span data-stu-id="88197-116">You should use resource files when:</span></span>  
  
- <span data-ttu-id="88197-117">コンパイルしてアセンブリに組み込んだ後に、リソース ファイルのコンテンツを更新する必要がない。</span><span class="sxs-lookup"><span data-stu-id="88197-117">You don't need to update the resource file's content after it is compiled into an assembly.</span></span>  
  
- <span data-ttu-id="88197-118">ファイルの依存関係の数を減らして、アプリケーション配布の複雑さを軽減する必要がある。</span><span class="sxs-lookup"><span data-stu-id="88197-118">You want to simplify application distribution complexity by reducing the number of file dependencies.</span></span>  
  
- <span data-ttu-id="88197-119">アプリケーションデータファイルはローカライズ可能である必要があります (「 [WPF のグローバリゼーションとローカライズの概要](../advanced/wpf-globalization-and-localization-overview.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="88197-119">Your application data file needs to be localizable (see [WPF Globalization and Localization Overview](../advanced/wpf-globalization-and-localization-overview.md)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="88197-120">このセクションで説明するリソースファイルは、「 [XAML リソース](../advanced/xaml-resources.md)」で説明されているリソースファイルとは異なり、「[アプリケーションリソースの管理 (.net)](/visualstudio/ide/managing-application-resources-dotnet)」で説明されている埋め込みリソースまたはリンクされたリソースとは異なります。</span><span class="sxs-lookup"><span data-stu-id="88197-120">The resource files described in this section are different than the resource files described in [XAML Resources](../advanced/xaml-resources.md) and different than the embedded or linked resources described in [Manage Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
### <a name="configuring-resource-files"></a><span data-ttu-id="88197-121">リソース ファイルの構成</span><span class="sxs-lookup"><span data-stu-id="88197-121">Configuring Resource Files</span></span>  
 <span data-ttu-id="88197-122">@No__t_0 では、リソースファイルは、`Resource` 項目として Microsoft build engine (MSBuild) プロジェクトに含まれるファイルです。</span><span class="sxs-lookup"><span data-stu-id="88197-122">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], a resource file is a file that is included in an Microsoft build engine (MSBuild) project as a `Resource` item.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="88197-123">@No__t_0 では、プロジェクトにファイルを追加し、その `Build Action` を `Resource` に設定することによって、リソースファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="88197-123">In [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], you create a resource file by adding a file to a project and setting its `Build Action` to `Resource`.</span></span>  
  
 <span data-ttu-id="88197-124">プロジェクトがビルドされると、MSBuild はリソースをコンパイルしてアセンブリにします。</span><span class="sxs-lookup"><span data-stu-id="88197-124">When the project is built, MSBuild compiles the resource into the assembly.</span></span>  
  
### <a name="using-resource-files"></a><span data-ttu-id="88197-125">リソース ファイルの使用</span><span class="sxs-lookup"><span data-stu-id="88197-125">Using Resource Files</span></span>  
 <span data-ttu-id="88197-126">リソースファイルを読み込むには、<xref:System.Windows.Application> クラスの <xref:System.Windows.Application.GetResourceStream%2A> メソッドを呼び出して、目的のリソースファイルを識別するパック URI を渡します。</span><span class="sxs-lookup"><span data-stu-id="88197-126">To load a resource file, you can call the <xref:System.Windows.Application.GetResourceStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired resource file.</span></span> <span data-ttu-id="88197-127"><xref:System.Windows.Application.GetResourceStream%2A> は <xref:System.Windows.Resources.StreamResourceInfo> オブジェクトを返します。このオブジェクトは、リソースファイルを <xref:System.IO.Stream> として公開し、そのコンテンツの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="88197-127"><xref:System.Windows.Application.GetResourceStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the resource file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="88197-128">例として、次のコードは、<xref:System.Windows.Application.GetResourceStream%2A> を使用して <xref:System.Windows.Controls.Page> リソースファイルを読み込み、<xref:System.Windows.Controls.Frame> (`pageFrame`) のコンテンツとして設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="88197-128">As an example, the following code shows how to use <xref:System.Windows.Application.GetResourceStream%2A> to load a <xref:System.Windows.Controls.Page> resource file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`):</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 <span data-ttu-id="88197-129">@No__t_0 を呼び出すと <xref:System.IO.Stream> にアクセスできますが、それを設定するプロパティの型に変換する追加作業を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88197-129">While calling <xref:System.Windows.Application.GetResourceStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="88197-130">代わりに、コードを使用して、リソースファイルを型のプロパティに直接読み込むことによって、<xref:System.IO.Stream> を開いて変換できるように [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] できます。</span><span class="sxs-lookup"><span data-stu-id="88197-130">Instead, you can let [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="88197-131">次の例は、コードを使用して <xref:System.Windows.Controls.Frame> (`pageFrame`) に <xref:System.Windows.Controls.Page> を直接読み込む方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="88197-131">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 <span data-ttu-id="88197-132">次の例は、上の例と同じ意味のマークアップです。</span><span class="sxs-lookup"><span data-stu-id="88197-132">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a><span data-ttu-id="88197-133">リソース ファイルとしてのアプリケーション コード ファイル</span><span class="sxs-lookup"><span data-stu-id="88197-133">Application Code Files as Resource Files</span></span>  
 <span data-ttu-id="88197-134">Windows、ページ、フロードキュメント、リソースディクショナリなどのパック Uri を使用して、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] アプリケーションコードファイルの特殊なセットを参照できます。</span><span class="sxs-lookup"><span data-stu-id="88197-134">A special set of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application code files can be referenced using pack URIs, including windows, pages, flow documents, and resource dictionaries.</span></span> <span data-ttu-id="88197-135">たとえば、アプリケーションの起動時に読み込むウィンドウまたはページを参照するパック URI を使用して、<xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> プロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="88197-135">For example, you can set the <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> property with a pack URI that references the window or page that you would like to load when an application starts.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 <span data-ttu-id="88197-136">これは、XAML ファイルが MSBuild プロジェクトに `Page` 項目として含まれている場合に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="88197-136">You can do this when a XAML file is included in an MSBuild project as a `Page` item.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Page Include="MainWindow.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="88197-137">@No__t_0 では、プロジェクトに新しい <xref:System.Windows.Window>、<xref:System.Windows.Navigation.NavigationWindow>、<xref:System.Windows.Controls.Page>、<xref:System.Windows.Documents.FlowDocument>、または <xref:System.Windows.ResourceDictionary> を追加すると、マークアップファイルの `Build Action` が既定で `Page` されます。</span><span class="sxs-lookup"><span data-stu-id="88197-137">In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], you add a new <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>, or <xref:System.Windows.ResourceDictionary> to a project, the `Build Action` for the markup file will default to `Page`.</span></span>  
  
 <span data-ttu-id="88197-138">@No__t_0 項目を含むプロジェクトがコンパイルされると、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 項目はバイナリ形式に変換され、関連付けられたアセンブリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="88197-138">When a project with `Page` items is compiled, the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] items are converted to binary format and compiled into the associated assembly.</span></span> <span data-ttu-id="88197-139">したがって、これらのファイルは、通常のリソース ファイルと同様に使用できます。</span><span class="sxs-lookup"><span data-stu-id="88197-139">Consequently, these files can be used in the same way as typical resource files.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="88197-140">@No__t_0 ファイルが `Resource` の項目として構成されていて、分離コードファイルがない場合、生の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] は、生の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] のバイナリバージョンではなく、アセンブリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="88197-140">If a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is configured as a `Resource` item, and does not have a code-behind file, the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is compiled into an assembly rather than a binary version of the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a><span data-ttu-id="88197-141">コンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="88197-141">Content Files</span></span>  
 <span data-ttu-id="88197-142">*コンテンツファイル*は、実行可能アセンブリと共に、圧縮されていないファイルとして配布されます。</span><span class="sxs-lookup"><span data-stu-id="88197-142">A *content file* is distributed as a loose file alongside an executable assembly.</span></span> <span data-ttu-id="88197-143">コンテンツ ファイルはコンパイルされてアセンブリに組み込まれるのではありませんが、アセンブリのコンパイル時に、各コンテンツ ファイルとの関連付けを確立するメタデータが使用されます。</span><span class="sxs-lookup"><span data-stu-id="88197-143">Although they are not compiled into an assembly, assemblies are compiled with metadata that establishes an association with each content file.</span></span>  
  
 <span data-ttu-id="88197-144">アプリケーションに必要な特定のアプリケーション データ ファイルのセットが更新されても、そのファイルを使用するアセンブリを再コンパイルせずに、コンテンツ ファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88197-144">You should use content files when your application requires a specific set of application data files that you want to be able to update without recompiling the assembly that consumes them.</span></span>  
  
### <a name="configuring-content-files"></a><span data-ttu-id="88197-145">コンテンツ ファイルの構成</span><span class="sxs-lookup"><span data-stu-id="88197-145">Configuring Content Files</span></span>  
 <span data-ttu-id="88197-146">コンテンツファイルをプロジェクトに追加するには、アプリケーションデータファイルが `Content` 項目として含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="88197-146">To add a content file to a project, an application data file must be included as a `Content` item.</span></span> <span data-ttu-id="88197-147">さらに、コンテンツファイルはアセンブリに直接コンパイルされないため、MSBuild `CopyToOutputDirectory` メタデータ要素を設定して、ビルドされたアセンブリに対して相対的な場所にコンテンツファイルをコピーするように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88197-147">Furthermore, because a content file is not compiled directly into the assembly, you need to set the MSBuild `CopyToOutputDirectory` metadata element to specify that the content file is copied to a location that is relative to the built assembly.</span></span> <span data-ttu-id="88197-148">プロジェクトをビルドするたびにリソースをビルド出力フォルダーにコピーする場合は、`CopyToOutputDirectory` メタデータ要素に `Always` 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="88197-148">If you want the resource to be copied to the build output folder every time a project is built, you set the `CopyToOutputDirectory` metadata element with the `Always` value.</span></span> <span data-ttu-id="88197-149">それ以外の場合は、`PreserveNewest` 値を使用して、リソースの最新バージョンのみがビルド出力フォルダーにコピーされるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="88197-149">Otherwise, you can ensure that only the newest version of the resource is copied to the build output folder by using the `PreserveNewest` value.</span></span>  
  
 <span data-ttu-id="88197-150">次に示すファイルは、新しいバージョンのリソースがプロジェクトに追加された場合にのみビルド出力フォルダーにコピーされるコンテンツ ファイルとして構成されています。</span><span class="sxs-lookup"><span data-stu-id="88197-150">The following shows a file that is configured as a content file which is copied to the build output folder only when a new version of the resource is added to the project.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Content Include="ContentFile.xaml">  
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
    </Content>  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="88197-151">@No__t_0 では、ファイルをプロジェクトに追加し、その `Build Action` を `Content` に設定し、その `Copy to Output Directory` を `Copy always` (`Always` と同じ) および `Copy if newer` (`PreserveNewest` と同じ) に設定して、コンテンツファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="88197-151">In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], you create a content file by adding a file to a project and setting its `Build Action` to `Content`, and set its `Copy to Output Directory` to `Copy always` (same as `Always`) and `Copy if newer` (same as `PreserveNewest`).</span></span>  
  
 <span data-ttu-id="88197-152">プロジェクトがビルドされると、<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 属性が、各コンテンツファイルのアセンブリのメタデータにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="88197-152">When the project is built, an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is compiled into the metadata of the assembly for each content file.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 <span data-ttu-id="88197-153">@No__t_0 の値は、プロジェクト内のその位置に対するコンテンツファイルへの相対パスを意味します。</span><span class="sxs-lookup"><span data-stu-id="88197-153">The value of the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> implies the path to the content file relative to its position in the project.</span></span> <span data-ttu-id="88197-154">たとえば、コンテンツファイルがプロジェクトサブフォルダー内にある場合、追加のパス情報が <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> の値に組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="88197-154">For example, if a content file was located in a project subfolder, the additional path information would be incorporated into the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <span data-ttu-id="88197-155">@No__t_0 値は、ビルド出力フォルダー内のコンテンツファイルへのパスの値でもあります。</span><span class="sxs-lookup"><span data-stu-id="88197-155">The <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value is also the value of the path to the content file in the build output folder.</span></span>  
  
### <a name="using-content-files"></a><span data-ttu-id="88197-156">コンテンツ ファイルの使用</span><span class="sxs-lookup"><span data-stu-id="88197-156">Using Content Files</span></span>  
 <span data-ttu-id="88197-157">コンテンツファイルを読み込むには、<xref:System.Windows.Application> クラスの <xref:System.Windows.Application.GetContentStream%2A> メソッドを呼び出して、目的のコンテンツファイルを識別するパック URI を渡します。</span><span class="sxs-lookup"><span data-stu-id="88197-157">To load a content file, you can call the <xref:System.Windows.Application.GetContentStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired content file.</span></span> <span data-ttu-id="88197-158"><xref:System.Windows.Application.GetContentStream%2A> は <xref:System.Windows.Resources.StreamResourceInfo> オブジェクトを返します。これにより、コンテンツファイルが <xref:System.IO.Stream> として公開され、コンテンツの種類が記述されます。</span><span class="sxs-lookup"><span data-stu-id="88197-158"><xref:System.Windows.Application.GetContentStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the content file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="88197-159">例として、次のコードは、<xref:System.Windows.Application.GetContentStream%2A> を使用して <xref:System.Windows.Controls.Page> コンテンツファイルを読み込み、<xref:System.Windows.Controls.Frame> (`pageFrame`) のコンテンツとして設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="88197-159">As an example, the following code shows how to use <xref:System.Windows.Application.GetContentStream%2A> to load a <xref:System.Windows.Controls.Page> content file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 <span data-ttu-id="88197-160">@No__t_0 を呼び出すと <xref:System.IO.Stream> にアクセスできますが、それを設定するプロパティの型に変換する追加作業を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88197-160">While calling <xref:System.Windows.Application.GetContentStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="88197-161">代わりに、コードを使用して、リソースファイルを型のプロパティに直接読み込むことによって、<xref:System.IO.Stream> を開いて変換できるように [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] できます。</span><span class="sxs-lookup"><span data-stu-id="88197-161">Instead, you can let [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="88197-162">次の例は、コードを使用して <xref:System.Windows.Controls.Frame> (`pageFrame`) に <xref:System.Windows.Controls.Page> を直接読み込む方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="88197-162">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 <span data-ttu-id="88197-163">次の例は、上の例と同じ意味のマークアップです。</span><span class="sxs-lookup"><span data-stu-id="88197-163">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a><span data-ttu-id="88197-164">起点サイト ファイル</span><span class="sxs-lookup"><span data-stu-id="88197-164">Site of Origin Files</span></span>  
 <span data-ttu-id="88197-165">リソースファイルには、<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> による定義に従って、配布されるアセンブリと共に明示的な関係があります。</span><span class="sxs-lookup"><span data-stu-id="88197-165">Resource files have an explicit relationship with the assemblies that they are distributed alongside, as defined by the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.</span></span> <span data-ttu-id="88197-166">ただし、アセンブリとアプリケーション データ ファイル間に暗黙的な関係を持たせる、または関係を持たせない場合があります。たとえば次のような場合です。</span><span class="sxs-lookup"><span data-stu-id="88197-166">But, there are times when you may want to establish either an implicit or non-existent relationship between an assembly and an application data file, including when:</span></span>  
  
- <span data-ttu-id="88197-167">コンパイル時にファイルが存在しません。</span><span class="sxs-lookup"><span data-stu-id="88197-167">A file doesn't exist at compile time.</span></span>  
  
- <span data-ttu-id="88197-168">アセンブリが必要とするファイルが、実行時までわからない場合。</span><span class="sxs-lookup"><span data-stu-id="88197-168">You don't know what files your assembly will require until run time.</span></span>  
  
- <span data-ttu-id="88197-169">関連付けられているアセンブリを再コンパイルせずにファイルを更新可能にする場合。</span><span class="sxs-lookup"><span data-stu-id="88197-169">You want to be able to update files without recompiling the assembly that they are associated with.</span></span>  
  
- <span data-ttu-id="88197-170">オーディオやビデオなど大容量のデータ ファイルを使用するアプリケーションで、ユーザーが選択した場合にのみファイルをダウンロードする場合。</span><span class="sxs-lookup"><span data-stu-id="88197-170">Your application uses large data files, such as audio and video, and you only want users to download them if they choose to.</span></span>  
  
 <span data-ttu-id="88197-171">これらの種類のファイルは、file:///スキームや http://スキームなどの従来の URI スキームを使用して読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="88197-171">It is possible to load these types of files by using traditional URI schemes, such as the file:/// and http:// schemes.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 <span data-ttu-id="88197-172">ただし、file:/// スキームや http:// スキームを使用する場合は、アプリケーションに完全信頼が必要です。</span><span class="sxs-lookup"><span data-stu-id="88197-172">However, the file:/// and http:// schemes require your application to have full trust.</span></span> <span data-ttu-id="88197-173">アプリケーションがインターネットまたはイントラネットから起動された [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] であり、その場所から起動されたアプリケーションに対して許可されるアクセス許可のセットだけを要求する場合、圧縮されていないファイルはアプリケーションの元のサイトからのみ読み込むことができます (起動場所)。</span><span class="sxs-lookup"><span data-stu-id="88197-173">If your application is a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that was launched from the Internet or intranet, and it requests only the set of permissions that are allowed for applications launched from those locations, loose files can only be loaded from the application's site of origin (launch location).</span></span> <span data-ttu-id="88197-174">このようなファイルは、*起点サイト*ファイルと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="88197-174">Such files are known as *site of origin* files.</span></span>  
  
 <span data-ttu-id="88197-175">起点サイト ファイルは部分信頼アプリケーションの唯一のオプションですが、部分信頼アプリケーション以外でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="88197-175">Site of origin files are the only option for partial trust applications, although are not limited to partial trust applications.</span></span> <span data-ttu-id="88197-176">完全信頼アプリケーションでも、読み込むアプリケーション データ ファイルがビルド時点では不明な場合があります。完全信頼アプリケーションでは file:/// を使用できますが、アプリケーション データ ファイルがアプリケーション アセンブリと同じフォルダーにインストールされることも、サブフォルダーにインストールされることも考えられます。</span><span class="sxs-lookup"><span data-stu-id="88197-176">Full trust applications may still need to load application data files that they do not know about at build time; while full trust applications could use file:///, it is likely that the application data files will be installed in the same folder as, or a subfolder of, the application assembly.</span></span> <span data-ttu-id="88197-177">この場合は、起点サイト参照を使用する方が、file:/// を使用するよりも簡単です。file:/// を使用するには、ファイルの完全パスを指定する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="88197-177">In this case, using site of origin referencing is easier than using file:///, because using file:/// requires you to work out the full path the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="88197-178">起点サイトファイルは、クライアントコンピューターに [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] と共にキャッシュされることはありませんが、コンテンツファイルはです。</span><span class="sxs-lookup"><span data-stu-id="88197-178">Site of origin files are not cached with an [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] on a client machine, while content files are.</span></span> <span data-ttu-id="88197-179">したがって、起点サイト ファイルは明確に要求されたときにのみダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="88197-179">Consequently, they are only downloaded when specifically requested.</span></span> <span data-ttu-id="88197-180">@No__t_0 アプリケーションに大きなメディアファイルが含まれている場合は、それらを起点サイトファイルとして構成すると、最初のアプリケーションの起動にかかる時間が大幅に短縮され、ファイルは要求時にのみダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="88197-180">If an [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] application has large media files, configuring them as site of origin files means the initial application launch is much faster, and the files are only downloaded on demand.</span></span>  
  
### <a name="configuring-site-of-origin-files"></a><span data-ttu-id="88197-181">起点サイト ファイルの構成</span><span class="sxs-lookup"><span data-stu-id="88197-181">Configuring Site of Origin Files</span></span>  
 <span data-ttu-id="88197-182">コンパイル時に起点サイトファイルが存在しないか不明な場合は、`XCopy` コマンドラインプログラムまたは [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)] を使用するなど、必要なファイルを実行時に確実に使用できるようにするために、従来の配置メカニズムを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88197-182">If your site of origin files are non-existent or unknown at compile time, you need to use traditional deployment mechanisms for ensuring the required files are available at run time, including using either the `XCopy` command-line program or the [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].</span></span>  
  
 <span data-ttu-id="88197-183">発行元のサイトに配置する必要があるファイルがコンパイル時にわかっていても、明示的な依存関係を回避したい場合は、それらのファイルを `None` 項目として MSBuild プロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="88197-183">If you do know at compile time the files that you would like to be located at the site of origin, but still want to avoid an explicit dependency, you can add those files to an MSBuild project as `None` item.</span></span> <span data-ttu-id="88197-184">コンテンツファイルと同様に、MSBuild `CopyToOutputDirectory` 属性を設定して、`Always` 値または `PreserveNewest` 値を指定することによって、ビルドされたアセンブリに対して相対的な場所に起点サイトファイルをコピーするように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88197-184">As with content files, you need to set the MSBuild `CopyToOutputDirectory` attribute to specify that the site of origin file is copied to a location that is relative to the built assembly, by specifying either the `Always` value or the `PreserveNewest` value.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <None Include="PageSiteOfOriginFile.xaml">  
    <CopyToOutputDirectory>Always</CopyToOutputDirectory>  
  </None>  
  ...  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="88197-185">@No__t_0 では、プロジェクトにファイルを追加し、その `Build Action` を `None` に設定することにより、起点サイトファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="88197-185">In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], you create a site of origin file by adding a file to a project and setting its `Build Action` to `None`.</span></span>  
  
 <span data-ttu-id="88197-186">プロジェクトがビルドされると、MSBuild は、指定されたファイルをビルド出力フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="88197-186">When the project is built, MSBuild copies the specified files to the build output folder.</span></span>  
  
### <a name="using-site-of-origin-files"></a><span data-ttu-id="88197-187">起点サイト ファイルの使用</span><span class="sxs-lookup"><span data-stu-id="88197-187">Using Site of Origin Files</span></span>  
 <span data-ttu-id="88197-188">起点サイトファイルを読み込むには、<xref:System.Windows.Application> クラスの <xref:System.Windows.Application.GetRemoteStream%2A> メソッドを呼び出して、目的の起点サイトファイルを識別するパック URI を渡します。</span><span class="sxs-lookup"><span data-stu-id="88197-188">To load a site of origin file, you can call the <xref:System.Windows.Application.GetRemoteStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired site of origin file.</span></span> <span data-ttu-id="88197-189"><xref:System.Windows.Application.GetRemoteStream%2A> は <xref:System.Windows.Resources.StreamResourceInfo> オブジェクトを返します。これにより、起点サイトファイルが <xref:System.IO.Stream> として公開され、そのコンテンツの種類が記述されます。</span><span class="sxs-lookup"><span data-stu-id="88197-189"><xref:System.Windows.Application.GetRemoteStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the site of origin file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="88197-190">例として、次のコードは、<xref:System.Windows.Application.GetRemoteStream%2A> を使用して元のファイルの <xref:System.Windows.Controls.Page> サイトを読み込み、<xref:System.Windows.Controls.Frame> (`pageFrame`) のコンテンツとして設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="88197-190">As an example, the following code shows how to use <xref:System.Windows.Application.GetRemoteStream%2A> to load a <xref:System.Windows.Controls.Page> site of origin file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 <span data-ttu-id="88197-191">@No__t_0 を呼び出すと <xref:System.IO.Stream> にアクセスできますが、それを設定するプロパティの型に変換する追加作業を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88197-191">While calling <xref:System.Windows.Application.GetRemoteStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="88197-192">代わりに、コードを使用して、リソースファイルを型のプロパティに直接読み込むことによって、<xref:System.IO.Stream> を開いて変換できるように [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] できます。</span><span class="sxs-lookup"><span data-stu-id="88197-192">Instead, you can let [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="88197-193">次の例は、コードを使用して <xref:System.Windows.Controls.Frame> (`pageFrame`) に <xref:System.Windows.Controls.Page> を直接読み込む方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="88197-193">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 <span data-ttu-id="88197-194">次の例は、上の例と同じ意味のマークアップです。</span><span class="sxs-lookup"><span data-stu-id="88197-194">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a><span data-ttu-id="88197-195">ビルドの種類を変更した後のリビルド</span><span class="sxs-lookup"><span data-stu-id="88197-195">Rebuilding After Changing Build Type</span></span>  
 <span data-ttu-id="88197-196">アプリケーション データ ファイルのビルドの種類を変更した後は、変更を確実に反映するためにアプリケーション全体をリビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="88197-196">After you change the build type of an application data file, you need to rebuild the entire application to ensure those changes are applied.</span></span> <span data-ttu-id="88197-197">アプリケーションのみをビルドしても、変更は適用されません。</span><span class="sxs-lookup"><span data-stu-id="88197-197">If you only build the application, the changes are not applied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88197-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="88197-198">See also</span></span>

- [<span data-ttu-id="88197-199">WPF におけるパッケージの URI</span><span class="sxs-lookup"><span data-stu-id="88197-199">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)
