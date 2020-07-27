---
title: UI オートメーション MultipleView コントロール パターンの実装
description: UI オートメーションで、多重ビューコントロールパターンを実装するためのガイドラインと規則を確認します。 IMultipleViewProvider インターフェイスに必要なメンバーを参照してください。
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
ms.openlocfilehash: 0d65d57637891fcb1307f5ee83a417941ff323fb
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168224"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a><span data-ttu-id="07a67-104">UI オートメーション MultipleView コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="07a67-104">Implementing the UI Automation MultipleView Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="07a67-105">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="07a67-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="07a67-106">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI オートメーション](/windows/win32/winauto/entry-uiauto-win32)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="07a67-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="07a67-107">このトピックでは、イベントおよびプロパティに関する情報など、 <xref:System.Windows.Automation.Provider.IMultipleViewProvider>の実装のためのガイドラインと規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="07a67-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, including information about events and properties.</span></span> <span data-ttu-id="07a67-108">その他のリファレンスへのリンクは、トピックの最後に記載します。</span><span class="sxs-lookup"><span data-stu-id="07a67-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="07a67-109"><xref:System.Windows.Automation.MultipleViewPattern> コントロール パターンは、同じ情報セットまたは子コントロールの複数の表現を提供し、それらの表現を切り替えることができるコントロールをサポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="07a67-109">The <xref:System.Windows.Automation.MultipleViewPattern> control pattern is used to support controls that provide, and are able to switch between, multiple representations of the same set of information or child controls.</span></span>  
  
 <span data-ttu-id="07a67-110">複数のビューを表示できるコントロールの例としては、リストビュー (コンテンツをサムネイルとして表示できるもの) があります。タイル、アイコン、または詳細)、Microsoft Excel グラフ (円グラフ、折れ線グラフ、横棒グラフ、数式を含むセル値)、Microsoft Word 文書 (標準、Web レイアウト、印刷レイアウト、閲覧レイアウト、アウトライン)、Microsoft Outlook カレンダー (年、月、週、日)、および Microsoft Windows Media Player スキン。</span><span class="sxs-lookup"><span data-stu-id="07a67-110">Examples of controls that can present multiple views include the list view (which can show its contents as thumbnails, tiles, icons, or details), Microsoft Excel charts (pie, line, bar, cell value with a formula), Microsoft Word documents (normal, Web layout, print layout, reading layout, outline), Microsoft Outlook calendar (year, month, week, day), and Microsoft Windows Media Player skins.</span></span> <span data-ttu-id="07a67-111">サポートされるビューはコントロールの開発者によって決定され、各コントロールに固有です。</span><span class="sxs-lookup"><span data-stu-id="07a67-111">The supported views are determined by the control developer and are specific to each control.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="07a67-112">実装のガイドラインと規則</span><span class="sxs-lookup"><span data-stu-id="07a67-112">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="07a67-113">Multiple View コントロール パターンを実装する場合は、次のガイドラインと規則にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="07a67-113">When implementing the Multiple View control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="07a67-114">現在のビューを管理するコンテナーが現在のビューを提供するコントロールとは異なる場合は、現在のビューを管理するためのコンテナーにも<xref:System.Windows.Automation.Provider.IMultipleViewProvider> を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a67-114"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> should also be implemented on a container that manages the current view if it is different from a control that provides the current view.</span></span> <span data-ttu-id="07a67-115">たとえば、Windows エクスプローラーには現在のフォルダーのコンテンツの List コントロールが含まれていますが、そのコントロールのビューは Windows エクスプローラーのアプリケーションから管理されています。</span><span class="sxs-lookup"><span data-stu-id="07a67-115">For example, Windows Explorer contains a List control for the current folder content while the view for the control is managed from the Windows Explorer application.</span></span>  
  
- <span data-ttu-id="07a67-116">自身のコンテンツを並べ替えることができるコントロールは、複数のビューをサポートしているとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="07a67-116">A control that is able to sort its content is not considered to support multiple views.</span></span>  
  
