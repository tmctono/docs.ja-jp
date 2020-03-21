---
title: アプリケーション開発
ms.date: 01/26/2018
helpviewer_keywords:
- WPF [WPF], about application development
- application development [WPF], about
ms.assetid: 2996ce5e-81e9-49ae-881b-952db3dd1b7e
ms.openlocfilehash: 5ff9f58b72982f79e70b80f60c10828c3b54e5bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186000"
---
# <a name="application-development"></a><span data-ttu-id="edd3d-102">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="edd3d-102">Application Development</span></span>
<a name="introduction"></a><span data-ttu-id="edd3d-103">Windows プレゼンテーションファンデーション (WPF) は、次の種類のアプリケーションを開発するために使用できるプレゼンテーション フレームワークです。</span><span class="sxs-lookup"><span data-stu-id="edd3d-103">Windows Presentation Foundation (WPF) is a presentation framework that can be used to develop the following types of applications:</span></span>  
  
- <span data-ttu-id="edd3d-104">スタンドアロン アプリケーション (クライアント コンピューターにインストールされ、クライアント コンピューターから実行される実行可能アセンブリとして構築された従来のスタイルの Windows アプリケーション)。</span><span class="sxs-lookup"><span data-stu-id="edd3d-104">Standalone Applications (traditional style Windows applications built as executable assemblies that are installed to and run from the client computer).</span></span>  
  
- <span data-ttu-id="edd3d-105">XAML ブラウザ アプリケーション (XBAPs) (実行可能アセンブリとして構築され、Internet Explorer や Mozilla Firefox などの Web ブラウザによってホストされるナビゲーション ページで構成されるアプリケーション)。</span><span class="sxs-lookup"><span data-stu-id="edd3d-105">XAML browser applications (XBAPs) (applications composed of navigation pages that are built as executable assemblies and hosted by Web browsers such as Microsoft Internet Explorer or Mozilla Firefox).</span></span>  
  
- <span data-ttu-id="edd3d-106">カスタム コントロール ライブラリ (再利用可能なコントロールを含む被実行可能アセンブリ)。</span><span class="sxs-lookup"><span data-stu-id="edd3d-106">Custom Control Libraries (non-executable assemblies containing reusable controls).</span></span>  
  
- <span data-ttu-id="edd3d-107">クラス ライブラリ (再利用可能なクラスを含む非実行可能アセンブリ)。</span><span class="sxs-lookup"><span data-stu-id="edd3d-107">Class Libraries (non-executable assemblies that contain reusable classes).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="edd3d-108">Windows サービスで WPF 型を使用するのは避けることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="edd3d-108">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="edd3d-109">Windows サービスでこれらの機能を使用すると、期待どおりの動作が得られない場合があります。</span><span class="sxs-lookup"><span data-stu-id="edd3d-109">If you attempt to use these features in a Windows service, they may not work as expected.</span></span>  
  
 <span data-ttu-id="edd3d-110">このアプリケーション セットをビルドするために、WPF はホストのサービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="edd3d-110">To build this set of applications, WPF implements a host of services.</span></span> <span data-ttu-id="edd3d-111">このトピックでは、これらのサービスの概要を説明し、詳細情報へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="edd3d-111">This topic provides an overview of these services and where to find more information.</span></span>  

<a name="Application_Management"></a>
## <a name="application-management"></a><span data-ttu-id="edd3d-112">アプリケーション管理</span><span class="sxs-lookup"><span data-stu-id="edd3d-112">Application Management</span></span>  
 <span data-ttu-id="edd3d-113">実行可能な WPF アプリケーションでは、一般的に、次のような機能のコア セットが必要です。</span><span class="sxs-lookup"><span data-stu-id="edd3d-113">Executable WPF applications commonly require a core set of functionality that includes the following:</span></span>  
  
- <span data-ttu-id="edd3d-114">共通アプリケーション インフラストラクチャを作成し、管理する (エントリ ポイント メソッドと、システム メッセージおよび入力メッセージを受け取るための Windows メッセージ ループの作成を含む)。</span><span class="sxs-lookup"><span data-stu-id="edd3d-114">Creating and managing common application infrastructure (including creating an entry point method and a Windows message loop to receive system and input messages).</span></span>  
  
