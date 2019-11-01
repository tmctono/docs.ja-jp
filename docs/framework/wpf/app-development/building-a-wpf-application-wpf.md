---
title: WPF アプリケーション (WPF) のビルド
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF application [WPF], building
ms.assetid: a58696fd-bdad-4b55-9759-136dfdf8b91c
ms.openlocfilehash: cac7a7552d1a24480d614b7b90fdd8cf0ef8a3e8
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197797"
---
# <a name="building-a-wpf-application-wpf"></a><span data-ttu-id="37505-102">WPF アプリケーション (WPF) のビルド</span><span class="sxs-lookup"><span data-stu-id="37505-102">Building a WPF Application (WPF)</span></span>

<span data-ttu-id="37505-103">Windows Presentation Foundation (WPF) アプリケーションは、.NET Framework の実行可能ファイル (.exe)、ライブラリ (.dll)、または両方の種類のアセンブリの組み合わせとしてビルドできます。</span><span class="sxs-lookup"><span data-stu-id="37505-103">Windows Presentation Foundation (WPF) applications can be built as .NET Framework executables (.exe), libraries (.dll), or a combination of both types of assemblies.</span></span> <span data-ttu-id="37505-104">このトピックでは、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] アプリケーションをビルドする方法を紹介し、ビルド プロセスの主な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="37505-104">This topic introduces how to build [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications and describes the key steps in the build process.</span></span>

<a name="Building_a_WPF_Application_using_Command_Line"></a>

## <a name="building-a-wpf-application"></a><span data-ttu-id="37505-105">WPF アプリケーションのビルド</span><span class="sxs-lookup"><span data-stu-id="37505-105">Building a WPF Application</span></span>

<span data-ttu-id="37505-106">WPF アプリケーションは、次の方法でコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="37505-106">A WPF application can be compiled in the following ways:</span></span>

- <span data-ttu-id="37505-107">コマンド ライン。</span><span class="sxs-lookup"><span data-stu-id="37505-107">Command-line.</span></span> <span data-ttu-id="37505-108">アプリケーションには、コード (XAML ではない) とアプリケーション定義ファイルだけを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="37505-108">The application must contain only code (no XAML) and an application definition file.</span></span> <span data-ttu-id="37505-109">詳細については、「[csc.exe を使用したコマンド ラインからのビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)」または「[コマンド ラインからのビルド (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37505-109">For more information, see [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Building from the Command Line (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>

- <span data-ttu-id="37505-110">Microsoft Build Engine (MSBuild)。</span><span class="sxs-lookup"><span data-stu-id="37505-110">Microsoft Build Engine (MSBuild).</span></span> <span data-ttu-id="37505-111">コードと XAML ファイルに加えて、アプリケーションには MSBuild プロジェクト ファイルを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="37505-111">In addition to the code and XAML files, the application must contain an MSBuild project file.</span></span> <span data-ttu-id="37505-112">詳細については、「MSBuild」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37505-112">For more information, see "MSBuild".</span></span>

- <span data-ttu-id="37505-113">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="37505-113">Visual Studio.</span></span> <span data-ttu-id="37505-114">Visual Studio は、MSBuild を使用して WPF アプリケーションをコンパイルする統合開発環境であり、UI を作成するためのビジュアル デザイナーを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="37505-114">Visual Studio is an integrated development environment that compiles WPF applications with MSBuild and includes a visual designer for creating UI.</span></span> <span data-ttu-id="37505-115">詳細については、「 [Visual studio を使用したコードの記述と管理](/visualstudio/ide/index-writing-code)」および「 [visual STUDIO での XAML のデザイン](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37505-115">For more information, see [Write and manage code using Visual Studio](/visualstudio/ide/index-writing-code) and [Design XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span></span>

<a name="The_Windows_Presentation_Foundation_Build_Pipeline"></a>

## <a name="wpf-build-pipeline"></a><span data-ttu-id="37505-116">WPF ビルド パイプライン</span><span class="sxs-lookup"><span data-stu-id="37505-116">WPF Build Pipeline</span></span>

<span data-ttu-id="37505-117">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] プロジェクトがビルドされるときには、言語固有のターゲットと [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 固有のターゲットの組み合わせが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="37505-117">When a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] project is built, the combination of language-specific and [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-specific targets are invoked.</span></span> <span data-ttu-id="37505-118">これらのターゲットを実行するプロセスはビルド パイプラインと呼ばれます。主要な手順を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="37505-118">The process of executing these targets is called the build pipeline, and the key steps are illustrated by the following figure.</span></span>

<span data-ttu-id="37505-119">![WPF のビルドプロセス](./media/wpfbuildsystem-figure1.png "WPFBuildSystem_Figure1")</span><span class="sxs-lookup"><span data-stu-id="37505-119">![WPF build process](./media/wpfbuildsystem-figure1.png "WPFBuildSystem_Figure1")</span></span>

<a name="Pre_Build_Initializations"></a>

### <a name="pre-build-initializations"></a><span data-ttu-id="37505-120">ビルド前の初期化</span><span class="sxs-lookup"><span data-stu-id="37505-120">Pre-Build Initializations</span></span>

<span data-ttu-id="37505-121">ビルドする前に、MSBuild は次のような重要なツールとライブラリの場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="37505-121">Before building, MSBuild determines the location of important tools and libraries, including the following:</span></span>

- <span data-ttu-id="37505-122">.NET Framework。</span><span class="sxs-lookup"><span data-stu-id="37505-122">The .NET Framework.</span></span>

- <span data-ttu-id="37505-123">[!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)] ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="37505-123">The [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)] directories.</span></span>

- <span data-ttu-id="37505-124">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 参照アセンブリの場所。</span><span class="sxs-lookup"><span data-stu-id="37505-124">The location of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] reference assemblies.</span></span>

- <span data-ttu-id="37505-125">アセンブリ検索パスのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="37505-125">The property for the assembly search paths.</span></span>

<span data-ttu-id="37505-126">MSBuild がアセンブリを検索する最初の場所は、参照アセンブリディレクトリ (%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.0\\) です。</span><span class="sxs-lookup"><span data-stu-id="37505-126">The first location where MSBuild searches for assemblies is the reference assembly directory (%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.0\\).</span></span> <span data-ttu-id="37505-127">この手順では、ビルド プロセスはさまざまなプロパティと項目グループを初期化し、必要なクリーンアップ作業も実行します。</span><span class="sxs-lookup"><span data-stu-id="37505-127">During this step, the build process also initializes the various properties and item groups and performs any required cleanup work.</span></span>

<a name="Resolving_references"></a>

### <a name="resolving-references"></a><span data-ttu-id="37505-128">参照の解決</span><span class="sxs-lookup"><span data-stu-id="37505-128">Resolving References</span></span>

<span data-ttu-id="37505-129">ビルド プロセスは、アプリケーション プロジェクトのビルドに必要なアセンブリを探して、バインドします。</span><span class="sxs-lookup"><span data-stu-id="37505-129">The build process locates and binds the assemblies required to build the application project.</span></span> <span data-ttu-id="37505-130">このロジックは、`ResolveAssemblyReference` タスクに含まれます。</span><span class="sxs-lookup"><span data-stu-id="37505-130">This logic is contained in the `ResolveAssemblyReference` task.</span></span> <span data-ttu-id="37505-131">プロジェクト ファイル内で `Reference` として宣言されたすべてのアセンブリは、検索パスに関する情報と、すでにシステムにインストールされているアセンブリのメタデータと共にタスクに渡されます。</span><span class="sxs-lookup"><span data-stu-id="37505-131">All assemblies declared as `Reference` in the project file are provided to the task along with information on the search paths and metadata on assemblies already installed on the system.</span></span> <span data-ttu-id="37505-132">タスクは、アセンブリを検索し、インストールされているアセンブリのメタデータを使用して、出力マニフェストに含める必要のないコアの [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] アセンブリをフィルターして除外します。</span><span class="sxs-lookup"><span data-stu-id="37505-132">The task looks up assemblies and uses the installed assembly's metadata to filter out those core [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] assemblies that need not show up in the output manifests.</span></span> <span data-ttu-id="37505-133">これは、ClickOnce マニフェストに冗長な情報が含まれるのを避けるために行われます。</span><span class="sxs-lookup"><span data-stu-id="37505-133">This is done to avoid redundant information in the ClickOnce manifests.</span></span> <span data-ttu-id="37505-134">たとえば、プレゼンテーションフレームワーク .dll は、に組み込まれているアプリケーションの代表者として、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] と、さらに、.NET Framework がインストールされているすべてのコンピューター上のすべての [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] アセンブリが存在するため、マニフェスト内のすべての .NET Framework 参照アセンブリに関する情報をすべて含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="37505-134">For example, since PresentationFramework.dll can be considered representative of an application built on and for the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] and moreover since all [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] assemblies exist at the same location on every machine that has the .NET Framework installed, there is no need to include all information on all .NET Framework reference assemblies in the manifests.</span></span>

<a name="Markup_Compilation___Pass_1"></a>

### <a name="markup-compilationpass-1"></a><span data-ttu-id="37505-135">マークアップ コンパイル - パス 1</span><span class="sxs-lookup"><span data-stu-id="37505-135">Markup Compilation—Pass 1</span></span>

<span data-ttu-id="37505-136">この手順では、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルを解析してコンパイルし、ランタイムが [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] の解析やプロパティ値の検証に時間を費やさずに済むようにします。</span><span class="sxs-lookup"><span data-stu-id="37505-136">In this step, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files are parsed and compiled so that the runtime does not spend time parsing [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] and validating property values.</span></span> <span data-ttu-id="37505-137">コンパイルされた [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルを事前にトークン化するため、実行時の読み込みは、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルを読み込むよりもはるかに短時間で終わります。</span><span class="sxs-lookup"><span data-stu-id="37505-137">The compiled [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is pre-tokenized so that, at run time, loading it should be much faster than loading a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span>

<span data-ttu-id="37505-138">この手順では、`Page` ビルド項目である [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルごとに、次のアクティビティが実行されます。</span><span class="sxs-lookup"><span data-stu-id="37505-138">During this step, the following activities take place for every [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file that is a `Page` build item:</span></span>

1. <span data-ttu-id="37505-139">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルがマークアップ コンパイラによって解析されます。</span><span class="sxs-lookup"><span data-stu-id="37505-139">The [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is parsed by the markup compiler.</span></span>

2. <span data-ttu-id="37505-140">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 用にコンパイル済みの表現が作成されて、obj\Release フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="37505-140">A compiled representation is created for that [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and copied to the obj\Release folder.</span></span>

3. <span data-ttu-id="37505-141">新しい部分クラスの CodeDOM 表現が作成され、obj\Release フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="37505-141">A CodeDOM representation of a new partial class is created and copied to the obj\Release folder.</span></span>

<span data-ttu-id="37505-142">さらに、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルごとに、言語固有のコード ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="37505-142">In addition, a language-specific code file is generated for every [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="37505-143">たとえば、Visual Basic プロジェクトの Page1 ページの場合は、Page1 が生成されます。C#プロジェクトの Page1 ページの場合、Page1.g.cs が生成されます。</span><span class="sxs-lookup"><span data-stu-id="37505-143">For example, for a Page1.xaml page in a Visual Basic project, a Page1.g.vb is generated; for a Page1.xaml page in a C# project, a Page1.g.cs is generated.</span></span> <span data-ttu-id="37505-144">ファイル名の ".g" は、ファイルが生成されたコードであり、マークアップ ファイルのトップレベルの要素 (`Page` や `Window` など) に対する部分クラス宣言を持つことを示しています。</span><span class="sxs-lookup"><span data-stu-id="37505-144">The ".g" in the file name indicates the file is generated code that has a partial class declaration for the top-level element of the markup file (such as `Page` or `Window`).</span></span> <span data-ttu-id="37505-145">クラスは、(Visual Basic で`Extends`) のC# `partial` 修飾子を使用して宣言し、他の場所 (通常は分離コードファイル Page1.xaml.cs) に別の宣言があることを示します。</span><span class="sxs-lookup"><span data-stu-id="37505-145">The class is declared with the `partial` modifier in C# (`Extends` in Visual Basic) to indicate there is another declaration for the class elsewhere, usually in the code-behind file Page1.xaml.cs.</span></span>

<span data-ttu-id="37505-146">部分クラスは、適切な基本クラス (ページの <xref:System.Windows.Controls.Page> など) から拡張され、<xref:System.Windows.Markup.IComponentConnector?displayProperty=nameWithType> インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="37505-146">The partial class extends from the appropriate base class (such as <xref:System.Windows.Controls.Page> for a page) and implements the <xref:System.Windows.Markup.IComponentConnector?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="37505-147"><xref:System.Windows.Markup.IComponentConnector> インターフェイスには、コンポーネントを初期化し、そのコンテンツ内の要素の名前とイベントを接続するメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="37505-147">The <xref:System.Windows.Markup.IComponentConnector> interface has methods to initialize a component and connect names and events on elements in its content.</span></span> <span data-ttu-id="37505-148">その結果、生成されたコード ファイルには、次のようなメソッドの実装が含まれます。</span><span class="sxs-lookup"><span data-stu-id="37505-148">Consequently, the generated code file has a method implementation like the following:</span></span>

```csharp
public void InitializeComponent() {
    if (_contentLoaded) {
        return;
    }
    _contentLoaded = true;
    System.Uri resourceLocater =
        new System.Uri(
            "window1.xaml",
            System.UriKind.RelativeOrAbsolute);
    System.Windows.Application.LoadComponent(this, resourceLocater);
}
```

```vb
Public Sub InitializeComponent() _

    If _contentLoaded Then
        Return
    End If

    _contentLoaded = True
    Dim resourceLocater As System.Uri = _
        New System.Uri("mainwindow.xaml", System.UriKind.Relative)

    System.Windows.Application.LoadComponent(Me, resourceLocater)

End Sub
```

<span data-ttu-id="37505-149">既定では、マークアップコンパイルは MSBuild エンジンと同じ <xref:System.AppDomain> で実行されます。</span><span class="sxs-lookup"><span data-stu-id="37505-149">By default, markup compilation runs in the same <xref:System.AppDomain> as the MSBuild engine.</span></span> <span data-ttu-id="37505-150">これにより、パフォーマンスが大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="37505-150">This provides significant performance gains.</span></span> <span data-ttu-id="37505-151">この動作は、`AlwaysCompileMarkupFilesInSeparateDomain` プロパティで切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="37505-151">This behavior can be toggled with the `AlwaysCompileMarkupFilesInSeparateDomain` property.</span></span> <span data-ttu-id="37505-152">これには、個別の <xref:System.AppDomain>をアンロードすることによって、すべての参照アセンブリをアンロードするという利点があります。</span><span class="sxs-lookup"><span data-stu-id="37505-152">This has the advantage of unloading all reference assemblies by unloading the separate <xref:System.AppDomain>.</span></span>

<a name="Pass_2_of_Markup_Compilation"></a>

### <a name="markup-compilationpass-2"></a><span data-ttu-id="37505-153">マークアップ コンパイル - パス 2</span><span class="sxs-lookup"><span data-stu-id="37505-153">Markup Compilation—Pass 2</span></span>

<span data-ttu-id="37505-154">マークアップ コンパイルのパス 1 ですべての [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ページがコンパイルされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="37505-154">Not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages are compiled at during pass 1 of markup compilation.</span></span> <span data-ttu-id="37505-155">ローカルで定義された型参照 (同じプロジェクト内の他のコードで定義された型の参照) を含む [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルは、この時点ではコンパイルから除外されます。</span><span class="sxs-lookup"><span data-stu-id="37505-155">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that have locally defined type references (references to types defined in code elsewhere in the same project) are exempt from compilation at this time.</span></span> <span data-ttu-id="37505-156">これは、ローカルで定義された型は、ソース内にのみ存在し、まだコンパイルされていないためです。</span><span class="sxs-lookup"><span data-stu-id="37505-156">This is because those locally defined types exist only in source and have not yet been compiled.</span></span> <span data-ttu-id="37505-157">これを判別するために、パーサーは、マークアップ ファイル内で `x:Name` などの項目を検索するヒューリスティックを使用します。</span><span class="sxs-lookup"><span data-stu-id="37505-157">In order to determine this, the parser uses heuristics that involve looking for items such as `x:Name` in the markup file.</span></span> <span data-ttu-id="37505-158">このようなインスタンスが見つかると、そのマークアップ ファイルのコンパイルは、コード ファイルがコンパイルされるまで延期され、その後、2 階目のマークアップ コンパイル パスで、これらのファイルが処理されます。</span><span class="sxs-lookup"><span data-stu-id="37505-158">When such an instance is found, that markup file’s compilation is postponed until the code files have been compiled, after which, the second markup compilation pass processes these files.</span></span>

<a name="File_Classification"></a>

### <a name="file-classification"></a><span data-ttu-id="37505-159">ファイルの分類</span><span class="sxs-lookup"><span data-stu-id="37505-159">File Classification</span></span>

<span data-ttu-id="37505-160">ビルド プロセスは、配置されるアプリケーション アセンブリに基づいて、出力ファイルを異なるリソース グループに分けます。</span><span class="sxs-lookup"><span data-stu-id="37505-160">The build process puts output files into different resource groups based on which application assembly they will be placed in.</span></span> <span data-ttu-id="37505-161">一般的なローカライズされないアプリケーションでは、`Resource` としてマークされたすべてのデータ ファイルは、メイン アセンブリ (実行可能ファイルまたはライブラリ) に配置されます。</span><span class="sxs-lookup"><span data-stu-id="37505-161">In a typical nonlocalized application, all data files marked as `Resource` are placed in the main assembly (executable or library).</span></span> <span data-ttu-id="37505-162">プロジェクトで `UICulture` が設定されると、コンパイル済みのすべての [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルと、言語固有として明示的にマークされたリソースは、サテライト リソース アセンブリに配置されます。</span><span class="sxs-lookup"><span data-stu-id="37505-162">When `UICulture` is set in the project, all compiled [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files and those resources specifically marked as language-specific are placed in the satellite resource assembly.</span></span> <span data-ttu-id="37505-163">さらに、言語に依存しないすべてのリソースは、メイン アセンブリに配置されます。</span><span class="sxs-lookup"><span data-stu-id="37505-163">Furthermore, all language-neutral resources are placed in the main assembly.</span></span> <span data-ttu-id="37505-164">ビルド プロセスのこの手順で、この決定が行われます。</span><span class="sxs-lookup"><span data-stu-id="37505-164">In this step of the build process, that determination is made.</span></span>

<span data-ttu-id="37505-165">プロジェクト ファイル内の `ApplicationDefinition`、`Page`、および `Resource` ビルト アクションは、`Localizable` メタデータで拡張でき (受け入れられる値は `true` と `false`)、これによって、ファイルが言語固有か、言語に依存しないかを指定します。</span><span class="sxs-lookup"><span data-stu-id="37505-165">The `ApplicationDefinition`, `Page`, and `Resource` build actions in the project file can be augmented with the `Localizable` metadata (acceptable values are `true` and `false`), which dictates whether the file is language-specific or language-neutral.</span></span>

<a name="Core_Compilation"></a>

### <a name="core-compilation"></a><span data-ttu-id="37505-166">コア コンパイル</span><span class="sxs-lookup"><span data-stu-id="37505-166">Core Compilation</span></span>

<span data-ttu-id="37505-167">コア コンパイル手順では、コード ファイルのコンパイルが行われます。</span><span class="sxs-lookup"><span data-stu-id="37505-167">The core compile step involves compilation of code files.</span></span> <span data-ttu-id="37505-168">これは Microsoft.CSharp.targets や Microsoft.VisualBasic.targets など、言語固有のターゲット ファイル内のロジックによって調整されます。</span><span class="sxs-lookup"><span data-stu-id="37505-168">This is orchestrated by logic in the language-specific targets files Microsoft.CSharp.targets and Microsoft.VisualBasic.targets.</span></span> <span data-ttu-id="37505-169">ヒューリスティックによってマークアップ コンパイラの 1 回のパスでは不十分であると判断されると、メイン アセンブリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="37505-169">If heuristics have determined that a single pass of the markup compiler is sufficient, then the main assembly is generated.</span></span> <span data-ttu-id="37505-170">ただし、プロジェクト内の 1 つ以上の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルにローカルで定義された型の参照が含まれている場合、一時的な .dll ファイルが生成され、これによってマークアップ コンパイルの 2 回目のパスが完了すると、最終的なアプリケーション アセンブリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="37505-170">However, if one or more [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files in the project have references to locally defined types, then a temporary .dll file is generated so the final application assemblies may be created after the second pass of markup compilation is complete.</span></span>

<a name="Manifest_generation"></a>

### <a name="manifest-generation"></a><span data-ttu-id="37505-171">マニフェストの生成</span><span class="sxs-lookup"><span data-stu-id="37505-171">Manifest Generation</span></span>

<span data-ttu-id="37505-172">ビルドプロセスの最後に、すべてのアプリケーションアセンブリとコンテンツファイルの準備が整ったら、アプリケーションの ClickOnce マニフェストが生成されます。</span><span class="sxs-lookup"><span data-stu-id="37505-172">At the end of the build process, after all the application assemblies and content files are ready, the ClickOnce manifests for the application are generated.</span></span>

<span data-ttu-id="37505-173">配置マニフェスト ファイルは、配置モデル (現在のバージョン、更新動作、およびパブリッシャーの ID とデジタル署名) を記述します。</span><span class="sxs-lookup"><span data-stu-id="37505-173">The deployment manifest file describes the deployment model: the current version, update behavior, and publisher identity along with digital signature.</span></span> <span data-ttu-id="37505-174">このマニフェストは、配置を処理する管理者が作成します。</span><span class="sxs-lookup"><span data-stu-id="37505-174">This manifest is intended to be authored by administrators who handle deployment.</span></span> <span data-ttu-id="37505-175">ファイル拡張子は、.xbap ([!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 用) と、インストール型アプリケーションを表す .application です。</span><span class="sxs-lookup"><span data-stu-id="37505-175">The file extension is .xbap (for [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]) and .application for installed applications.</span></span> <span data-ttu-id="37505-176">前者は `HostInBrowser` プロジェクト プロパティによって指定されるため、マニフェストはアプリケーションがブラウザーによってホストされることを識別します。</span><span class="sxs-lookup"><span data-stu-id="37505-176">The former is dictated by the `HostInBrowser` project property and as a result the manifest identifies the application as browser-hosted.</span></span>

<span data-ttu-id="37505-177">アプリケーション マニフェスト (.exe.manifest ファイル) は、アプリケーション アセンブリと依存ライブラリを記述し、アプリケーションに必要なアクセス許可をリストします。</span><span class="sxs-lookup"><span data-stu-id="37505-177">The application manifest (an .exe.manifest file) describes the application assemblies and dependent libraries and lists permissions required by the application.</span></span> <span data-ttu-id="37505-178">このファイルは、アプリケーション開発者が作成します。</span><span class="sxs-lookup"><span data-stu-id="37505-178">This file is intended to be authored by the application developer.</span></span> <span data-ttu-id="37505-179">ClickOnce アプリケーションを起動するために、ユーザーはアプリケーションの配置マニフェストファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="37505-179">In order to launch a ClickOnce application, a user opens the application's deployment manifest file.</span></span>

<span data-ttu-id="37505-180">これらのマニフェスト ファイルは、常に [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 用に作成されます。</span><span class="sxs-lookup"><span data-stu-id="37505-180">These manifest files are always created for [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].</span></span> <span data-ttu-id="37505-181">インストール型アプリケーションの場合、プロジェクト ファイル内で `GenerateManifests` プロパティの値が `true` に指定されない限り、作成されません。</span><span class="sxs-lookup"><span data-stu-id="37505-181">For installed applications, they are not created unless the `GenerateManifests` property is specified in the project file with value `true`.</span></span>

<span data-ttu-id="37505-182">一般的なインターネットゾーンのアプリケーションに割り当てられているアクセス許可に対して、<xref:System.Security.Permissions.WebBrowserPermission> と <xref:System.Security.Permissions.MediaPermission>の2つの追加のアクセス許可を取得 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] ます。</span><span class="sxs-lookup"><span data-stu-id="37505-182">[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] get two additional permissions over and above those permissions assigned to typical Internet zone applications: <xref:System.Security.Permissions.WebBrowserPermission> and <xref:System.Security.Permissions.MediaPermission>.</span></span> <span data-ttu-id="37505-183">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ビルド システムは、これらのアクセス許可をアプリケーション マニフェストで宣言します。</span><span class="sxs-lookup"><span data-stu-id="37505-183">The [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] build system declares those permissions in the application manifest.</span></span>

<a name="Incremental_Build_Support"></a>

## <a name="incremental-build-support"></a><span data-ttu-id="37505-184">インクリメンタル ビルドのサポート</span><span class="sxs-lookup"><span data-stu-id="37505-184">Incremental Build Support</span></span>

<span data-ttu-id="37505-185">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ビルド システムは、インクリメンタル ビルドをサポートします。</span><span class="sxs-lookup"><span data-stu-id="37505-185">The [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] build system provides support for incremental builds.</span></span> <span data-ttu-id="37505-186">これは、マークアップやコードに加えられた変更を検出し、変更の影響を受けるアイテムだけをコンパイルするという高度な機能です。</span><span class="sxs-lookup"><span data-stu-id="37505-186">It is fairly intelligent about detecting changes made to markup or code, and it compiles only those artifacts affected by the change.</span></span> <span data-ttu-id="37505-187">インクリメンタル ビルド メカニズムは、次のファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="37505-187">The incremental build mechanism uses the following files:</span></span>

- <span data-ttu-id="37505-188">$(*AssemblyName*)_MarkupCompiler.Cache ファイル。コンパイラの現在の状態を保持します。</span><span class="sxs-lookup"><span data-stu-id="37505-188">An $(*AssemblyName*)_MarkupCompiler.Cache file to maintain current compiler state.</span></span>

- <span data-ttu-id="37505-189">$(*AssemblyName*)_MarkupCompiler.lref ファイル。ローカルで定義された型への参照を持つ [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルをキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="37505-189">An $(*AssemblyName*)_MarkupCompiler.lref file to cache the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files with references to locally defined types.</span></span>

<span data-ttu-id="37505-190">インクリメンタル ビルドを制御する規則のセットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="37505-190">The following is a set of rules governing incremental build:</span></span>

- <span data-ttu-id="37505-191">ビルド システムが変更を検出する最小単位は、ファイルです。</span><span class="sxs-lookup"><span data-stu-id="37505-191">The file is the smallest unit at which the build system detects change.</span></span> <span data-ttu-id="37505-192">そのため、コード ファイルの場合、ビルド システムは、型が変更されたかどうか、またはコードが追加されたかどうかを検出できません。</span><span class="sxs-lookup"><span data-stu-id="37505-192">So, for a code file, the build system cannot tell if a type was changed or if code was added.</span></span> <span data-ttu-id="37505-193">プロジェクト ファイルの場合も同様です。</span><span class="sxs-lookup"><span data-stu-id="37505-193">The same holds for project files.</span></span>

- <span data-ttu-id="37505-194">インクリメンタル ビルドのメカニズムは、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ページがクラスを定義するのか、他のクラスを使用するのかを認識できなければなりません。</span><span class="sxs-lookup"><span data-stu-id="37505-194">The incremental build mechanism must be cognizant that a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page either defines a class or uses other classes.</span></span>

- <span data-ttu-id="37505-195">`Reference` エントリが変更された場合は、すべてのページを再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="37505-195">If `Reference` entries change, then recompile all pages.</span></span>

- <span data-ttu-id="37505-196">コード ファイルが変更された場合は、ローカルで定義された型の参照を含むすべてのページを再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="37505-196">If a code file changes, recompile all pages with locally defined type references.</span></span>

- <span data-ttu-id="37505-197">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルが変更された場合:</span><span class="sxs-lookup"><span data-stu-id="37505-197">If a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file changes:</span></span>

  - <span data-ttu-id="37505-198">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] がプロジェクトで `Page` として宣言されている場合: [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] にローカルで定義された型の参照が含まれていない場合は、その [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] とローカル参照を含むすべての [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ページを再コンパイルします。[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] にローカル参照が含まれる場合は、ローカル参照が含まれているすべての [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ページを再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="37505-198">If [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is declared as `Page` in the project: if the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] does not have locally defined type references, recompile that [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] plus all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages with local references; if the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has local references, recompile all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages with local references.</span></span>

  - <span data-ttu-id="37505-199">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] がプロジェクトの `ApplicationDefinition` として宣言されている場合: すべての [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ページを再コンパイルします (理由: 各 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] に、変更された可能性のある <xref:System.Windows.Application> 型への参照が含まれています)。</span><span class="sxs-lookup"><span data-stu-id="37505-199">If [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is declared as `ApplicationDefinition` in the project: recompile all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages (reason: each [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has reference to an <xref:System.Windows.Application> type that may have changed).</span></span>

- <span data-ttu-id="37505-200">プロジェクト ファイルがコード ファイルを [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルではなくアプリケーション定義として宣言している場合:</span><span class="sxs-lookup"><span data-stu-id="37505-200">If the project file declares a code file as application definition instead of a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file:</span></span>

  - <span data-ttu-id="37505-201">プロジェクト ファイル内の `ApplicationClassName` 値が変更されたかどうか (新しいアプリケーションの種類があるかどうか) を確認します。</span><span class="sxs-lookup"><span data-stu-id="37505-201">Check if the `ApplicationClassName` value in the project file has changed (is there a new application type?).</span></span> <span data-ttu-id="37505-202">変更されていた場合は、アプリケーション全体を再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="37505-202">If so, recompile the entire application.</span></span>

  - <span data-ttu-id="37505-203">変更されていなかった場合は、ローカル参照を含んでいるすべての [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ページを再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="37505-203">Otherwise, recompile all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages with local references.</span></span>

- <span data-ttu-id="37505-204">プロジェクト ファイルが変更された場合、上記のすべての規則を適用し、再コンパイルする必要があるものを確認します。</span><span class="sxs-lookup"><span data-stu-id="37505-204">If a project file changes: apply all preceding rules and see what needs to be recompiled.</span></span> <span data-ttu-id="37505-205">`AssemblyName`、`IntermediateOutputPath`、`RootNamespace`、および `HostInBrowser` プロパティが変更された場合は、再コンパイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="37505-205">Changes to the following properties trigger a complete recompile: `AssemblyName`, `IntermediateOutputPath`, `RootNamespace`, and `HostInBrowser`.</span></span>

<span data-ttu-id="37505-206">次のような再コンパイルのシナリオが考えられます。</span><span class="sxs-lookup"><span data-stu-id="37505-206">The following recompile scenarios are possible:</span></span>

- <span data-ttu-id="37505-207">アプリケーション全体が再コンパイルされる。</span><span class="sxs-lookup"><span data-stu-id="37505-207">The entire application is recompiled.</span></span>

- <span data-ttu-id="37505-208">ローカルで定義された方参照を含んでいる [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルのみが再コンパイルされる。</span><span class="sxs-lookup"><span data-stu-id="37505-208">Only those [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that have locally defined type references are recompiled.</span></span>

- <span data-ttu-id="37505-209">何も再コンパイルされない (プロジェクトに何も変更が加えられていない場合)。</span><span class="sxs-lookup"><span data-stu-id="37505-209">Nothing is recompiled (if nothing in the project has changed).</span></span>

## <a name="see-also"></a><span data-ttu-id="37505-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="37505-210">See also</span></span>

- [<span data-ttu-id="37505-211">WPF アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="37505-211">Deploying a WPF Application</span></span>](deploying-a-wpf-application-wpf.md)
- [<span data-ttu-id="37505-212">WPF MSBuild Reference (WPF MSBuild リファレンス)</span><span class="sxs-lookup"><span data-stu-id="37505-212">WPF MSBuild Reference</span></span>](/visualstudio/msbuild/wpf-msbuild-reference)
- [<span data-ttu-id="37505-213">WPF におけるパッケージの URI</span><span class="sxs-lookup"><span data-stu-id="37505-213">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)
- [<span data-ttu-id="37505-214">WPF アプリケーションのリソース ファイル、コンテンツ ファイル、およびデータ ファイル</span><span class="sxs-lookup"><span data-stu-id="37505-214">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
