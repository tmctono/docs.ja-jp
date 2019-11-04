---
title: UI オートメーション MultipleView コントロール パターンの実装
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
ms.openlocfilehash: 62f0ba1dc8b7836a3b4699699b91b567eb8051f3
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458180"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a><span data-ttu-id="431cc-102">UI オートメーション MultipleView コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="431cc-102">Implementing the UI Automation MultipleView Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="431cc-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="431cc-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="431cc-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI Automation (Windows のオートメーション API: UI オートメーション)](https://go.microsoft.com/fwlink/?LinkID=156746)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="431cc-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="431cc-105">このトピックでは、イベントおよびプロパティに関する情報など、 <xref:System.Windows.Automation.Provider.IMultipleViewProvider>の実装のためのガイドラインと規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="431cc-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, including information about events and properties.</span></span> <span data-ttu-id="431cc-106">その他のリファレンスへのリンクは、トピックの最後に記載します。</span><span class="sxs-lookup"><span data-stu-id="431cc-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="431cc-107"><xref:System.Windows.Automation.MultipleViewPattern> コントロール パターンは、同じ情報セットまたは子コントロールの複数の表現を提供し、それらの表現を切り替えることができるコントロールをサポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="431cc-107">The <xref:System.Windows.Automation.MultipleViewPattern> control pattern is used to support controls that provide, and are able to switch between, multiple representations of the same set of information or child controls.</span></span>  
  
 <span data-ttu-id="431cc-108">複数のビューを表示するコントロールの例としては、リストビュー (コンテンツをサムネイル、タイル、アイコン、詳細として表示できる)、Microsoft Excel のグラフ (円、線、横棒、セルの値など)、Microsoft Word 文書 (標準、Web レイアウト、印刷など) があります。レイアウト、閲覧レイアウト、アウトライン)、Microsoft Outlook カレンダー (年、月、週、日)、および Microsoft Windows Media Player スキン。</span><span class="sxs-lookup"><span data-stu-id="431cc-108">Examples of controls that can present multiple views include the list view (which can show its contents as thumbnails, tiles, icons, or details), Microsoft Excel charts (pie, line, bar, cell value with a formula), Microsoft Word documents (normal, Web layout, print layout, reading layout, outline), Microsoft Outlook calendar (year, month, week, day), and Microsoft Windows Media Player skins.</span></span> <span data-ttu-id="431cc-109">サポートされるビューはコントロールの開発者によって決定され、各コントロールに固有です。</span><span class="sxs-lookup"><span data-stu-id="431cc-109">The supported views are determined by the control developer and are specific to each control.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="431cc-110">実装のガイドラインと規則</span><span class="sxs-lookup"><span data-stu-id="431cc-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="431cc-111">Multiple View コントロール パターンを実装する場合は、次のガイドラインと規則にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="431cc-111">When implementing the Multiple View control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="431cc-112">現在のビューを管理するコンテナーが現在のビューを提供するコントロールとは異なる場合は、現在のビューを管理するためのコンテナーにも<xref:System.Windows.Automation.Provider.IMultipleViewProvider> を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="431cc-112"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> should also be implemented on a container that manages the current view if it is different from a control that provides the current view.</span></span> <span data-ttu-id="431cc-113">たとえば、Windows エクスプローラーには現在のフォルダーのコンテンツの List コントロールが含まれていますが、そのコントロールのビューは Windows エクスプローラーのアプリケーションから管理されています。</span><span class="sxs-lookup"><span data-stu-id="431cc-113">For example, Windows Explorer contains a List control for the current folder content while the view for the control is managed from the Windows Explorer application.</span></span>  
  
- <span data-ttu-id="431cc-114">自身のコンテンツを並べ替えることができるコントロールは、複数のビューをサポートしているとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="431cc-114">A control that is able to sort its content is not considered to support multiple views.</span></span>  
  
- <span data-ttu-id="431cc-115">ビューのコレクションは、インスタンス間で同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="431cc-115">The collection of views must be identical across instances.</span></span>  
  
