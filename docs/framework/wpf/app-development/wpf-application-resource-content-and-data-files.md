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
ms.openlocfilehash: 2c48788507eed40e8240491dbd5064ad6c293c9f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651927"
---
# <a name="wpf-application-resource-content-and-data-files"></a><span data-ttu-id="1b1e2-102">WPF アプリケーションのリソース ファイル、コンテンツ ファイル、およびデータ ファイル</span><span class="sxs-lookup"><span data-stu-id="1b1e2-102">WPF Application Resource, Content, and Data Files</span></span>
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] <span data-ttu-id="1b1e2-103">多くの場合など、非実行可能ファイルのデータを含むファイルに依存するアプリケーション[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]イメージ、ビデオ、およびオーディオです。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-103">applications often depend on files that contain non-executable data, such as [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], images, video, and audio.</span></span> <span data-ttu-id="1b1e2-104">Windows Presentation Foundation (WPF) の構成の識別、およびこれらの種類のアプリケーション データ ファイルと呼ばれる、データ ファイルを使用して特別なサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-104">Windows Presentation Foundation (WPF) offers special support for configuring, identifying, and using these types of data files, which are called application data files.</span></span> <span data-ttu-id="1b1e2-105">このサポートの中心となるのは、次のような特定のアプリケーション データ ファイルの種類のセットです。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-105">This support revolves around a specific set of application data file types, including:</span></span>  
  