- <span data-ttu-id="07a67-117">ビューのコレクションは、インスタンス間で同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a67-117">The collection of views must be identical across instances.</span></span>  
  
- <span data-ttu-id="07a67-118">ビューの名前は、読み上げ、ブライユ点字、その他の人間が判読できるアプリケーションでの使用に適した名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a67-118">View names must be suitable for use in Text to Speech, Braille, and other human-readable applications.</span></span>  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>
## <a name="required-members-for-imultipleviewprovider"></a><span data-ttu-id="07a67-119">IMultipleViewProvider の必須メンバー</span><span class="sxs-lookup"><span data-stu-id="07a67-119">Required Members for IMultipleViewProvider</span></span>  
 <span data-ttu-id="07a67-120">IMultipleViewProvider の実装には、次のプロパティとメソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="07a67-120">The following properties and methods are required for implementing IMultipleViewProvider.</span></span>  
  
|<span data-ttu-id="07a67-121">必須メンバー</span><span class="sxs-lookup"><span data-stu-id="07a67-121">Required members</span></span>|<span data-ttu-id="07a67-122">メンバーの型</span><span class="sxs-lookup"><span data-stu-id="07a67-122">Member type</span></span>|<span data-ttu-id="07a67-123">メモ</span><span class="sxs-lookup"><span data-stu-id="07a67-123">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|<span data-ttu-id="07a67-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="07a67-124">Property</span></span>|<span data-ttu-id="07a67-125">なし</span><span class="sxs-lookup"><span data-stu-id="07a67-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|<span data-ttu-id="07a67-126">メソッド</span><span class="sxs-lookup"><span data-stu-id="07a67-126">Method</span></span>|<span data-ttu-id="07a67-127">なし</span><span class="sxs-lookup"><span data-stu-id="07a67-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|<span data-ttu-id="07a67-128">メソッド</span><span class="sxs-lookup"><span data-stu-id="07a67-128">Method</span></span>|<span data-ttu-id="07a67-129">なし</span><span class="sxs-lookup"><span data-stu-id="07a67-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|<span data-ttu-id="07a67-130">メソッド</span><span class="sxs-lookup"><span data-stu-id="07a67-130">Method</span></span>|<span data-ttu-id="07a67-131">なし</span><span class="sxs-lookup"><span data-stu-id="07a67-131">None</span></span>|  
  
 <span data-ttu-id="07a67-132">このコントロールのパターンに関連付けられているイベントはありません。</span><span class="sxs-lookup"><span data-stu-id="07a67-132">There are no events associated with this control pattern.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="07a67-133">例外</span><span class="sxs-lookup"><span data-stu-id="07a67-133">Exceptions</span></span>  
 <span data-ttu-id="07a67-134">プロバイダーは、次の例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a67-134">Provider must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="07a67-135">例外の種類</span><span class="sxs-lookup"><span data-stu-id="07a67-135">Exception type</span></span>|<span data-ttu-id="07a67-136">条件</span><span class="sxs-lookup"><span data-stu-id="07a67-136">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="07a67-137"><xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> または <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> が、サポートされているビュー コレクションのメンバーではないパラメーターで呼び出された場合。</span><span class="sxs-lookup"><span data-stu-id="07a67-137">When either <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> or <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> is called with a parameter that is not a member of the supported views collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07a67-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="07a67-138">See also</span></span>

- [<span data-ttu-id="07a67-139">UI オートメーション コントロール パターンの概要</span><span class="sxs-lookup"><span data-stu-id="07a67-139">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="07a67-140">UI オートメーション プロバイダーでのコントロール パターンのサポート</span><span class="sxs-lookup"><span data-stu-id="07a67-140">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="07a67-141">クライアントの UI オートメーション コントロール パターン</span><span class="sxs-lookup"><span data-stu-id="07a67-141">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="07a67-142">UI オートメーション ツリーの概要</span><span class="sxs-lookup"><span data-stu-id="07a67-142">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="07a67-143">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="07a67-143">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