- <span data-ttu-id="431cc-116">ビューの名前は、読み上げ、ブライユ点字、その他の人間が判読できるアプリケーションでの使用に適した名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="431cc-116">View names must be suitable for use in Text to Speech, Braille, and other human-readable applications.</span></span>  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>   
## <a name="required-members-for-imultipleviewprovider"></a><span data-ttu-id="431cc-117">IMultipleViewProvider の必須メンバー</span><span class="sxs-lookup"><span data-stu-id="431cc-117">Required Members for IMultipleViewProvider</span></span>  
 <span data-ttu-id="431cc-118">IMultipleViewProvider の実装には、次のプロパティとメソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="431cc-118">The following properties and methods are required for implementing IMultipleViewProvider.</span></span>  
  
|<span data-ttu-id="431cc-119">必須メンバー</span><span class="sxs-lookup"><span data-stu-id="431cc-119">Required members</span></span>|<span data-ttu-id="431cc-120">メンバーの型</span><span class="sxs-lookup"><span data-stu-id="431cc-120">Member type</span></span>|<span data-ttu-id="431cc-121">ノート</span><span class="sxs-lookup"><span data-stu-id="431cc-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|<span data-ttu-id="431cc-122">property</span><span class="sxs-lookup"><span data-stu-id="431cc-122">Property</span></span>|<span data-ttu-id="431cc-123">None</span><span class="sxs-lookup"><span data-stu-id="431cc-123">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|<span data-ttu-id="431cc-124">メソッド</span><span class="sxs-lookup"><span data-stu-id="431cc-124">Method</span></span>|<span data-ttu-id="431cc-125">None</span><span class="sxs-lookup"><span data-stu-id="431cc-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|<span data-ttu-id="431cc-126">メソッド</span><span class="sxs-lookup"><span data-stu-id="431cc-126">Method</span></span>|<span data-ttu-id="431cc-127">None</span><span class="sxs-lookup"><span data-stu-id="431cc-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|<span data-ttu-id="431cc-128">メソッド</span><span class="sxs-lookup"><span data-stu-id="431cc-128">Method</span></span>|<span data-ttu-id="431cc-129">None</span><span class="sxs-lookup"><span data-stu-id="431cc-129">None</span></span>|  
  
 <span data-ttu-id="431cc-130">このコントロールのパターンに関連付けられているイベントはありません。</span><span class="sxs-lookup"><span data-stu-id="431cc-130">There are no events associated with this control pattern.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="431cc-131">例外</span><span class="sxs-lookup"><span data-stu-id="431cc-131">Exceptions</span></span>  
 <span data-ttu-id="431cc-132">プロバイダーは、次の例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="431cc-132">Provider must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="431cc-133">例外の種類</span><span class="sxs-lookup"><span data-stu-id="431cc-133">Exception type</span></span>|<span data-ttu-id="431cc-134">条件</span><span class="sxs-lookup"><span data-stu-id="431cc-134">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="431cc-135"><xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> または <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> が、サポートされているビュー コレクションのメンバーではないパラメーターで呼び出された場合。</span><span class="sxs-lookup"><span data-stu-id="431cc-135">When either <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> or <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> is called with a parameter that is not a member of the supported views collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="431cc-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="431cc-136">See also</span></span>

- [<span data-ttu-id="431cc-137">UI Automation コントロール パターンの概要</span><span class="sxs-lookup"><span data-stu-id="431cc-137">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="431cc-138">UI オートメーション プロバイダーでのコントロール パターンのサポート</span><span class="sxs-lookup"><span data-stu-id="431cc-138">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="431cc-139">クライアントの UI オートメーション コントロール パターン</span><span class="sxs-lookup"><span data-stu-id="431cc-139">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="431cc-140">UI Automation ツリーの概要</span><span class="sxs-lookup"><span data-stu-id="431cc-140">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="431cc-141">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="431cc-141">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