- <span data-ttu-id="1b1e2-106">**リソース ファイル**:データ ファイルも実行可能ファイルまたはライブラリにコンパイルされる[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-106">**Resource Files**: Data files that are compiled into either an executable or library [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] assembly.</span></span>  
  
- <span data-ttu-id="1b1e2-107">**コンテンツ ファイル**:スタンドアロン データ ファイルを実行可能ファイルとの明示的な関連付けを持つ[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-107">**Content Files**: Standalone data files that have an explicit association with an executable [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] assembly.</span></span>  
  
- <span data-ttu-id="1b1e2-108">**起点サイト ファイル**:実行可能ファイルとの関連付けを持たないスタンドアロン データ ファイル[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-108">**Site of Origin Files**: Standalone data files that have no association with an executable [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] assembly.</span></span>  
  
 <span data-ttu-id="1b1e2-109">これらの 3 種類のファイルの重要な違いは、リソース ファイルとコンテンツ ファイルはビルド時に認識されるという点です。アセンブリは、これらを明確に認識します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-109">One important distinction to make between these three types of files is that resource files and content files are known at build time; an assembly has explicit knowledge of them.</span></span> <span data-ttu-id="1b1e2-110">起点サイト ファイル、ただし、アセンブリがありますそれらの知識、またはパックを使用して暗黙的な知識[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]参照。 後者の場合、参照される起点サイト ファイルが実際に存在する保証はありません。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-110">For site of origin files, however, an assembly may have no knowledge of them at all, or implicit knowledge through a pack [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] reference; the case of the latter, there is no guarantee that the referenced site of origin file actually exists.</span></span>  
  
 <span data-ttu-id="1b1e2-111">Windows Presentation Foundation (WPF) が、パックを使用するにはアプリケーション データ ファイルを参照するには、[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]はで詳しく説明されているスキーム[WPF におけるパック Uri](pack-uris-in-wpf.md))。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-111">To reference application data files, Windows Presentation Foundation (WPF) uses the Pack [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] Scheme, which is described in detail in [Pack URIs in WPF](pack-uris-in-wpf.md)).</span></span>  
  
 <span data-ttu-id="1b1e2-112">このトピックでは、アプリケーション データ ファイルを構成および使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-112">This topic describes how to configure and use application data files.</span></span>  

<a name="Resource_Files"></a>   
## <a name="resource-files"></a><span data-ttu-id="1b1e2-113">リソース ファイル (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="1b1e2-113">Resource Files</span></span>  
 <span data-ttu-id="1b1e2-114">アプリケーション データ ファイルを常にアプリケーションで使用可能にするには、コンパイルしてアプリケーションのメイン実行可能アセンブリまたはその参照アセンブリの 1 つに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-114">If an application data file must always be available to an application, the only way to guarantee availability is to compile it into an application's main executable assembly or one of its referenced assemblies.</span></span> <span data-ttu-id="1b1e2-115">この種類のアプリケーション データ ファイルと呼ばれる、*リソース ファイル*します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-115">This type of application data file is known as a *resource file*.</span></span>  
  
 <span data-ttu-id="1b1e2-116">リソース ファイルは、次のときに使用します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-116">You should use resource files when:</span></span>  
  
- <span data-ttu-id="1b1e2-117">コンパイルしてアセンブリに組み込んだ後に、リソース ファイルのコンテンツを更新する必要がない。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-117">You don't need to update the resource file's content after it is compiled into an assembly.</span></span>  
  
- <span data-ttu-id="1b1e2-118">ファイルの依存関係の数を減らして、アプリケーション配布の複雑さを軽減する必要がある。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-118">You want to simplify application distribution complexity by reducing the number of file dependencies.</span></span>  
  
- <span data-ttu-id="1b1e2-119">アプリケーション データ ファイルがローカライズ可能にする必要があります (を参照してください[WPF のグローバリゼーションおよびローカリゼーションの概要](../advanced/wpf-globalization-and-localization-overview.md))。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-119">Your application data file needs to be localizable (see [WPF Globalization and Localization Overview](../advanced/wpf-globalization-and-localization-overview.md)).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b1e2-120">このセクションで説明されているリソース ファイルは、リソース ファイルで説明されているものと異なる[XAML リソース](../advanced/xaml-resources.md)しで説明されている埋め込みまたはリンクされたリソースとは異なる[管理アプリケーションのリソース (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="1b1e2-120">The resource files described in this section are different than the resource files described in [XAML Resources](../advanced/xaml-resources.md) and different than the embedded or linked resources described in [Manage Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
### <a name="configuring-resource-files"></a><span data-ttu-id="1b1e2-121">リソース ファイルの構成</span><span class="sxs-lookup"><span data-stu-id="1b1e2-121">Configuring Resource Files</span></span>  
 <span data-ttu-id="1b1e2-122">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]、リソース ファイルに含まれているファイルとは、[!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)]プロジェクトとして、`Resource`項目。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-122">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], a resource file is a file that is included in an [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] project as a `Resource` item.</span></span>  
  
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
>  <span data-ttu-id="1b1e2-123">[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]、リソース ファイルを作成するファイルをプロジェクトの設定を追加してその`Build Action`に`Resource`します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-123">In [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], you create a resource file by adding a file to a project and setting its `Build Action` to `Resource`.</span></span>  
  
 <span data-ttu-id="1b1e2-124">プロジェクトのビルド時に[!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]リソースをアセンブリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-124">When the project is built, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] compiles the resource into the assembly.</span></span>  
  
### <a name="using-resource-files"></a><span data-ttu-id="1b1e2-125">リソース ファイルの使用</span><span class="sxs-lookup"><span data-stu-id="1b1e2-125">Using Resource Files</span></span>  
 <span data-ttu-id="1b1e2-126">リソース ファイルを読み込むを呼び出すことができます、<xref:System.Windows.Application.GetResourceStream%2A>のメソッド、<xref:System.Windows.Application>クラス、パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]目的のリソース ファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-126">To load a resource file, you can call the <xref:System.Windows.Application.GetResourceStream%2A> method of the <xref:System.Windows.Application> class, passing a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that identifies the desired resource file.</span></span> <span data-ttu-id="1b1e2-127"><xref:System.Windows.Application.GetResourceStream%2A> 返します、<xref:System.Windows.Resources.StreamResourceInfo>リソース ファイルとして公開するオブジェクト、<xref:System.IO.Stream>とそのコンテンツの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-127"><xref:System.Windows.Application.GetResourceStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the resource file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="1b1e2-128">たとえば、次のコードが使用する方法を示します<xref:System.Windows.Application.GetResourceStream%2A>を読み込む、<xref:System.Windows.Controls.Page>リソース ファイルし、のコンテンツとして設定する、 <xref:System.Windows.Controls.Frame> (`pageFrame`)。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-128">As an example, the following code shows how to use <xref:System.Windows.Application.GetResourceStream%2A> to load a <xref:System.Windows.Controls.Page> resource file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`):</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 <span data-ttu-id="1b1e2-129">呼び出し中に<xref:System.Windows.Application.GetResourceStream%2A>にアクセスすること、 <xref:System.IO.Stream>、それを設定 プロパティの型に変換する余分な作業を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-129">While calling <xref:System.Windows.Application.GetResourceStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="1b1e2-130">代わりに、させることができます[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]注意を開いたり変換したり、<xref:System.IO.Stream>でコードを使用して型のプロパティに直接、リソース ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-130">Instead, you can let [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="1b1e2-131">次の例を読み込む方法を示しています、<xref:System.Windows.Controls.Page>に直接、 <xref:System.Windows.Controls.Frame> (`pageFrame`) コードを使用します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-131">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 <span data-ttu-id="1b1e2-132">次の例は、上の例と同じ意味のマークアップです。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-132">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a><span data-ttu-id="1b1e2-133">リソース ファイルとしてのアプリケーション コード ファイル</span><span class="sxs-lookup"><span data-stu-id="1b1e2-133">Application Code Files as Resource Files</span></span>  
 <span data-ttu-id="1b1e2-134">一連の特殊な[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]パックを使用して、アプリケーション コード ファイルを参照できる[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)](windows、ページ、フロー ドキュメント、リソース ディクショナリなど)。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-134">A special set of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application code files can be referenced using pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], including windows, pages, flow documents, and resource dictionaries.</span></span> <span data-ttu-id="1b1e2-135">たとえば、設定、<xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>パック プロパティ[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]ウィンドウまたはアプリケーションの起動時に読み込むしたいページを参照します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-135">For example, you can set the <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> property with a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that references the window or page that you would like to load when an application starts.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 <span data-ttu-id="1b1e2-136">場合にこのを行うことができます、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]でファイルが含まれて、[!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)]プロジェクトとして、`Page`項目。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-136">You can do this when a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is included in an [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] project as a `Page` item.</span></span>  
  
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
>  <span data-ttu-id="1b1e2-137">[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]、追加<xref:System.Windows.Window>、 <xref:System.Windows.Navigation.NavigationWindow>、 <xref:System.Windows.Controls.Page>、 <xref:System.Windows.Documents.FlowDocument>、または<xref:System.Windows.ResourceDictionary>をプロジェクトに、`Build Action`ファイルは既定のマークアップ`Page`します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-137">In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], you add a new <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>, or <xref:System.Windows.ResourceDictionary> to a project, the `Build Action` for the markup file will default to `Page`.</span></span>  
  
 <span data-ttu-id="1b1e2-138">ときに、プロジェクトで`Page`項目がコンパイルされると、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]項目がバイナリ形式に変換され、関連付けられているアセンブリにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-138">When a project with `Page` items is compiled, the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] items are converted to binary format and compiled into the associated assembly.</span></span> <span data-ttu-id="1b1e2-139">したがって、これらのファイルは、通常のリソース ファイルと同様に使用できます。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-139">Consequently, these files can be used in the same way as typical resource files.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b1e2-140">場合、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]としてファイルが構成されている、`Resource`項目、および分離コード ファイル、生がない[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]は、生のバイナリのバージョンではなく、アセンブリにコンパイル[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-140">If a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is configured as a `Resource` item, and does not have a code-behind file, the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is compiled into an assembly rather than a binary version of the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a><span data-ttu-id="1b1e2-141">コンテンツ ファイル</span><span class="sxs-lookup"><span data-stu-id="1b1e2-141">Content Files</span></span>  
 <span data-ttu-id="1b1e2-142">A*コンテンツ ファイル*は実行可能アセンブリと共に圧縮しないファイルとして配布されます。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-142">A *content file* is distributed as a loose file alongside an executable assembly.</span></span> <span data-ttu-id="1b1e2-143">コンテンツ ファイルはコンパイルされてアセンブリに組み込まれるのではありませんが、アセンブリのコンパイル時に、各コンテンツ ファイルとの関連付けを確立するメタデータが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-143">Although they are not compiled into an assembly, assemblies are compiled with metadata that establishes an association with each content file.</span></span>  
  
 <span data-ttu-id="1b1e2-144">アプリケーションに必要な特定のアプリケーション データ ファイルのセットが更新されても、そのファイルを使用するアセンブリを再コンパイルせずに、コンテンツ ファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-144">You should use content files when your application requires a specific set of application data files that you want to be able to update without recompiling the assembly that consumes them.</span></span>  
  
