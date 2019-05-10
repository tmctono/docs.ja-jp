---
title: WPF のセキュリティ方針 - セキュリティ エンジニアリング
ms.date: 03/30/2017
helpviewer_keywords:
- security [WPF], testing techniques
- Security Development Lifecycle (SDL), security analysis [WPF]
- Security Development Lifecycle (SDL), threat modeling
- Security Development Lifecycle (SDL), testing techniques
- Security Development Lifecycle (SDL), source analysis tools
- Security Development Lifecycle (SDL), critical code management
- threat modeling [WPF]
ms.assetid: 0fc04394-4e47-49ca-b0cf-8cd1161d95b9
ms.openlocfilehash: 9123d59709b483c72ab49652bda1e547430fa33d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663248"
---
# <a name="wpf-security-strategy---security-engineering"></a><span data-ttu-id="0ebe0-102">WPF のセキュリティ方針 - セキュリティ エンジニアリング</span><span class="sxs-lookup"><span data-stu-id="0ebe0-102">WPF Security Strategy - Security Engineering</span></span>
<span data-ttu-id="0ebe0-103">信頼できるコンピューティングは、セキュリティで保護されたコードの実稼働環境を確保するための Microsoft イニシアチブです。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-103">Trustworthy Computing is a Microsoft initiative for ensuring the production of secure code.</span></span> <span data-ttu-id="0ebe0-104">信頼できるコンピューティング イニシアチブの重要な要素は、[!INCLUDE[TLA#tla_sdl](../../../includes/tlasharptla-sdl-md.md)] です。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-104">A key element of the Trustworthy Computing initiative is the [!INCLUDE[TLA#tla_sdl](../../../includes/tlasharptla-sdl-md.md)].</span></span> <span data-ttu-id="0ebe0-105">[!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] は、セキュリティで保護されたコードの配信を容易にする標準のエンジニアリング プロセスと組み合わせて使用するエンジニアリングの方法です。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-105">The [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] is an engineering practice that is used in conjunction with standard engineering processes to facilitate the delivery of secure code.</span></span> <span data-ttu-id="0ebe0-106">[!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] は、ベスト プラクティスと形式化、測定可能性、追加の構造を組み合わせた 10 のフェーズで構成しています。それらは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-106">The [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] consists of ten phases that combine best practices with formalization, measurability, and additional structure, including:</span></span>  
  
- <span data-ttu-id="0ebe0-107">セキュリティ設計の分析</span><span class="sxs-lookup"><span data-stu-id="0ebe0-107">Security design analysis</span></span>  
  
- <span data-ttu-id="0ebe0-108">ツール ベースの品質チェック</span><span class="sxs-lookup"><span data-stu-id="0ebe0-108">Tool-based quality checks</span></span>  
  
- <span data-ttu-id="0ebe0-109">侵入テスト</span><span class="sxs-lookup"><span data-stu-id="0ebe0-109">Penetration testing</span></span>  
  
- <span data-ttu-id="0ebe0-110">最終的なセキュリティ レビュー</span><span class="sxs-lookup"><span data-stu-id="0ebe0-110">Final security review</span></span>  
  
- <span data-ttu-id="0ebe0-111">製品のリリース後のセキュリティ管理</span><span class="sxs-lookup"><span data-stu-id="0ebe0-111">Post release product security management</span></span>  
  
## <a name="wpf-specifics"></a><span data-ttu-id="0ebe0-112">WPF 固有の仕様</span><span class="sxs-lookup"><span data-stu-id="0ebe0-112">WPF Specifics</span></span>  
 <span data-ttu-id="0ebe0-113">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] エンジニアリング チームは、[!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] の適用と拡張の両方を行います。この組み合わせには、次の主要な側面があります。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-113">The [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] engineering team both applies and extends the [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)], the combination of which includes the following key aspects:</span></span>  
  
 [<span data-ttu-id="0ebe0-114">脅威モデリング</span><span class="sxs-lookup"><span data-stu-id="0ebe0-114">Threat Modeling</span></span>](#threat_modeling)  
  
 [<span data-ttu-id="0ebe0-115">セキュリティ分析および編集ツール</span><span class="sxs-lookup"><span data-stu-id="0ebe0-115">Security Analysis and Editing Tools</span></span>](#tools)  
  
 [<span data-ttu-id="0ebe0-116">テスト手法</span><span class="sxs-lookup"><span data-stu-id="0ebe0-116">Testing Techniques</span></span>](#techniques)  
  
 [<span data-ttu-id="0ebe0-117">クリティカル コードの管理</span><span class="sxs-lookup"><span data-stu-id="0ebe0-117">Critical Code Management</span></span>](#critical_code)  
  
<a name="threat_modeling"></a>   
### <a name="threat-modeling"></a><span data-ttu-id="0ebe0-118">脅威モデリング</span><span class="sxs-lookup"><span data-stu-id="0ebe0-118">Threat Modeling</span></span>  
 <span data-ttu-id="0ebe0-119">脅威モデリングは、[!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] の主要コンポーネントで、システムをプロファイリングして潜在的なセキュリティの脆弱性を判断するために使用します。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-119">Threat modeling is a core component of the [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)], and is used to profile a system to determine potential security vulnerabilities.</span></span> <span data-ttu-id="0ebe0-120">脆弱性が特定されると、脅威モデリングは、常に適切な緩和策が存在することも保証します。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-120">Once the vulnerabilities are identified, threat modeling also ensures that appropriate mitigations are in place.</span></span>  
  
 <span data-ttu-id="0ebe0-121">概略でとらえれば、食料品店を例にすると、脅威モデリングには次の主要な手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-121">At a high level, threat modeling involves the following key steps by using a grocery store as an example:</span></span>  
  
1. <span data-ttu-id="0ebe0-122">**資産の特定**。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-122">**Identifying Assets**.</span></span> <span data-ttu-id="0ebe0-123">食料品店の資産には、従業員、安全、レジ、および在庫などがあります。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-123">A grocery store's assets might include employees, a safe, cash registers, and inventory.</span></span>  
  
2. <span data-ttu-id="0ebe0-124">**エントリ ポイントの列挙**。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-124">**Enumerating Entry Points**.</span></span> <span data-ttu-id="0ebe0-125">食料品店のエントリ ポイントには、玄関と裏口、窓、搬入口、および空調装置などがあります。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-125">A grocery store's entry points might include the front and back doors, windows, the loading dock, and air conditioning units.</span></span>  
  
3. <span data-ttu-id="0ebe0-126">**エントリ ポイントを使用した資産に対する攻撃の調査**。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-126">**Investigating Attacks against Assets using Entry Points**.</span></span> <span data-ttu-id="0ebe0-127">可能性のある攻撃の 1 つは、*空調設備*のエントリ ポイントを通じた食料品店の*安全*資産をターゲットとするものです。空調装置のねじが緩められると、そこから食糧品の安全が損なわれ、店自体の損失になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-127">One possible attack could target a grocery store's *safe* asset through the *air conditioning* entry point; the air conditioning unit could be unscrewed to allow the safe to be pulled up through it and out of the store.</span></span>  
  
 <span data-ttu-id="0ebe0-128">脅威モデリングは [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 全体に適用されます。それは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-128">Threat modeling is applied throughout [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] and includes the following:</span></span>  
  
- <span data-ttu-id="0ebe0-129">[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] パーサーのファイルの読み取り方法、対応するオブジェクト モデルのクラスへのテキストのマッピング方法、および実際のコードの作成方法。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-129">How the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] parser reads files, maps text to corresponding object model classes, and creates the actual code.</span></span>  
  
- <span data-ttu-id="0ebe0-130">ウィンドウ ハンドル (hWnd) の作成方法、メッセージの送信方法、hWnd を使用したウィンドウの内容の表示方法。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-130">How a window handle (hWnd) is created, sends messages, and is used for rendering the contents of a window.</span></span>  
  
- <span data-ttu-id="0ebe0-131">データ バインドがリソースを取得し、システムと対話する方法。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-131">How data binding obtains resources and interacts with the system.</span></span>  
  
 <span data-ttu-id="0ebe0-132">これらの脅威モデリングは、開発プロセス中のセキュリティ設計要件の識別と脅威の緩和策にとって重要です。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-132">These threat models are important for identifying security design requirements and threat mitigations during the development process.</span></span>  
  
<a name="tools"></a>   
### <a name="source-analysis-and-editing-tools"></a><span data-ttu-id="0ebe0-133">ソースの分析および編集ツール</span><span class="sxs-lookup"><span data-stu-id="0ebe0-133">Source Analysis and Editing Tools</span></span>  
 <span data-ttu-id="0ebe0-134">[!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] の手動セキュリティ コード レビュー要素に加えて、[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] チームは、ソースの分析と関連する編集のためのいくつかのツールを使用してセキュリティの脆弱性を低減します。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-134">In addition to the manual security code review elements of the [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)], the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] team uses several tools for source analysis and associated edits to decrease security vulnerabilities.</span></span> <span data-ttu-id="0ebe0-135">さまざまなソースのツールを使用できます。それらは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-135">A wide range of source tools are used, and include the following:</span></span>  
  
- <span data-ttu-id="0ebe0-136">**FXCop**:継承ルールからコード アクセス セキュリティと安全にアンマネージ コードと相互運用する方法の使用法に至るまで、マネージ コードでは、一般的なセキュリティ問題を検索します。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-136">**FXCop**: Finds common security issues in managed code ranging from inheritance rules to code access security usage to how to safely interoperate with unmanaged code.</span></span> <span data-ttu-id="0ebe0-137">[FXCop](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/bb429476%28v=vs.80%29) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-137">See [FXCop](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/bb429476%28v=vs.80%29).</span></span>  
  
- <span data-ttu-id="0ebe0-138">**Prefix/prefast**:バッファー オーバーラン、書式文字列の問題、エラー チェックなどのアンマネージ コードでは、セキュリティの脆弱性および一般的なセキュリティ問題を検索します。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-138">**Prefix/Prefast**: Finds security vulnerabilities and common security issues in unmanaged code such as buffer overruns, format string issues, and error checking.</span></span>  
  
- <span data-ttu-id="0ebe0-139">**Banned APIs**:ソースのセキュリティ問題の原因としてなどのよく知られている関数の偶発的な使用を識別するためにコードを検索`strcpy`します。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-139">**Banned APIs**: Searches source code to identify accidental usage of functions that are well-known for causing security issues, such as `strcpy`.</span></span> <span data-ttu-id="0ebe0-140">そのような関数が識別されると、よりセキュリティの高い代替手段に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-140">Once identified, these functions are replaced with alternatives that are more security.</span></span>  
  
<a name="techniques"></a>   
### <a name="testing-techniques"></a><span data-ttu-id="0ebe0-141">テスト手法</span><span class="sxs-lookup"><span data-stu-id="0ebe0-141">Testing Techniques</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="0ebe0-142">では、さまざまなテスト手法を使用します。それらは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-142">uses a variety of security testing techniques that include:</span></span>  
  
- <span data-ttu-id="0ebe0-143">**ホワイト ボックス テスト**:テスト担当者が、ソース コードを表示および悪用テストを作成し、</span><span class="sxs-lookup"><span data-stu-id="0ebe0-143">**Whitebox Testing**: Testers view source code, and then build exploit tests</span></span>  
  
- <span data-ttu-id="0ebe0-144">**ブラック ボックス テスト**:テスト担当者は、API と機能を調査してセキュリティの悪用を検索しようし、製品を攻撃ましょう。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-144">**Blackbox Testing**: Testers try to find security exploits by examining the API and features, and then try to attack the product.</span></span>  
  
- <span data-ttu-id="0ebe0-145">**その他の製品から問題を再現セキュリティ**:該当する場合、関連する製品からのセキュリティの問題がテストされます。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-145">**Regressing Security Issues from other Products**: Where relevant, security issues from related products are tested.</span></span> <span data-ttu-id="0ebe0-146">たとえば、[!INCLUDE[TLA2#tla_ie](../../../includes/tla2sharptla-ie-md.md)] の約 60 のセキュリティの問題に適した変種を特定して、それが [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] に適用できるかどうかを試します。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-146">For example, appropriate variants of approximately sixty security issues for [!INCLUDE[TLA2#tla_ie](../../../includes/tla2sharptla-ie-md.md)] have been identified and tried for their applicability to [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
- <span data-ttu-id="0ebe0-147">**ツール ベースの侵入テストを通じたファイルのファジー テスト**:ファイルのファジー化は、ファイル リーダーの悪用のさまざまな入力からの範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-147">**Tools-Based Penetration Testing through File Fuzzing**: File fuzzing is the exploitation of a file reader's input range through a variety of inputs.</span></span> <span data-ttu-id="0ebe0-148">この手法が使用される [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] の一例は、イメージ デコード コードでエラーを確認することです。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-148">One example in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] where this technique is used is to check for failure in image decoding code.</span></span>  
  
<a name="critical_code"></a>   
### <a name="critical-code-management"></a><span data-ttu-id="0ebe0-149">クリティカル コードの管理</span><span class="sxs-lookup"><span data-stu-id="0ebe0-149">Critical Code Management</span></span>  
 <span data-ttu-id="0ebe0-150">[!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)]、[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]マークおよび特権を昇格させるセキュリティ クリティカルなコードを追跡するための .NET Framework のサポートを使用してセキュリティ サンド ボックスをビルド (を参照してください**セキュリティ クリティカルな手法**で[WPFセキュリティ方針 - プラットフォーム セキュリティ](wpf-security-strategy-platform-security.md))。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-150">For [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] builds a security sandbox by using .NET Framework support for marking and tracking security-critical code that elevates privileges (see **Security-Critical Methodology** in [WPF Security Strategy - Platform Security](wpf-security-strategy-platform-security.md)).</span></span> <span data-ttu-id="0ebe0-151">セキュリティ クリティカルなコードに対して高度なセキュリティの品質要件を指定すると、このようなコードは、追加レベルのソース管理の制御とセキュリティの監査を受けします。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-151">Given the high security quality requirements on security critical code, such code receives an additional level of source management control and security audit.</span></span> <span data-ttu-id="0ebe0-152">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] の約 5 ～ 10% はセキュリティ クリティカルなコードで構成され、専用のレビュー チームによって確認されます。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-152">Approximately 5% to 10% of [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] consists of security-critical code, which is reviewed by a dedicated reviewing team.</span></span> <span data-ttu-id="0ebe0-153">ソース コードとチェックイン プロセスの管理は、セキュリティ クリティカルなコードを追跡し、各クリティカル エンティティ (重要なコードを含むメソッド) をサイン オフ状態にマップすることにより行われています。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-153">The source code and check-in process is managed by tracking security critical code and mapping each critical entity (i.e. a method that contains critical code) to its sign off state.</span></span> <span data-ttu-id="0ebe0-154">サイン オフ状態には、1 つ以上のレビュー担当者の名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-154">The sign off state includes the names of one or more reviewers.</span></span> <span data-ttu-id="0ebe0-155">毎日の [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] のビルドは、前のビルドのクリティカル コードと比較されて、承認されていない変更がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-155">Each daily build of [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] compares the critical code to that in previous builds to check for unapproved changes.</span></span> <span data-ttu-id="0ebe0-156">エンジニアがレビュー チームからの承認を得ずにクリティカル コードを変更すると、そのクリティカル コードはすぐに識別および修正されます。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-156">If an engineer modifies critical code without approval from the reviewing team, it is identified and fixed immediately.</span></span> <span data-ttu-id="0ebe0-157">このプロセスでは、[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] サンドボックス コードで特に高いレベルの監視の適用と維持が可能になります。</span><span class="sxs-lookup"><span data-stu-id="0ebe0-157">This process enables the application and maintenance of an especially high level of scrutiny over [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] sandbox code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ebe0-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ebe0-158">See also</span></span>

- [<span data-ttu-id="0ebe0-159">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="0ebe0-159">Security</span></span>](security-wpf.md)
- [<span data-ttu-id="0ebe0-160">WPF 部分信頼セキュリティ</span><span class="sxs-lookup"><span data-stu-id="0ebe0-160">WPF Partial Trust Security</span></span>](wpf-partial-trust-security.md)
- [<span data-ttu-id="0ebe0-161">WPF のセキュリティ方針 - プラットフォーム セキュリティ</span><span class="sxs-lookup"><span data-stu-id="0ebe0-161">WPF Security Strategy - Platform Security</span></span>](wpf-security-strategy-platform-security.md)
- [<span data-ttu-id="0ebe0-162">信頼できるコンピューティング</span><span class="sxs-lookup"><span data-stu-id="0ebe0-162">Trustworthy Computing</span></span>](https://www.microsoft.com/mscorp/twc/default.mspx)
- [<span data-ttu-id="0ebe0-163">.NET でのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="0ebe0-163">Security in .NET</span></span>](../../standard/security/index.md)
