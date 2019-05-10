---
title: アプリケーション開発
ms.date: 01/26/2018
helpviewer_keywords:
- WPF [WPF], about application development
- application development [WPF], about
ms.assetid: 2996ce5e-81e9-49ae-881b-952db3dd1b7e
ms.openlocfilehash: 56dbdfd70dd335d32224d11c31a5e64abd3124af
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64655463"
---
# <a name="application-development"></a><span data-ttu-id="ec580-102">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="ec580-102">Application Development</span></span>
<a name="introduction"></a> <span data-ttu-id="ec580-103">Windows Presentation Foundation (WPF) とは、次の種類のアプリケーションの開発に使用できるプレゼンテーション フレームワークです。</span><span class="sxs-lookup"><span data-stu-id="ec580-103">Windows Presentation Foundation (WPF) is a presentation framework that can be used to develop the following types of applications:</span></span>  
  
- <span data-ttu-id="ec580-104">スタンドアロン アプリケーション (クライアント コンピューターにインストールし、そこから実行できる実行可能アセンブリとしてビルドされた従来スタイルの [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] アプリケーション)。</span><span class="sxs-lookup"><span data-stu-id="ec580-104">Standalone Applications (traditional style [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] applications built as executable assemblies that are installed to and run from the client computer).</span></span>  
  
- [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] <span data-ttu-id="ec580-105">([!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] や Mozilla Firefox などの Web ブラウザーによってホストされ、実行可能アセンブリとしてビルドされたナビゲーション ページで構成されるアプリケーション)。</span><span class="sxs-lookup"><span data-stu-id="ec580-105">(applications composed of navigation pages that are built as executable assemblies and hosted by Web browsers such as [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] or Mozilla Firefox).</span></span>  
  
- <span data-ttu-id="ec580-106">カスタム コントロール ライブラリ (再利用可能なコントロールを含む被実行可能アセンブリ)。</span><span class="sxs-lookup"><span data-stu-id="ec580-106">Custom Control Libraries (non-executable assemblies containing reusable controls).</span></span>  
  
- <span data-ttu-id="ec580-107">クラス ライブラリ (再利用可能なクラスを含む非実行可能アセンブリ)。</span><span class="sxs-lookup"><span data-stu-id="ec580-107">Class Libraries (non-executable assemblies that contain reusable classes).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec580-108">Windows サービスで WPF 型を使用するのは避けることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ec580-108">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="ec580-109">Windows サービスでこれらの機能を使用すると、期待どおりの動作が得られない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec580-109">If you attempt to use these features in a Windows service, they may not work as expected.</span></span>  
  
 <span data-ttu-id="ec580-110">このような一連のアプリケーションをビルドするために、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] は多数のサービスを実装しています。</span><span class="sxs-lookup"><span data-stu-id="ec580-110">To build this set of applications, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] implements a host of services.</span></span> <span data-ttu-id="ec580-111">このトピックでは、これらのサービスの概要を説明し、詳細情報へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="ec580-111">This topic provides an overview of these services and where to find more information.</span></span>  

<a name="Application_Management"></a>   
## <a name="application-management"></a><span data-ttu-id="ec580-112">アプリケーション構成の管理</span><span class="sxs-lookup"><span data-stu-id="ec580-112">Application Management</span></span>  
 <span data-ttu-id="ec580-113">実行可能 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] アプリケーションは、一般に次のコアな機能セットを必要とします。</span><span class="sxs-lookup"><span data-stu-id="ec580-113">Executable [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications commonly require a core set of functionality that includes the following:</span></span>  
  
- <span data-ttu-id="ec580-114">共通アプリケーション インフラストラクチャを作成し、管理する (エントリ ポイント メソッドと、システム メッセージおよび入力メッセージを受け取るための Windows メッセージ ループの作成を含む)。</span><span class="sxs-lookup"><span data-stu-id="ec580-114">Creating and managing common application infrastructure (including creating an entry point method and a Windows message loop to receive system and input messages).</span></span>  
  
- <span data-ttu-id="ec580-115">アプリケーションの有効期間を追跡し、これと相互作用する。</span><span class="sxs-lookup"><span data-stu-id="ec580-115">Tracking and interacting with the lifetime of an application.</span></span>  
  
- <span data-ttu-id="ec580-116">コマンド ライン パラメーターを取得し、処理する。</span><span class="sxs-lookup"><span data-stu-id="ec580-116">Retrieving and processing command-line parameters.</span></span>  
  
- <span data-ttu-id="ec580-117">アプリケーション スコープのプロパティと [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] リソースを共有する。</span><span class="sxs-lookup"><span data-stu-id="ec580-117">Sharing application-scope properties and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] resources.</span></span>  
  
