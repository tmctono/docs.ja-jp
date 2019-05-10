---
title: ToolStrip コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 75df256f852b45af4bc6cf519c13ccd62ae1d689
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64654768"
---
# <a name="toolstrip-control-overview-windows-forms"></a><span data-ttu-id="0397a-102">ToolStrip コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="0397a-102">ToolStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="0397a-103">Windows フォーム<xref:System.Windows.Forms.ToolStrip>コントロールとその関連クラスは、ツールバー、ステータス バー、およびメニューにユーザー インターフェイス要素を結合するため、共通のフレームワークを提供します。</span><span class="sxs-lookup"><span data-stu-id="0397a-103">The Windows Forms <xref:System.Windows.Forms.ToolStrip> control and its associated classes provide a common framework for combining user interface elements into toolbars, status bars, and menus.</span></span> <span data-ttu-id="0397a-104"><xref:System.Windows.Forms.ToolStrip> コントロールでは、水平または垂直スペースを共有するツールバーの機能は、インプレース アクティブ化と編集、カスタム レイアウト、およびラフティング、豊富なデザイン時エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0397a-104"><xref:System.Windows.Forms.ToolStrip> controls offer a rich design-time experience that includes in-place activation and editing, custom layout, and rafting, which is the ability of toolbars to share horizontal or vertical space.</span></span>  
  
 <span data-ttu-id="0397a-105"><xref:System.Windows.Forms.ToolStrip>が置換および以前のバージョンで制御する機能を追加<xref:System.Windows.Forms.ToolBar>必要な場合に、旧バージョンとの互換性と将来の使用のため保持されます。</span><span class="sxs-lookup"><span data-stu-id="0397a-105">Although <xref:System.Windows.Forms.ToolStrip> replaces and adds functionality to the control in previous versions, <xref:System.Windows.Forms.ToolBar> is retained for both backward compatibility and future use if desired.</span></span>  
  
## <a name="features-of-the-toolstrip-controls"></a><span data-ttu-id="0397a-106">ToolStrip コントロールの機能</span><span class="sxs-lookup"><span data-stu-id="0397a-106">Features of the ToolStrip Controls</span></span>  
 <span data-ttu-id="0397a-107">使用して、<xref:System.Windows.Forms.ToolStrip>を制御します。</span><span class="sxs-lookup"><span data-stu-id="0397a-107">Use the <xref:System.Windows.Forms.ToolStrip> control to:</span></span>  
  
- <span data-ttu-id="0397a-108">コンテナー間には、一般的なユーザー インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0397a-108">Present a common user interface across containers.</span></span>  
  
- <span data-ttu-id="0397a-109">簡単にカスタマイズされた作成、サポートするツールバーが一般的に使用されるユーザー インターフェイスとレイアウトの機能の詳細などのテキストとイメージ、ドロップダウン ボタン、およびコントロールのドッキング、ラフティング、ボタン、オーバーフロー ボタン、および実行時の並べ替えの<xref:System.Windows.Forms.ToolStrip>項目。</span><span class="sxs-lookup"><span data-stu-id="0397a-109">Create easily customized, commonly employed toolbars that support advanced user interface and layout features, such as docking, rafting, buttons with text and images, drop-down buttons and controls, overflow buttons, and run-time reordering of <xref:System.Windows.Forms.ToolStrip> items.</span></span>  
  
- <span data-ttu-id="0397a-110">オーバーフローおよび実行時の項目の並べ替えをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0397a-110">Support overflow and run-time item reordering.</span></span> <span data-ttu-id="0397a-111">オーバーフロー機能がでそれらを表示する十分な空き領域がない場合に、ドロップダウン メニューに項目を移動、<xref:System.Windows.Forms.ToolStrip>します。</span><span class="sxs-lookup"><span data-stu-id="0397a-111">The overflow feature moves items to a drop-down menu when there is not enough room to display them in a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
- <span data-ttu-id="0397a-112">標準的な外観と動作の一般的なレンダリング モデルにより、オペレーティング システムをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0397a-112">Support the typical appearance and behavior of the operating system through a common rendering model.</span></span>  
  