- <span data-ttu-id="edd3d-115">アプリケーションの有効期間を追跡し、これと相互作用する。</span><span class="sxs-lookup"><span data-stu-id="edd3d-115">Tracking and interacting with the lifetime of an application.</span></span>  
  
- <span data-ttu-id="edd3d-116">コマンド ライン パラメーターを取得し、処理する。</span><span class="sxs-lookup"><span data-stu-id="edd3d-116">Retrieving and processing command-line parameters.</span></span>  
  
- <span data-ttu-id="edd3d-117">アプリケーション スコープのプロパティと [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] リソースを共有する。</span><span class="sxs-lookup"><span data-stu-id="edd3d-117">Sharing application-scope properties and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] resources.</span></span>  
  
- <span data-ttu-id="edd3d-118">未処理の例外を検出し、処理する。</span><span class="sxs-lookup"><span data-stu-id="edd3d-118">Detecting and processing unhandled exceptions.</span></span>  
  
- <span data-ttu-id="edd3d-119">終了コードを返す。</span><span class="sxs-lookup"><span data-stu-id="edd3d-119">Returning exit codes.</span></span>  
  
- <span data-ttu-id="edd3d-120">スタンドアロン アプリケーションのウィンドウを管理する。</span><span class="sxs-lookup"><span data-stu-id="edd3d-120">Managing windows in standalone applications.</span></span>  
  