- <span data-ttu-id="ec580-118">未処理の例外を検出し、処理する。</span><span class="sxs-lookup"><span data-stu-id="ec580-118">Detecting and processing unhandled exceptions.</span></span>  
  
- <span data-ttu-id="ec580-119">終了コードを返す。</span><span class="sxs-lookup"><span data-stu-id="ec580-119">Returning exit codes.</span></span>  
  
- <span data-ttu-id="ec580-120">スタンドアロン アプリケーションのウィンドウを管理する。</span><span class="sxs-lookup"><span data-stu-id="ec580-120">Managing windows in standalone applications.</span></span>  
  
- <span data-ttu-id="ec580-121">[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] や、ナビゲーション ウィンドウとフレームを持つスタンドアロン アプリケーションで、ナビゲーションを追跡する。</span><span class="sxs-lookup"><span data-stu-id="ec580-121">Tracking navigation in [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)], and standalone applications with navigation windows and frames.</span></span>  
  
 <span data-ttu-id="ec580-122">これらの機能は <xref:System.Windows.Application> クラスで実装します。このクラスをアプリケーションに追加するには、*アプリケーション定義*を使用します。</span><span class="sxs-lookup"><span data-stu-id="ec580-122">These capabilities are implemented by the <xref:System.Windows.Application> class, which you add to your applications using an *application definition*.</span></span>  
  
 <span data-ttu-id="ec580-123">詳細については、「[アプリケーション管理の概要](application-management-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec580-123">For more information, see [Application Management Overview](application-management-overview.md).</span></span>  
  
<a name="WPF_Application_Resource__Content__and_Data_Files"></a>   
## <a name="wpf-application-resource-content-and-data-files"></a><span data-ttu-id="ec580-124">WPF アプリケーションのリソース ファイル、コンテンツ ファイル、およびデータ ファイル</span><span class="sxs-lookup"><span data-stu-id="ec580-124">WPF Application Resource, Content, and Data Files</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="ec580-125">データの非実行可能ファイルの 3 種類のサポートの埋め込みリソースの Microsoft .NET framework core のサポートを拡張します。 リソース、コンテンツ、およびデータ。</span><span class="sxs-lookup"><span data-stu-id="ec580-125">extends the core support in the Microsoft .NET Framework for embedded resources with support for three kinds of non-executable data files: resource, content, and data.</span></span> <span data-ttu-id="ec580-126">詳細については、「[WPF アプリケーションのリソース、コンテンツ ファイル、およびデータ ファイル](wpf-application-resource-content-and-data-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec580-126">For more information, see [WPF Application Resource, Content, and Data Files](wpf-application-resource-content-and-data-files.md).</span></span>  
  
 <span data-ttu-id="ec580-127">WPF 非実行可能データ ファイル サポートの重要なコンポーネントは、一意の [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] を使用して、これらのファイルを識別し、読み込む機能です。</span><span class="sxs-lookup"><span data-stu-id="ec580-127">A key component of the support for WPF non-executable data files is the ability to identify and load them using a unique [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span> <span data-ttu-id="ec580-128">詳細については、「[WPF におけるパック URI](pack-uris-in-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec580-128">For more information, see [Pack URIs in WPF](pack-uris-in-wpf.md).</span></span>  
  
<a name="Windows_and_Dialog_Boxes"></a>   
## <a name="windows-and-dialog-boxes"></a><span data-ttu-id="ec580-129">ウィンドウとダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="ec580-129">Windows and Dialog Boxes</span></span>  
 <span data-ttu-id="ec580-130">ユーザーは、ウィンドウをとおして、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] スタンドアロン アプリケーションとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="ec580-130">Users interact with [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] standalone applications through windows.</span></span> <span data-ttu-id="ec580-131">ウィンドウの目的は、アプリケーションのコンテンツをホストし、コンテンツとやり取りするためにユーザーが利用できるアプリケーション機能を公開することです。</span><span class="sxs-lookup"><span data-stu-id="ec580-131">The purpose of a window is to host application content and expose application functionality that usually allows users to interact with the content.</span></span> <span data-ttu-id="ec580-132">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] では、ウィンドウは <xref:System.Windows.Window> クラスにカプセル化されます。このクラスは、次の機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="ec580-132">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], windows are encapsulated by the <xref:System.Windows.Window> class, which supports:</span></span>  
  