- <span data-ttu-id="0397a-113">同様に他のコントロールのイベントを処理するには、すべてのコンテナーと含まれる項目を一貫してイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="0397a-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
- <span data-ttu-id="0397a-114">いずれかから項目をドラッグ<xref:System.Windows.Forms.ToolStrip>別、または、<xref:System.Windows.Forms.ToolStrip>します。</span><span class="sxs-lookup"><span data-stu-id="0397a-114">Drag items from one <xref:System.Windows.Forms.ToolStrip> to another or within a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
- <span data-ttu-id="0397a-115">ドロップダウン コントロールとユーザー インターフェイス型エディターを高度なレイアウトを作成、<xref:System.Windows.Forms.ToolStripDropDown>します。</span><span class="sxs-lookup"><span data-stu-id="0397a-115">Create drop-down controls and user interface type editors with advanced layouts in a <xref:System.Windows.Forms.ToolStripDropDown>.</span></span>  
  
 <span data-ttu-id="0397a-116">使用して、<xref:System.Windows.Forms.ToolStripControlHost>クラスを他のコントロールを使用して、<xref:System.Windows.Forms.ToolStrip>行い、<xref:System.Windows.Forms.ToolStrip>それらの機能です。</span><span class="sxs-lookup"><span data-stu-id="0397a-116">Use the <xref:System.Windows.Forms.ToolStripControlHost> class to use other controls on a <xref:System.Windows.Forms.ToolStrip> and gain <xref:System.Windows.Forms.ToolStrip> functionality for them.</span></span>  
  
 <span data-ttu-id="0397a-117">機能を拡張しを使用して外観と動作を変更することができます、 <xref:System.Windows.Forms.ToolStripRenderer>、 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>、および<xref:System.Windows.Forms.ToolStripManager>と共に、<xref:System.Windows.Forms.ToolStripRenderMode>と<xref:System.Windows.Forms.ToolStripManagerRenderMode>列挙体。</span><span class="sxs-lookup"><span data-stu-id="0397a-117">You can extend the functionality and modify the appearance and behavior by using the <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, and <xref:System.Windows.Forms.ToolStripManager> along with the <xref:System.Windows.Forms.ToolStripRenderMode> and <xref:System.Windows.Forms.ToolStripManagerRenderMode> enumerations.</span></span>  
  
 <span data-ttu-id="0397a-118"><xref:System.Windows.Forms.ToolStrip>コントロール、構成可能かつ拡張可能なおよび多くのプロパティ、メソッド、および外観と動作をカスタマイズするイベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="0397a-118">The <xref:System.Windows.Forms.ToolStrip> control is highly configurable and extensible, and it provides many properties, methods, and events to customize appearance and behavior.</span></span> <span data-ttu-id="0397a-119">いくつかの重要なメンバーを次に示します。</span><span class="sxs-lookup"><span data-stu-id="0397a-119">Below are some noteworthy members:</span></span>  
  
### <a name="important-toolstrip-members"></a><span data-ttu-id="0397a-120">ToolStrip の重要なメンバー</span><span class="sxs-lookup"><span data-stu-id="0397a-120">Important ToolStrip Members</span></span>  
  