- <span data-ttu-id="edd3d-121">XAML ブラウザー アプリケーション (XAPS) でのナビゲーションの追跡、およびナビゲーション ウィンドウとフレームを含むスタンドアロン アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="edd3d-121">Tracking navigation in XAML browser applications (XBAPs), and standalone applications with navigation windows and frames.</span></span>  
  
 <span data-ttu-id="edd3d-122">これらの機能は <xref:System.Windows.Application> クラスで実装します。このクラスをアプリケーションに追加するには、*アプリケーション定義*を使用します。</span><span class="sxs-lookup"><span data-stu-id="edd3d-122">These capabilities are implemented by the <xref:System.Windows.Application> class, which you add to your applications using an *application definition*.</span></span>  
  
 <span data-ttu-id="edd3d-123">詳細については、「[アプリケーション管理の概要](application-management-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edd3d-123">For more information, see [Application Management Overview](application-management-overview.md).</span></span>  
  
<a name="WPF_Application_Resource__Content__and_Data_Files"></a>
## <a name="wpf-application-resource-content-and-data-files"></a><span data-ttu-id="edd3d-124">WPF アプリケーションのリソース ファイル、コンテンツ ファイル、およびデータ ファイル</span><span class="sxs-lookup"><span data-stu-id="edd3d-124">WPF Application Resource, Content, and Data Files</span></span>  
 <span data-ttu-id="edd3d-125">WPF では、Microsoft .NET Framework の埋め込みリソースのコア サポートが拡張され、実行可能でないデータ ファイル (リソース、コンテンツ、データ) の 3 種類がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="edd3d-125">WPF extends the core support in the Microsoft .NET Framework for embedded resources with support for three kinds of non-executable data files: resource, content, and data.</span></span> <span data-ttu-id="edd3d-126">詳細については、「[WPF アプリケーションのリソース、コンテンツ ファイル、およびデータ ファイル](wpf-application-resource-content-and-data-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edd3d-126">For more information, see [WPF Application Resource, Content, and Data Files](wpf-application-resource-content-and-data-files.md).</span></span>  
  
 <span data-ttu-id="edd3d-127">WPF の非実行可能データ ファイルのサポートの重要なコンポーネントは、一意の URI を使用してそれらを識別し、読み込む機能です。</span><span class="sxs-lookup"><span data-stu-id="edd3d-127">A key component of the support for WPF non-executable data files is the ability to identify and load them using a unique URI.</span></span> <span data-ttu-id="edd3d-128">詳細については、「[WPF におけるパック URI](pack-uris-in-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edd3d-128">For more information, see [Pack URIs in WPF](pack-uris-in-wpf.md).</span></span>  
  
<a name="Windows_and_Dialog_Boxes"></a>
## <a name="windows-and-dialog-boxes"></a><span data-ttu-id="edd3d-129">ウィンドウとダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="edd3d-129">Windows and Dialog Boxes</span></span>  
 <span data-ttu-id="edd3d-130">ユーザーは、ウィンドウを使用して WPF スタンドアロン アプリケーションと対話します。</span><span class="sxs-lookup"><span data-stu-id="edd3d-130">Users interact with WPF standalone applications through windows.</span></span> <span data-ttu-id="edd3d-131">ウィンドウの目的は、アプリケーションのコンテンツをホストし、コンテンツとやり取りするためにユーザーが利用できるアプリケーション機能を公開することです。</span><span class="sxs-lookup"><span data-stu-id="edd3d-131">The purpose of a window is to host application content and expose application functionality that usually allows users to interact with the content.</span></span> <span data-ttu-id="edd3d-132">WPF では、ウィンドウはクラスによってカプセル<xref:System.Windows.Window>化され、次の機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="edd3d-132">In WPF, windows are encapsulated by the <xref:System.Windows.Window> class, which supports:</span></span>  
  
- <span data-ttu-id="edd3d-133">ウィンドウを作成し、表示する。</span><span class="sxs-lookup"><span data-stu-id="edd3d-133">Creating and showing windows.</span></span>  
  
- <span data-ttu-id="edd3d-134">所有者と所有ウィンドウの関係を確立する。</span><span class="sxs-lookup"><span data-stu-id="edd3d-134">Establishing owner/owned window relationships.</span></span>  
  
- <span data-ttu-id="edd3d-135">ウィンドウの外観を構成する (サイズ、位置、アイコン、タイトル バーのテキスト、境界など)。</span><span class="sxs-lookup"><span data-stu-id="edd3d-135">Configuring window appearance (for example, size, location, icons, title bar text, border).</span></span>  
  
- <span data-ttu-id="edd3d-136">ウィンドウの有効期間を追跡し、これと相互作用する。</span><span class="sxs-lookup"><span data-stu-id="edd3d-136">Tracking and interacting with the lifetime of a window.</span></span>  
  
 <span data-ttu-id="edd3d-137">詳細については、「[WPF ウィンドウの概要](wpf-windows-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edd3d-137">For more information, see [WPF Windows Overview](wpf-windows-overview.md).</span></span>  
  
 <span data-ttu-id="edd3d-138"><xref:System.Windows.Window> では、ダイアログ ボックスと呼ばれる特別な種類のウィンドウを作成できます。</span><span class="sxs-lookup"><span data-stu-id="edd3d-138"><xref:System.Windows.Window> supports the ability to create a special type of window known as a dialog box.</span></span> <span data-ttu-id="edd3d-139">モーダル ダイアログ ボックスとモードレス ダイアログ ボックスの両方の種類のダイアログ ボックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="edd3d-139">Both modal and modeless types of dialog boxes can be created.</span></span>  
  
 <span data-ttu-id="edd3d-140">WPF では、アプリケーション間で再利用性と一貫したユーザー エクスペリエンスを実現するために、WINDOWS の一般的なダイアログ ボックス<xref:Microsoft.Win32.OpenFileDialog> <xref:Microsoft.Win32.SaveFileDialog>、、<xref:System.Windows.Controls.PrintDialog>および 3 つのダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="edd3d-140">For convenience, and the benefits of reusability and a consistent user experience across applications, WPF exposes three of the common Windows dialog boxes: <xref:Microsoft.Win32.OpenFileDialog>, <xref:Microsoft.Win32.SaveFileDialog>, and <xref:System.Windows.Controls.PrintDialog>.</span></span>  
  
 <span data-ttu-id="edd3d-141">メッセージ ボックスは、重要な情報をテキストでユーザーに表示し、単純な [はい]、[いいえ]、[OK]、[キャンセル] の応答を求めるために使用する特別なダイアログ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="edd3d-141">A message box is a special type of dialog box for showing important textual information to users, and for asking simple Yes/No/OK/Cancel questions.</span></span> <span data-ttu-id="edd3d-142">メッセージ ボックスを作成および表示するには <xref:System.Windows.MessageBox> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="edd3d-142">You use the <xref:System.Windows.MessageBox> class to create and show message boxes.</span></span>  
  
 <span data-ttu-id="edd3d-143">詳細については、「[ダイアログ ボックスの概要](dialog-boxes-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edd3d-143">For more information, see [Dialog Boxes Overview](dialog-boxes-overview.md).</span></span>  
  
<a name="Navigation"></a>
## <a name="navigation"></a><span data-ttu-id="edd3d-144">「ナビゲーション」</span><span class="sxs-lookup"><span data-stu-id="edd3d-144">Navigation</span></span>  
 <span data-ttu-id="edd3d-145">WPF では、ページ ( )<xref:System.Windows.Controls.Page>とハイパーリンク (<xref:System.Windows.Documents.Hyperlink>) を使用した Web スタイルのナビゲーションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="edd3d-145">WPF supports Web-style navigation using pages (<xref:System.Windows.Controls.Page>) and hyperlinks (<xref:System.Windows.Documents.Hyperlink>).</span></span> <span data-ttu-id="edd3d-146">ナビゲーションは、次のようなさまざまな方法で実装できます。</span><span class="sxs-lookup"><span data-stu-id="edd3d-146">Navigation can be implemented in a variety of ways that include the following:</span></span>  
  
- <span data-ttu-id="edd3d-147">Web ブラウザーでホストされるスタンドアロンのページ。</span><span class="sxs-lookup"><span data-stu-id="edd3d-147">Standalone pages that are hosted in a Web browser.</span></span>  
  
- <span data-ttu-id="edd3d-148">Web ブラウザーでホストされる XBAP にコンパイルされたページ。</span><span class="sxs-lookup"><span data-stu-id="edd3d-148">Pages compiled into an XBAP that is hosted in a Web browser.</span></span>  
  
- <span data-ttu-id="edd3d-149">スタンドアロン アプリケーションにコンパイルされ、ナビゲーション ウィンドウ (<xref:System.Windows.Navigation.NavigationWindow>) によってホストされるページ。</span><span class="sxs-lookup"><span data-stu-id="edd3d-149">Pages compiled into a standalone application and hosted by a navigation window (<xref:System.Windows.Navigation.NavigationWindow>).</span></span>  
  
- <span data-ttu-id="edd3d-150">フレーム (<xref:System.Windows.Controls.Frame>) によってホストされるページで、スタンドアロン ページでホストされている場合や、XBAP またはスタンドアロン アプリケーションにコンパイルされたページ。</span><span class="sxs-lookup"><span data-stu-id="edd3d-150">Pages that are hosted by a frame (<xref:System.Windows.Controls.Frame>), which may be hosted in a standalone page, or a page compiled into either an XBAP or a standalone application.</span></span>  
  
 <span data-ttu-id="edd3d-151">ナビゲーションを容易にするために、WPF は次の機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="edd3d-151">To facilitate navigation, WPF implements the following:</span></span>  
  
- <span data-ttu-id="edd3d-152"><xref:System.Windows.Navigation.NavigationService>、アプリケーション内ナビゲーションをサポートするために 、 、<xref:System.Windows.Controls.Frame><xref:System.Windows.Navigation.NavigationWindow>および XBaAp によって使用されるナビゲーション要求を処理するための共有ナビゲーション エンジン。</span><span class="sxs-lookup"><span data-stu-id="edd3d-152"><xref:System.Windows.Navigation.NavigationService>, the shared navigation engine for processing navigation requests that is used by <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>, and XBAPs to support intra-application navigation.</span></span>  
  
- <span data-ttu-id="edd3d-153">ナビゲーションを開始するためのナビゲーション メソッド。</span><span class="sxs-lookup"><span data-stu-id="edd3d-153">Navigation methods to initiate navigation.</span></span>  
  
- <span data-ttu-id="edd3d-154">ナビゲーションの有効期間を追跡し、これと相互作用するためのナビゲーション イベント。</span><span class="sxs-lookup"><span data-stu-id="edd3d-154">Navigation events to track and interact with navigation lifetime.</span></span>  
  
- <span data-ttu-id="edd3d-155">履歴を使用した前方や後方へのナビゲーションの記憶。履歴は、調べたり、操作したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="edd3d-155">Remembering back and forward navigation using a journal, which can also be inspected and manipulated.</span></span>  
  
 <span data-ttu-id="edd3d-156">詳細については、「[ナビゲーションの概要](navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edd3d-156">For information, see [Navigation Overview](navigation-overview.md).</span></span>  
  
 <span data-ttu-id="edd3d-157">WPF では、構造化ナビゲーションと呼ばれる特殊な種類のナビゲーションもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="edd3d-157">WPF also supports a special type of navigation known as structured navigation.</span></span> <span data-ttu-id="edd3d-158">構造化ナビゲーションを使用すると、呼び出し元関数との一貫性が保たれた、構造化されて予測可能な形式でデータを返す 1 つ以上のページを呼び出す事ができます。</span><span class="sxs-lookup"><span data-stu-id="edd3d-158">Structured navigation can be used to call one or more pages that return data in a structured and predictable way that is consistent with calling functions.</span></span> <span data-ttu-id="edd3d-159">この機能は <xref:System.Windows.Navigation.PageFunction%601> クラスに依存します。このクラスの詳細については、「[構造化ナビゲーションの概要](structured-navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edd3d-159">This capability depends on the <xref:System.Windows.Navigation.PageFunction%601> class, which is described further in [Structured Navigation Overview](structured-navigation-overview.md).</span></span> <span data-ttu-id="edd3d-160">また、<xref:System.Windows.Navigation.PageFunction%601> を使用すると、複雑なナビゲーション トポロジを簡単に作成することもできます。詳細については、「[ナビゲーション トポロジの概要](navigation-topologies-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edd3d-160"><xref:System.Windows.Navigation.PageFunction%601> also serves to simplify the creation of complex navigation topologies, which are described in [Navigation Topologies Overview](navigation-topologies-overview.md).</span></span>  
  
<a name="Hosting"></a>
## <a name="hosting"></a><span data-ttu-id="edd3d-161">Hosting</span><span class="sxs-lookup"><span data-stu-id="edd3d-161">Hosting</span></span>  
 <span data-ttu-id="edd3d-162">XBAPs は、インターネット エクスプローラまたは Firefox でホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="edd3d-162">XBAPs can be hosted in Microsoft Internet Explorer or Firefox.</span></span> <span data-ttu-id="edd3d-163">ホストのモデルによって考慮事項や制約が異なります。詳細については、「[ホスティング](hosting-wpf-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edd3d-163">Each hosting model has its own set of considerations and constraints that are covered in [Hosting](hosting-wpf-applications.md).</span></span>  
  
<a name="Build_and_Deploy"></a>
## <a name="build-and-deploy"></a><span data-ttu-id="edd3d-164">ビルドと配置</span><span class="sxs-lookup"><span data-stu-id="edd3d-164">Build and Deploy</span></span>  
 <span data-ttu-id="edd3d-165">単純な WPF アプリケーションは、コマンド ライン コンパイラを使用してコマンド プロンプトからビルドできますが、WPF は Visual Studio と統合して、開発とビルド プロセスを簡略化する追加のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="edd3d-165">Although simple WPF applications can be built from a command prompt using command-line compilers, WPF integrates with Visual Studio to provide additional support that simplified the development and build process.</span></span> <span data-ttu-id="edd3d-166">詳細については、「[WPF アプリケーションのビルド](building-a-wpf-application-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edd3d-166">For more information, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>  
  
 <span data-ttu-id="edd3d-167">ビルドするアプリケーションの種類によって、選択する配置オプションが異なります。</span><span class="sxs-lookup"><span data-stu-id="edd3d-167">Depending on the type of application you build, there are one or more deployment options to choose from.</span></span> <span data-ttu-id="edd3d-168">詳細については、「[WPF アプリケーションの配置](deploying-a-wpf-application-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edd3d-168">For more information, see [Deploying a WPF Application](deploying-a-wpf-application-wpf.md).</span></span>  
  
<a name="related_topics"></a>
## <a name="related-topics"></a><span data-ttu-id="edd3d-169">関連トピック</span><span class="sxs-lookup"><span data-stu-id="edd3d-169">Related Topics</span></span>  
  
|<span data-ttu-id="edd3d-170">タイトル</span><span class="sxs-lookup"><span data-stu-id="edd3d-170">Title</span></span>|<span data-ttu-id="edd3d-171">説明</span><span class="sxs-lookup"><span data-stu-id="edd3d-171">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="edd3d-172">アプリケーション管理の概要</span><span class="sxs-lookup"><span data-stu-id="edd3d-172">Application Management Overview</span></span>](application-management-overview.md)|<span data-ttu-id="edd3d-173">アプリケーションの有効期間、ウィンドウ、アプリケーション リソース、ナビゲーションの管理など、<xref:System.Windows.Application> クラスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="edd3d-173">Provides an overview of the <xref:System.Windows.Application> class including managing application lifetime, windows, application resources, and navigation.</span></span>|  
|[<span data-ttu-id="edd3d-174">WPF のウィンドウ</span><span class="sxs-lookup"><span data-stu-id="edd3d-174">Windows in WPF</span></span>](windows-in-wpf-applications.md)|<span data-ttu-id="edd3d-175"><xref:System.Windows.Window> クラスおよびダイアログ ボックスの使い方など、アプリケーション内のウィンドウ管理の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="edd3d-175">Provides details of managing windows in your application including how to use the <xref:System.Windows.Window> class and dialog boxes.</span></span>|  
|[<span data-ttu-id="edd3d-176">ナビゲーションの概要</span><span class="sxs-lookup"><span data-stu-id="edd3d-176">Navigation Overview</span></span>](navigation-overview.md)|<span data-ttu-id="edd3d-177">アプリケーション内のページ間でのナビゲーション管理の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="edd3d-177">Provides an overview of managing navigation between pages of your application.</span></span>|  
|[<span data-ttu-id="edd3d-178">ホスティング</span><span class="sxs-lookup"><span data-stu-id="edd3d-178">Hosting</span></span>](hosting-wpf-applications.md)|<span data-ttu-id="edd3d-179">XAML ブラウザー アプリケーション (XAAP) の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="edd3d-179">Provides an overview of XAML browser applications (XBAPs).</span></span>|  
|[<span data-ttu-id="edd3d-180">ビルドと配置</span><span class="sxs-lookup"><span data-stu-id="edd3d-180">Build and Deploy</span></span>](building-and-deploying-wpf-applications.md)|<span data-ttu-id="edd3d-181">WPF アプリケーションをビルドして配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="edd3d-181">Describes how to build and deploy your WPF application.</span></span>|  
|[<span data-ttu-id="edd3d-182">Visual Studio での WPF の概要</span><span class="sxs-lookup"><span data-stu-id="edd3d-182">Introduction to WPF in Visual Studio</span></span>](../getting-started/introduction-to-wpf-in-vs.md)|<span data-ttu-id="edd3d-183">WPF の主な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="edd3d-183">Describes the main features of WPF.</span></span>|  
|[<span data-ttu-id="edd3d-184">チュートリアル: 初めての WPF デスクトップ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="edd3d-184">Walkthrough: My first WPF desktop application</span></span>](../getting-started/walkthrough-my-first-wpf-desktop-application.md)|<span data-ttu-id="edd3d-185">ページ ナビゲーション、レイアウト、コントロール、イメージ、スタイル、バインディングを使用する WPF アプリケーションの作成方法を示すチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="edd3d-185">A walkthrough that shows how to create a WPF application using page navigation, layout, controls, images, styles, and binding.</span></span>|