### <a name="configuring-content-files"></a><span data-ttu-id="1b1e2-145">コンテンツ ファイルの構成</span><span class="sxs-lookup"><span data-stu-id="1b1e2-145">Configuring Content Files</span></span>  
 <span data-ttu-id="1b1e2-146">コンテンツ ファイルをプロジェクトに追加するには、アプリケーション データ ファイルでとして指定する必要があります、`Content`項目。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-146">To add a content file to a project, an application data file must be included as a `Content` item.</span></span> <span data-ttu-id="1b1e2-147">さらに、コンテンツ ファイルがアセンブリに直接コンパイルされていないため、設定する必要が、 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory`メタデータ要素をコンテンツ ファイルがビルドされたアセンブリに対して相対的な場所にコピーされたことを指定します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-147">Furthermore, because a content file is not compiled directly into the assembly, you need to set the [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`CopyToOutputDirectory` metadata element to specify that the content file is copied to a location that is relative to the built assembly.</span></span> <span data-ttu-id="1b1e2-148">プロジェクトをビルド、リソースを毎回ビルド出力フォルダーにコピーする場合は、設定、`CopyToOutputDirectory`メタデータ要素を`Always`値。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-148">If you want the resource to be copied to the build output folder every time a project is built, you set the `CopyToOutputDirectory` metadata element with the `Always` value.</span></span> <span data-ttu-id="1b1e2-149">使用してビルド出力フォルダーにリソースの最新バージョンのみがコピーされたことを確認する場合は、`PreserveNewest`値。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-149">Otherwise, you can ensure that only the newest version of the resource is copied to the build output folder by using the `PreserveNewest` value.</span></span>  
  
 <span data-ttu-id="1b1e2-150">次に示すファイルは、新しいバージョンのリソースがプロジェクトに追加された場合にのみビルド出力フォルダーにコピーされるコンテンツ ファイルとして構成されています。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-150">The following shows a file that is configured as a content file which is copied to the build output folder only when a new version of the resource is added to the project.</span></span>  
  
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
>  <span data-ttu-id="1b1e2-151">[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]、ファイルをプロジェクトの設定を追加して、コンテンツ ファイルを作成するその`Build Action`に`Content`、設定とその`Copy to Output Directory`に`Copy always`(と同じ`Always`) と`Copy if newer`(と同じ`PreserveNewest`)。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-151">In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], you create a content file by adding a file to a project and setting its `Build Action` to `Content`, and set its `Copy to Output Directory` to `Copy always` (same as `Always`) and `Copy if newer` (same as `PreserveNewest`).</span></span>  
  
 <span data-ttu-id="1b1e2-152">プロジェクトをビルドするとき、<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>属性は各コンテンツ ファイルのアセンブリのメタデータにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-152">When the project is built, an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is compiled into the metadata of the assembly for each content file.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 <span data-ttu-id="1b1e2-153">値、<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>プロジェクト内の位置に対して相対的なコンテンツのファイルへのパスを意味します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-153">The value of the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> implies the path to the content file relative to its position in the project.</span></span> <span data-ttu-id="1b1e2-154">たとえば、コンテンツ ファイルは、プロジェクトのサブフォルダーにありますが、追加パス情報に組み込む、<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>値。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-154">For example, if a content file was located in a project subfolder, the additional path information would be incorporated into the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <span data-ttu-id="1b1e2-155"><xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>値も、ビルド出力フォルダー内のコンテンツのファイルへのパスの値。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-155">The <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value is also the value of the path to the content file in the build output folder.</span></span>  
  
### <a name="using-content-files"></a><span data-ttu-id="1b1e2-156">コンテンツ ファイルの使用</span><span class="sxs-lookup"><span data-stu-id="1b1e2-156">Using Content Files</span></span>  
 <span data-ttu-id="1b1e2-157">コンテンツ ファイルを読み込むを呼び出すことができます、<xref:System.Windows.Application.GetContentStream%2A>のメソッド、<xref:System.Windows.Application>クラス、パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]目的のコンテンツ ファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-157">To load a content file, you can call the <xref:System.Windows.Application.GetContentStream%2A> method of the <xref:System.Windows.Application> class, passing a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that identifies the desired content file.</span></span> <span data-ttu-id="1b1e2-158"><xref:System.Windows.Application.GetContentStream%2A> 返します、<xref:System.Windows.Resources.StreamResourceInfo>コンテンツ ファイルとして公開するオブジェクト、<xref:System.IO.Stream>とそのコンテンツの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-158"><xref:System.Windows.Application.GetContentStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the content file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="1b1e2-159">たとえば、次のコードが使用する方法を示します<xref:System.Windows.Application.GetContentStream%2A>を読み込む、<xref:System.Windows.Controls.Page>ファイルのコンテンツし、のコンテンツとして設定する、 <xref:System.Windows.Controls.Frame> (`pageFrame`)。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-159">As an example, the following code shows how to use <xref:System.Windows.Application.GetContentStream%2A> to load a <xref:System.Windows.Controls.Page> content file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 <span data-ttu-id="1b1e2-160">呼び出し中に<xref:System.Windows.Application.GetContentStream%2A>にアクセスすること、 <xref:System.IO.Stream>、それを設定 プロパティの型に変換する余分な作業を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-160">While calling <xref:System.Windows.Application.GetContentStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="1b1e2-161">代わりに、させることができます[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]注意を開いたり変換したり、<xref:System.IO.Stream>でコードを使用して型のプロパティに直接、リソース ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-161">Instead, you can let [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="1b1e2-162">次の例を読み込む方法を示しています、<xref:System.Windows.Controls.Page>に直接、 <xref:System.Windows.Controls.Frame> (`pageFrame`) コードを使用します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-162">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 <span data-ttu-id="1b1e2-163">次の例は、上の例と同じ意味のマークアップです。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-163">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a><span data-ttu-id="1b1e2-164">起点サイト ファイル</span><span class="sxs-lookup"><span data-stu-id="1b1e2-164">Site of Origin Files</span></span>  
 <span data-ttu-id="1b1e2-165">リソース ファイルで定義されている、共に配布されるアセンブリを使用した明示的な関連付けがある場合、<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-165">Resource files have an explicit relationship with the assemblies that they are distributed alongside, as defined by the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.</span></span> <span data-ttu-id="1b1e2-166">ただし、アセンブリとアプリケーション データ ファイル間に暗黙的な関係を持たせる、または関係を持たせない場合があります。たとえば次のような場合です。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-166">But, there are times when you may want to establish either an implicit or non-existent relationship between an assembly and an application data file, including when:</span></span>  
  