|<span data-ttu-id="0397a-121">名前</span><span class="sxs-lookup"><span data-stu-id="0397a-121">Name</span></span>|<span data-ttu-id="0397a-122">説明</span><span class="sxs-lookup"><span data-stu-id="0397a-122">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|<span data-ttu-id="0397a-123">取得または設定の親コンテナーの端を<xref:System.Windows.Forms.ToolStrip>にドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="0397a-123">Gets or sets which edge of the parent container a <xref:System.Windows.Forms.ToolStrip> is docked to.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|<span data-ttu-id="0397a-124"><xref:System.Windows.Forms.ToolStrip> クラスがドラッグ アンド ドロップおよび項目の並べ替えをプライベートで処理するかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="0397a-124">Gets or sets a value indicating whether drag-and-drop and item reordering are handled privately by the <xref:System.Windows.Forms.ToolStrip> class.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|<span data-ttu-id="0397a-125">取得または設定を示す値が、どのように<xref:System.Windows.Forms.ToolStrip>その項目のレイアウトします。</span><span class="sxs-lookup"><span data-stu-id="0397a-125">Gets or sets a value indicating how the <xref:System.Windows.Forms.ToolStrip> lays out its items.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|<span data-ttu-id="0397a-126">取得または設定するかどうかを<xref:System.Windows.Forms.ToolStripItem>にアタッチされて、<xref:System.Windows.Forms.ToolStrip>または<xref:System.Windows.Forms.ToolStripOverflowButton>2 つの間で変動するか。</span><span class="sxs-lookup"><span data-stu-id="0397a-126">Gets or sets whether a <xref:System.Windows.Forms.ToolStripItem> is attached to the <xref:System.Windows.Forms.ToolStrip> or <xref:System.Windows.Forms.ToolStripOverflowButton> or can float between the two.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|<span data-ttu-id="0397a-127">示す値を取得するかどうか、<xref:System.Windows.Forms.ToolStripItem>ドロップダウンからその他の項目を表示するときに、<xref:System.Windows.Forms.ToolStripItem>がクリックされました。</span><span class="sxs-lookup"><span data-stu-id="0397a-127">Gets a value indicating whether a <xref:System.Windows.Forms.ToolStripItem> displays other items in a drop-down list when the <xref:System.Windows.Forms.ToolStripItem> is clicked.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|<span data-ttu-id="0397a-128">オーバーフローが有効な <xref:System.Windows.Forms.ToolStripItem> のオーバーフロー ボタンである <xref:System.Windows.Forms.ToolStrip> を取得します。</span><span class="sxs-lookup"><span data-stu-id="0397a-128">Gets the <xref:System.Windows.Forms.ToolStripItem> that is the overflow button for a <xref:System.Windows.Forms.ToolStrip> with overflow enabled.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|<span data-ttu-id="0397a-129">取得または設定します、<xref:System.Windows.Forms.ToolStripRenderer>の動作 (ルック アンド フィール) と外観をカスタマイズするために使用する<xref:System.Windows.Forms.ToolStrip>します。</span><span class="sxs-lookup"><span data-stu-id="0397a-129">Gets or sets a <xref:System.Windows.Forms.ToolStripRenderer> used to customize the appearance and behavior (look and feel) of a <xref:System.Windows.Forms.ToolStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|<span data-ttu-id="0397a-130">取得または設定に適用される描画スタイル、<xref:System.Windows.Forms.ToolStrip>します。</span><span class="sxs-lookup"><span data-stu-id="0397a-130">Gets or sets the painting styles to be applied to the <xref:System.Windows.Forms.ToolStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|<span data-ttu-id="0397a-131"><xref:System.Windows.Forms.ToolStrip.Renderer%2A> プロパティが変更されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="0397a-131">Raised when the <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property changes.</span></span>|  
  
 <span data-ttu-id="0397a-132"><xref:System.Windows.Forms.ToolStrip>コントロールの柔軟性は、多数のコンパニオン クラスを使用して実現されます。</span><span class="sxs-lookup"><span data-stu-id="0397a-132">The <xref:System.Windows.Forms.ToolStrip> control's flexibility is achieved through the use of a number of companion classes.</span></span> <span data-ttu-id="0397a-133">最も注目に値するの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0397a-133">Below are some of the most noteworthy:</span></span>  
  
### <a name="important-toolstrip-companion-classes"></a><span data-ttu-id="0397a-134">ToolStrip の重要なコンパニオン クラス</span><span class="sxs-lookup"><span data-stu-id="0397a-134">Important ToolStrip Companion Classes</span></span>  
  