- <span data-ttu-id="ec580-133">ウィンドウを作成し、表示する。</span><span class="sxs-lookup"><span data-stu-id="ec580-133">Creating and showing windows.</span></span>  
  
- <span data-ttu-id="ec580-134">所有者と所有ウィンドウの関係を確立する。</span><span class="sxs-lookup"><span data-stu-id="ec580-134">Establishing owner/owned window relationships.</span></span>  
  
- <span data-ttu-id="ec580-135">ウィンドウの外観を構成する (サイズ、位置、アイコン、タイトル バーのテキスト、境界など)。</span><span class="sxs-lookup"><span data-stu-id="ec580-135">Configuring window appearance (for example, size, location, icons, title bar text, border).</span></span>  
  
- <span data-ttu-id="ec580-136">ウィンドウの有効期間を追跡し、これと相互作用する。</span><span class="sxs-lookup"><span data-stu-id="ec580-136">Tracking and interacting with the lifetime of a window.</span></span>  
  
 <span data-ttu-id="ec580-137">詳細については、「[WPF ウィンドウの概要](wpf-windows-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec580-137">For more information, see [WPF Windows Overview](wpf-windows-overview.md).</span></span>  
  
 <span data-ttu-id="ec580-138"><xref:System.Windows.Window> では、ダイアログ ボックスと呼ばれる特別な種類のウィンドウを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ec580-138"><xref:System.Windows.Window> supports the ability to create a special type of window known as a dialog box.</span></span> <span data-ttu-id="ec580-139">モーダル ダイアログ ボックスとモードレス ダイアログ ボックスの両方の種類のダイアログ ボックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ec580-139">Both modal and modeless types of dialog boxes can be created.</span></span>  
  
 <span data-ttu-id="ec580-140">再利用性と、アプリケーション間で一貫したユーザー エクスペリエンスのメリットを都合に合わせて、 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 3 つの Windows のコモン ダイアログ ボックスを公開します: <xref:Microsoft.Win32.OpenFileDialog>、 <xref:Microsoft.Win32.SaveFileDialog>、および<xref:System.Windows.Controls.PrintDialog>します。</span><span class="sxs-lookup"><span data-stu-id="ec580-140">For convenience, and the benefits of reusability and a consistent user experience across applications, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] exposes three of the common Windows dialog boxes: <xref:Microsoft.Win32.OpenFileDialog>, <xref:Microsoft.Win32.SaveFileDialog>, and <xref:System.Windows.Controls.PrintDialog>.</span></span>  
  
 <span data-ttu-id="ec580-141">メッセージ ボックスは、重要な情報をテキストでユーザーに表示し、単純な [はい]、[いいえ]、[OK]、[キャンセル] の応答を求めるために使用する特別なダイアログ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="ec580-141">A message box is a special type of dialog box for showing important textual information to users, and for asking simple Yes/No/OK/Cancel questions.</span></span> <span data-ttu-id="ec580-142">メッセージ ボックスを作成および表示するには <xref:System.Windows.MessageBox> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="ec580-142">You use the <xref:System.Windows.MessageBox> class to create and show message boxes.</span></span>  
  
 <span data-ttu-id="ec580-143">詳細については、「[ダイアログ ボックスの概要](dialog-boxes-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec580-143">For more information, see [Dialog Boxes Overview](dialog-boxes-overview.md).</span></span>  
  
<a name="Navigation"></a>   
## <a name="navigation"></a><span data-ttu-id="ec580-144">ナビゲーション</span><span class="sxs-lookup"><span data-stu-id="ec580-144">Navigation</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="ec580-145">では、ページ (<xref:System.Windows.Controls.Page>) およびハイパーリンク (<xref:System.Windows.Documents.Hyperlink>) を使用した Web スタイルのナビゲーションがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ec580-145">supports Web-style navigation using pages (<xref:System.Windows.Controls.Page>) and hyperlinks (<xref:System.Windows.Documents.Hyperlink>).</span></span> <span data-ttu-id="ec580-146">ナビゲーションは、次のようなさまざまな方法で実装できます。</span><span class="sxs-lookup"><span data-stu-id="ec580-146">Navigation can be implemented in a variety of ways that include the following:</span></span>  
  
- <span data-ttu-id="ec580-147">Web ブラウザーでホストされるスタンドアロンのページ。</span><span class="sxs-lookup"><span data-stu-id="ec580-147">Standalone pages that are hosted in a Web browser.</span></span>  
  
- <span data-ttu-id="ec580-148">Web ブラウザーでホストされる [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] にコンパイルされるページ。</span><span class="sxs-lookup"><span data-stu-id="ec580-148">Pages compiled into an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that is hosted in a Web browser.</span></span>  
  
- <span data-ttu-id="ec580-149">スタンドアロン アプリケーションにコンパイルされ、ナビゲーション ウィンドウ (<xref:System.Windows.Navigation.NavigationWindow>) によってホストされるページ。</span><span class="sxs-lookup"><span data-stu-id="ec580-149">Pages compiled into a standalone application and hosted by a navigation window (<xref:System.Windows.Navigation.NavigationWindow>).</span></span>  
  
- <span data-ttu-id="ec580-150">フレーム (<xref:System.Windows.Controls.Frame>) によってホストされるページ。フレームは、スタンドアロン ページか、[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] またはスタンドアロン アプリケーションにコンパイルされたページでホストできます。</span><span class="sxs-lookup"><span data-stu-id="ec580-150">Pages that are hosted by a frame (<xref:System.Windows.Controls.Frame>), which may be hosted in a standalone page, or a page compiled into either an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] or a standalone application.</span></span>  
  
 <span data-ttu-id="ec580-151">ナビゲーションに役立つように、次の機能が [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] に実装されます。</span><span class="sxs-lookup"><span data-stu-id="ec580-151">To facilitate navigation, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] implements the following:</span></span>  
  