- <span data-ttu-id="1b1e2-167">ファイルは、コンパイル時に存在しません。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-167">A file doesn't exist at compile time.</span></span>  
  
- <span data-ttu-id="1b1e2-168">アセンブリが必要とするファイルが、実行時までわからない場合。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-168">You don't know what files your assembly will require until run time.</span></span>  
  
- <span data-ttu-id="1b1e2-169">関連付けられているアセンブリを再コンパイルせずにファイルを更新可能にする場合。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-169">You want to be able to update files without recompiling the assembly that they are associated with.</span></span>  
  
- <span data-ttu-id="1b1e2-170">オーディオやビデオなど大容量のデータ ファイルを使用するアプリケーションで、ユーザーが選択した場合にのみファイルをダウンロードする場合。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-170">Your application uses large data files, such as audio and video, and you only want users to download them if they choose to.</span></span>  
  
 <span data-ttu-id="1b1e2-171">この種の従来型を使用してファイルをロードすることは[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]file:/// http:// 方式などのスキーム。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-171">It is possible to load these types of files by using traditional [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] schemes, such as the file:/// and http:// schemes.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 <span data-ttu-id="1b1e2-172">ただし、file:/// スキームや http:// スキームを使用する場合は、アプリケーションに完全信頼が必要です。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-172">However, the file:/// and http:// schemes require your application to have full trust.</span></span> <span data-ttu-id="1b1e2-173">アプリケーションの場合、[!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]がインターネットまたはイントラネットから起動して、圧縮しないファイルは、配信元 (アプリケーションのサイトからのみ読み込むことが、それらの場所から起動するアプリケーションの許可されるアクセス許可のセットのみを要求場所を起動) します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-173">If your application is a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that was launched from the Internet or intranet, and it requests only the set of permissions that are allowed for applications launched from those locations, loose files can only be loaded from the application's site of origin (launch location).</span></span> <span data-ttu-id="1b1e2-174">このようなファイルと呼びます*起点サイト*ファイル。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-174">Such files are known as *site of origin* files.</span></span>  
  
 <span data-ttu-id="1b1e2-175">起点サイト ファイルは部分信頼アプリケーションの唯一のオプションですが、部分信頼アプリケーション以外でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-175">Site of origin files are the only option for partial trust applications, although are not limited to partial trust applications.</span></span> <span data-ttu-id="1b1e2-176">完全信頼アプリケーションでも、読み込むアプリケーション データ ファイルがビルド時点では不明な場合があります。完全信頼アプリケーションでは file:/// を使用できますが、アプリケーション データ ファイルがアプリケーション アセンブリと同じフォルダーにインストールされることも、サブフォルダーにインストールされることも考えられます。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-176">Full trust applications may still need to load application data files that they do not know about at build time; while full trust applications could use file:///, it is likely that the application data files will be installed in the same folder as, or a subfolder of, the application assembly.</span></span> <span data-ttu-id="1b1e2-177">この場合は、起点サイト参照を使用する方が、file:/// を使用するよりも簡単です。file:/// を使用するには、ファイルの完全パスを指定する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-177">In this case, using site of origin referencing is easier than using file:///, because using file:/// requires you to work out the full path the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b1e2-178">ファイルがでキャッシュされません起点サイト、[!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]コンテンツ ファイルは、クライアント コンピューター上です。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-178">Site of origin files are not cached with an [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] on a client machine, while content files are.</span></span> <span data-ttu-id="1b1e2-179">したがって、起点サイト ファイルは明確に要求されたときにのみダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-179">Consequently, they are only downloaded when specifically requested.</span></span> <span data-ttu-id="1b1e2-180">場合、[!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]アプリケーションが大量のメディア ファイル、起点サイト ファイルは、初期のアプリケーションの起動がはるかに高速でありオンデマンド ファイルのダウンロードのみを意味として構成します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-180">If an [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] application has large media files, configuring them as site of origin files means the initial application launch is much faster, and the files are only downloaded on demand.</span></span>  
  