|<span data-ttu-id="0397a-135">名前</span><span class="sxs-lookup"><span data-stu-id="0397a-135">Name</span></span>|<span data-ttu-id="0397a-136">説明</span><span class="sxs-lookup"><span data-stu-id="0397a-136">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|<span data-ttu-id="0397a-137">置換および追加する機能、<xref:System.Windows.Forms.MainMenu>クラス。</span><span class="sxs-lookup"><span data-stu-id="0397a-137">Replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> class.</span></span>|  
|<xref:System.Windows.Forms.StatusStrip>|<span data-ttu-id="0397a-138">置換および追加する機能、<xref:System.Windows.Forms.StatusBar>クラス。</span><span class="sxs-lookup"><span data-stu-id="0397a-138">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> class.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="0397a-139">置換および追加する機能、<xref:System.Windows.Forms.ContextMenu>クラス。</span><span class="sxs-lookup"><span data-stu-id="0397a-139">Replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> class.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem>|<span data-ttu-id="0397a-140">すべての要素のイベントおよびレイアウトを管理する基本クラスを抽象化する、 <xref:System.Windows.Forms.ToolStrip>、 <xref:System.Windows.Forms.ToolStripControlHost>、または<xref:System.Windows.Forms.ToolStripDropDown>含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0397a-140">Abstract base class that manages events and layout for all the elements that a <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>, or <xref:System.Windows.Forms.ToolStripDropDown> can contain.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="0397a-141">さまざまな方法でコントロールを配置するフォームの両側のパネルには、コンテナーを提供します。</span><span class="sxs-lookup"><span data-stu-id="0397a-141">Provides a container with a panel on each side of the form in which controls can be arranged in various ways.</span></span>|  
|<xref:System.Windows.Forms.ToolStripRenderer>|<span data-ttu-id="0397a-142">描画機能を処理<xref:System.Windows.Forms.ToolStrip>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0397a-142">Handles the painting functionality for <xref:System.Windows.Forms.ToolStrip> objects.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|<span data-ttu-id="0397a-143">Microsoft Office スタイルの外観を提供します。</span><span class="sxs-lookup"><span data-stu-id="0397a-143">Provides Microsoft Office-style appearance.</span></span>|  
|<xref:System.Windows.Forms.ToolStripManager>|<span data-ttu-id="0397a-144">コントロール<xref:System.Windows.Forms.ToolStrip>レンダリングとラフティングとのマージ<xref:System.Windows.Forms.MenuStrip>、 <xref:System.Windows.Forms.ToolStripDropDownMenu>、および<xref:System.Windows.Forms.ToolStripMenuItem>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0397a-144">Controls <xref:System.Windows.Forms.ToolStrip> rendering and rafting, and the merging of <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, and <xref:System.Windows.Forms.ToolStripMenuItem> objects.</span></span>|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|<span data-ttu-id="0397a-145">指定の倍数に適用される描画スタイル (ユーザー設定、Windows XP、または Microsoft Office Professional)<xref:System.Windows.Forms.ToolStrip>フォームに含まれるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0397a-145">Specifies the painting style (custom, Windows XP, or Microsoft Office Professional) applied to multiple <xref:System.Windows.Forms.ToolStrip> objects contained in a form.</span></span>|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|<span data-ttu-id="0397a-146">いずれかに適用される描画スタイル (ユーザー設定、Windows XP、または Microsoft Office Professional) を指定します<xref:System.Windows.Forms.ToolStrip>フォームに含まれるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0397a-146">Specifies the painting style (custom, Windows XP, or Microsoft Office Professional) applied to one <xref:System.Windows.Forms.ToolStrip> object contained in a form.</span></span>|  
|<xref:System.Windows.Forms.ToolStripControlHost>|<span data-ttu-id="0397a-147">具体的にはないその他のコントロールをホスト<xref:System.Windows.Forms.ToolStrip>コントロールを決定するが、<xref:System.Windows.Forms.ToolStrip>機能します。</span><span class="sxs-lookup"><span data-stu-id="0397a-147">Hosts other controls that are not specifically <xref:System.Windows.Forms.ToolStrip> controls but for which you want <xref:System.Windows.Forms.ToolStrip> functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|<span data-ttu-id="0397a-148">指定するかどうかを<xref:System.Windows.Forms.ToolStripItem>、メイン レイアウトするのには、 <xref:System.Windows.Forms.ToolStrip>、オーバーフローに<xref:System.Windows.Forms.ToolStrip>、またはどちらもします。</span><span class="sxs-lookup"><span data-stu-id="0397a-148">Specifies whether a <xref:System.Windows.Forms.ToolStripItem> is to be laid out on the main <xref:System.Windows.Forms.ToolStrip>, on the overflow <xref:System.Windows.Forms.ToolStrip>, or neither.</span></span>|  
  
 <span data-ttu-id="0397a-149">詳細については、次を参照してください。 [ToolStrip テクノロジの概要](toolstrip-technology-summary.md)と[ToolStrip コントロールのアーキテクチャ](toolstrip-control-architecture.md)します。</span><span class="sxs-lookup"><span data-stu-id="0397a-149">For more information, see [ToolStrip Technology Summary](toolstrip-technology-summary.md) and [ToolStrip Control Architecture](toolstrip-control-architecture.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0397a-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="0397a-150">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