- <span data-ttu-id="ec580-152">ナビゲーション要求を処理する共有ナビゲーション エンジンである <xref:System.Windows.Navigation.NavigationService>。このエンジンは <xref:System.Windows.Controls.Frame>、<xref:System.Windows.Navigation.NavigationWindow>、[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] で使用され、アプリケーション内ナビゲーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ec580-152"><xref:System.Windows.Navigation.NavigationService>, the shared navigation engine for processing navigation requests that is used by <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>, and [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] to support intra-application navigation.</span></span>  
  
- <span data-ttu-id="ec580-153">ナビゲーションを開始するためのナビゲーション メソッド。</span><span class="sxs-lookup"><span data-stu-id="ec580-153">Navigation methods to initiate navigation.</span></span>  
  
- <span data-ttu-id="ec580-154">ナビゲーションの有効期間を追跡し、これと相互作用するためのナビゲーション イベント。</span><span class="sxs-lookup"><span data-stu-id="ec580-154">Navigation events to track and interact with navigation lifetime.</span></span>  
  
- <span data-ttu-id="ec580-155">履歴を使用した前方や後方へのナビゲーションの記憶。履歴は、調べたり、操作したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ec580-155">Remembering back and forward navigation using a journal, which can also be inspected and manipulated.</span></span>  
  
 <span data-ttu-id="ec580-156">詳細については、「[ナビゲーションの概要](navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec580-156">For information, see [Navigation Overview](navigation-overview.md).</span></span>  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="ec580-157">は、構造化ナビゲーションと呼ばれる特別な種類のナビゲーションもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ec580-157">also supports a special type of navigation known as structured navigation.</span></span> <span data-ttu-id="ec580-158">構造化ナビゲーションを使用すると、呼び出し元関数との一貫性が保たれた、構造化されて予測可能な形式でデータを返す 1 つ以上のページを呼び出す事ができます。</span><span class="sxs-lookup"><span data-stu-id="ec580-158">Structured navigation can be used to call one or more pages that return data in a structured and predictable way that is consistent with calling functions.</span></span> <span data-ttu-id="ec580-159">この機能は <xref:System.Windows.Navigation.PageFunction%601> クラスに依存します。このクラスの詳細については、「[構造化ナビゲーションの概要](structured-navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec580-159">This capability depends on the <xref:System.Windows.Navigation.PageFunction%601> class, which is described further in [Structured Navigation Overview](structured-navigation-overview.md).</span></span> <span data-ttu-id="ec580-160">また、<xref:System.Windows.Navigation.PageFunction%601> を使用すると、複雑なナビゲーション トポロジを簡単に作成することもできます。詳細については、「[ナビゲーション トポロジの概要](navigation-topologies-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec580-160"><xref:System.Windows.Navigation.PageFunction%601> also serves to simplify the creation of complex navigation topologies, which are described in [Navigation Topologies Overview](navigation-topologies-overview.md).</span></span>  
  
<a name="Hosting"></a>   
## <a name="hosting"></a><span data-ttu-id="ec580-161">ホスト</span><span class="sxs-lookup"><span data-stu-id="ec580-161">Hosting</span></span>  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] <span data-ttu-id="ec580-162">は、[!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] または Firefox でホストできます。</span><span class="sxs-lookup"><span data-stu-id="ec580-162">can be hosted in [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] or Firefox.</span></span> <span data-ttu-id="ec580-163">ホストのモデルによって考慮事項や制約が異なります。詳細については、「[ホスティング](hosting-wpf-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec580-163">Each hosting model has its own set of considerations and constraints that are covered in [Hosting](hosting-wpf-applications.md).</span></span>  
  
<a name="Build_and_Deploy"></a>   
## <a name="build-and-deploy"></a><span data-ttu-id="ec580-164">ビルドと配置</span><span class="sxs-lookup"><span data-stu-id="ec580-164">Build and Deploy</span></span>  
 <span data-ttu-id="ec580-165">単純な [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] アプリケーションはコマンド ライン コンパイラを使用してコマンド プロンプトでビルドできますが、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] と [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] が統合されることで、開発とビルドのプロセスを簡略化するための追加サポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec580-165">Although simple [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications can be built from a command prompt using command-line compilers, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] integrates with [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] to provide additional support that simplified the development and build process.</span></span> <span data-ttu-id="ec580-166">詳細については、「[WPF アプリケーションのビルド](building-a-wpf-application-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec580-166">For more information, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>  
  
 <span data-ttu-id="ec580-167">ビルドするアプリケーションの種類によって、選択する配置オプションが異なります。</span><span class="sxs-lookup"><span data-stu-id="ec580-167">Depending on the type of application you build, there are one or more deployment options to choose from.</span></span> <span data-ttu-id="ec580-168">詳細については、「[WPF アプリケーションの配置](deploying-a-wpf-application-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec580-168">For more information, see [Deploying a WPF Application](deploying-a-wpf-application-wpf.md).</span></span>  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="ec580-169">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ec580-169">Related Topics</span></span>  
  
|<span data-ttu-id="ec580-170">タイトル</span><span class="sxs-lookup"><span data-stu-id="ec580-170">Title</span></span>|<span data-ttu-id="ec580-171">説明</span><span class="sxs-lookup"><span data-stu-id="ec580-171">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="ec580-172">アプリケーション管理の概要</span><span class="sxs-lookup"><span data-stu-id="ec580-172">Application Management Overview</span></span>](application-management-overview.md)|<span data-ttu-id="ec580-173">アプリケーションの有効期間、ウィンドウ、アプリケーション リソース、ナビゲーションの管理など、<xref:System.Windows.Application> クラスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec580-173">Provides an overview of the <xref:System.Windows.Application> class including managing application lifetime, windows, application resources, and navigation.</span></span>|  
|[<span data-ttu-id="ec580-174">WPF のウィンドウ</span><span class="sxs-lookup"><span data-stu-id="ec580-174">Windows in WPF</span></span>](windows-in-wpf-applications.md)|<span data-ttu-id="ec580-175"><xref:System.Windows.Window> クラスおよびダイアログ ボックスの使い方など、アプリケーション内のウィンドウ管理の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec580-175">Provides details of managing windows in your application including how to use the <xref:System.Windows.Window> class and dialog boxes.</span></span>|  
|[<span data-ttu-id="ec580-176">ナビゲーションの概要</span><span class="sxs-lookup"><span data-stu-id="ec580-176">Navigation Overview</span></span>](navigation-overview.md)|<span data-ttu-id="ec580-177">アプリケーション内のページ間でのナビゲーション管理の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec580-177">Provides an overview of managing navigation between pages of your application.</span></span>|  
|[<span data-ttu-id="ec580-178">ホスティング</span><span class="sxs-lookup"><span data-stu-id="ec580-178">Hosting</span></span>](hosting-wpf-applications.md)|<span data-ttu-id="ec580-179">[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] の概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="ec580-179">Provides an overview of [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].</span></span>|  
|[<span data-ttu-id="ec580-180">ビルドと配置</span><span class="sxs-lookup"><span data-stu-id="ec580-180">Build and Deploy</span></span>](building-and-deploying-wpf-applications.md)|<span data-ttu-id="ec580-181">WPF アプリケーションをビルドして配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec580-181">Describes how to build and deploy your WPF application.</span></span>|  
|[<span data-ttu-id="ec580-182">Visual Studio での WPF の概要</span><span class="sxs-lookup"><span data-stu-id="ec580-182">Introduction to WPF in Visual Studio</span></span>](../getting-started/introduction-to-wpf-in-vs.md)|<span data-ttu-id="ec580-183">WPF の主な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec580-183">Describes the main features of WPF.</span></span>|  
|[<span data-ttu-id="ec580-184">チュートリアル: 初めての WPF デスクトップ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ec580-184">Walkthrough: My first WPF desktop application</span></span>](../getting-started/walkthrough-my-first-wpf-desktop-application.md)|<span data-ttu-id="ec580-185">ページ ナビゲーション、レイアウト、コントロール、イメージ、スタイル、バインディングを使用する WPF アプリケーションの作成方法を示すチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="ec580-185">A walkthrough that shows how to create a WPF application using page navigation, layout, controls, images, styles, and binding.</span></span>|