### <a name="configuring-site-of-origin-files"></a><span data-ttu-id="1b1e2-181">起点サイト ファイルの構成</span><span class="sxs-lookup"><span data-stu-id="1b1e2-181">Configuring Site of Origin Files</span></span>  
 <span data-ttu-id="1b1e2-182">起点サイト ファイルがコンパイル時に存在しないか不明な場合は、従来の展開を使用する必要がありますいずれかの使用など、実行時に、必要なファイルを確保するためのメカニズムが使用可能な、`XCopy`コマンド ライン プログラム、または、 [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b1e2-182">If your site of origin files are non-existent or unknown at compile time, you need to use traditional deployment mechanisms for ensuring the required files are available at run time, including using either the `XCopy` command-line program or the [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].</span></span>  
  
 <span data-ttu-id="1b1e2-183">それらのファイルを追加することがわかっている場合はコンパイル時にファイルを元のサイトに配置されるような場合は明示的な依存関係をしないように、[!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)]プロジェクトとして`None`項目。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-183">If you do know at compile time the files that you would like to be located at the site of origin, but still want to avoid an explicit dependency, you can add those files to an [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] project as `None` item.</span></span> <span data-ttu-id="1b1e2-184">コンテンツのファイルで設定する必要がある、 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory`元のファイルのサイトがいずれかを指定することによってビルドされたアセンブリに対応する場所にコピーされていることを指定する属性、`Always`値または`PreserveNewest`値。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-184">As with content files, you need to set the [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`CopyToOutputDirectory` attribute to specify that the site of origin file is copied to a location that is relative to the built assembly, by specifying either the `Always` value or the `PreserveNewest` value.</span></span>  
  
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
>  <span data-ttu-id="1b1e2-185">[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]、ファイルをプロジェクトの設定を追加して元のファイルのサイトを作成するその`Build Action`に`None`します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-185">In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], you create a site of origin file by adding a file to a project and setting its `Build Action` to `None`.</span></span>  
  
 <span data-ttu-id="1b1e2-186">プロジェクトのビルド時に[!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]ビルド出力フォルダーに、指定されたファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-186">When the project is built, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] copies the specified files to the build output folder.</span></span>  
  
### <a name="using-site-of-origin-files"></a><span data-ttu-id="1b1e2-187">起点サイト ファイルの使用</span><span class="sxs-lookup"><span data-stu-id="1b1e2-187">Using Site of Origin Files</span></span>  
 <span data-ttu-id="1b1e2-188">呼び出すことができます、起点サイト ファイルを読み込むには、<xref:System.Windows.Application.GetRemoteStream%2A>のメソッド、<xref:System.Windows.Application>クラス、パック[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]元のファイルの目的のサイトを識別します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-188">To load a site of origin file, you can call the <xref:System.Windows.Application.GetRemoteStream%2A> method of the <xref:System.Windows.Application> class, passing a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that identifies the desired site of origin file.</span></span> <span data-ttu-id="1b1e2-189"><xref:System.Windows.Application.GetRemoteStream%2A> 返します、<xref:System.Windows.Resources.StreamResourceInfo>としてファイルを配信元のサイトを公開するには、オブジェクト、<xref:System.IO.Stream>とそのコンテンツの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-189"><xref:System.Windows.Application.GetRemoteStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the site of origin file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="1b1e2-190">たとえば、次のコードが使用する方法を示します<xref:System.Windows.Application.GetRemoteStream%2A>を読み込む、<xref:System.Windows.Controls.Page>起点サイト ファイルし、のコンテンツとして設定、 <xref:System.Windows.Controls.Frame> (`pageFrame`)。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-190">As an example, the following code shows how to use <xref:System.Windows.Application.GetRemoteStream%2A> to load a <xref:System.Windows.Controls.Page> site of origin file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 <span data-ttu-id="1b1e2-191">呼び出し中に<xref:System.Windows.Application.GetRemoteStream%2A>にアクセスすること、 <xref:System.IO.Stream>、それを設定 プロパティの型に変換する余分な作業を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-191">While calling <xref:System.Windows.Application.GetRemoteStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="1b1e2-192">代わりに、させることができます[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]注意を開いたり変換したり、<xref:System.IO.Stream>でコードを使用して型のプロパティに直接、リソース ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-192">Instead, you can let [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="1b1e2-193">次の例を読み込む方法を示しています、<xref:System.Windows.Controls.Page>に直接、 <xref:System.Windows.Controls.Frame> (`pageFrame`) コードを使用します。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-193">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 <span data-ttu-id="1b1e2-194">次の例は、上の例と同じ意味のマークアップです。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-194">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a><span data-ttu-id="1b1e2-195">ビルドの種類を変更した後のリビルド</span><span class="sxs-lookup"><span data-stu-id="1b1e2-195">Rebuilding After Changing Build Type</span></span>  
 <span data-ttu-id="1b1e2-196">アプリケーション データ ファイルのビルドの種類を変更した後は、変更を確実に反映するためにアプリケーション全体をリビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-196">After you change the build type of an application data file, you need to rebuild the entire application to ensure those changes are applied.</span></span> <span data-ttu-id="1b1e2-197">アプリケーションのみをビルドしても、変更は適用されません。</span><span class="sxs-lookup"><span data-stu-id="1b1e2-197">If you only build the application, the changes are not applied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b1e2-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b1e2-198">See also</span></span>

- [<span data-ttu-id="1b1e2-199">WPF におけるパッケージの URI</span><span class="sxs-lookup"><span data-stu-id="1b1e2-199">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)
