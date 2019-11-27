---
title: UI オートメーション Table コントロール パターンの実装
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
ms.openlocfilehash: 8e929f181255f6738261533fa3261187ebe3c6ff
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447100"
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a><span data-ttu-id="d1472-102">UI オートメーション Table コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="d1472-102">Implementing the UI Automation Table Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="d1472-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="d1472-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d1472-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI オートメーション](/windows/win32/winauto/entry-uiauto-win32)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1472-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="d1472-105">このトピックでは、プロパティ、メソッド、イベントに関する情報など、 <xref:System.Windows.Automation.Provider.ITableProvider>の実装のためのガイドラインと規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1472-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="d1472-106">その他のリファレンスへのリンクは、概要の最後に記載します。</span><span class="sxs-lookup"><span data-stu-id="d1472-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="d1472-107"><xref:System.Windows.Automation.TablePattern> コントロール パターンは、子要素のコレクションのコンテナーとして機能するコントロールをサポートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="d1472-107">The <xref:System.Windows.Automation.TablePattern> control pattern is used to support controls that act as containers for a collection of child elements.</span></span> <span data-ttu-id="d1472-108">この要素の子には <xref:System.Windows.Automation.Provider.ITableItemProvider> を実装する必要があります。また、この要素の子は、行と列で表現できる 2 次元の論理座標システムで編成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="d1472-108">The children of this element must implement <xref:System.Windows.Automation.Provider.ITableItemProvider> and be organized in a two-dimensional logical coordinate system that can be traversed by row and column.</span></span> <span data-ttu-id="d1472-109">このコントロール パターンは、<xref:System.Windows.Automation.Provider.IGridProvider> を実装するコントロールが各子要素の列ヘッダーまたは行ヘッダーの関係を公開する必要もあることを除いて、<xref:System.Windows.Automation.Provider.ITableProvider> に似ています。</span><span class="sxs-lookup"><span data-stu-id="d1472-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridProvider>, with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableProvider> must also expose a column and/or row header relationship for each child element.</span></span> <span data-ttu-id="d1472-110">このコントロール パターンを実装するコントロールの例については、「 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1472-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="d1472-111">実装のガイドラインと規則</span><span class="sxs-lookup"><span data-stu-id="d1472-111">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="d1472-112">Table コントロール パターンを実装する場合は、次のガイドラインと規則に留意してください。</span><span class="sxs-lookup"><span data-stu-id="d1472-112">When implementing the Table control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="d1472-113">個々のセルのコンテンツへのアクセスは、2 次元論理座標系または <xref:System.Windows.Automation.Provider.IGridProvider> の必要な同時実装によって提供される配列を経由します。</span><span class="sxs-lookup"><span data-stu-id="d1472-113">Access to the content of individual cells is through a two-dimensional logical coordinate system or array provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span>  
  
- <span data-ttu-id="d1472-114">列ヘッダーまたは行ヘッダーは、テーブル オブジェクト内に含めることも、テーブル オブジェクトに関連付けられた別のヘッダー オブジェクトにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d1472-114">A column or row header can be contained within a table object or be a separate header object that is associated with a table object.</span></span>  
  
- <span data-ttu-id="d1472-115">列ヘッダーと行ヘッダーには、プライマリ ヘッダーだけでなく、任意の補助ヘッダーも含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d1472-115">Column and row headers may include both a primary header as well as any supporting headers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1472-116">この概念は、ユーザーが "First name" 列を定義した Microsoft Excel スプレッドシートで明らかになります。</span><span class="sxs-lookup"><span data-stu-id="d1472-116">This concept becomes evident in a Microsoft Excel spreadsheet where a user has defined a "First name" column.</span></span> <span data-ttu-id="d1472-117">これで、この列のヘッダーは、ユーザーが定義した [ファースト ネーム] ヘッダーとアプリケーションによって割り当てられたその列の英数字指定の 2 つになります。</span><span class="sxs-lookup"><span data-stu-id="d1472-117">This column now has two headers—the "First name" header defined by the user and the alphanumeric designation for that column assigned by the application.</span></span>  
  
- <span data-ttu-id="d1472-118">関連するグリッド機能について[は、「UI オートメーション Grid コントロールパターンの実装](implementing-the-ui-automation-grid-control-pattern.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1472-118">See [Implementing the UI Automation Grid Control Pattern](implementing-the-ui-automation-grid-control-pattern.md) for related grid functionality.</span></span>  
  
 <span data-ttu-id="d1472-119">![複合ヘッダー項目を含むテーブル。](./media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span><span class="sxs-lookup"><span data-stu-id="d1472-119">![Table with complex header items.](./media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span></span>  
<span data-ttu-id="d1472-120">列ヘッダーが複雑なテーブルの例</span><span class="sxs-lookup"><span data-stu-id="d1472-120">Example of a Table with Complex Column Headers</span></span>  
  
 <span data-ttu-id="d1472-121">![あいまいな RowOrColumnMajor プロパティを持つテーブルです。](./media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span><span class="sxs-lookup"><span data-stu-id="d1472-121">![Table with ambiguous RowOrColumnMajor property.](./media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span></span>  
<span data-ttu-id="d1472-122">RowOrColumnMajor プロパティがあいまいなテーブルの例</span><span class="sxs-lookup"><span data-stu-id="d1472-122">Example of a Table with Ambiguous RowOrColumnMajor Property</span></span>  
  
<a name="Required_Members_for_ITableProvider"></a>   
## <a name="required-members-for-itableprovider"></a><span data-ttu-id="d1472-123">ITableProvider の必須メンバー</span><span class="sxs-lookup"><span data-stu-id="d1472-123">Required Members for ITableProvider</span></span>  
 <span data-ttu-id="d1472-124">ITableProvider インターフェイスには、次のプロパティとメソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="d1472-124">The following properties and methods are required for the ITableProvider interface.</span></span>  
  
|<span data-ttu-id="d1472-125">必須メンバー</span><span class="sxs-lookup"><span data-stu-id="d1472-125">Required members</span></span>|<span data-ttu-id="d1472-126">メンバーの種類</span><span class="sxs-lookup"><span data-stu-id="d1472-126">Member type</span></span>|<span data-ttu-id="d1472-127">説明</span><span class="sxs-lookup"><span data-stu-id="d1472-127">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|<span data-ttu-id="d1472-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d1472-128">Property</span></span>|<span data-ttu-id="d1472-129">なし</span><span class="sxs-lookup"><span data-stu-id="d1472-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|<span data-ttu-id="d1472-130">メソッド</span><span class="sxs-lookup"><span data-stu-id="d1472-130">Method</span></span>|<span data-ttu-id="d1472-131">なし</span><span class="sxs-lookup"><span data-stu-id="d1472-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|<span data-ttu-id="d1472-132">メソッド</span><span class="sxs-lookup"><span data-stu-id="d1472-132">Method</span></span>|<span data-ttu-id="d1472-133">なし</span><span class="sxs-lookup"><span data-stu-id="d1472-133">None</span></span>|  
  
 <span data-ttu-id="d1472-134">このコントロール パターンには、関連するイベントがありません。</span><span class="sxs-lookup"><span data-stu-id="d1472-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="d1472-135">例外</span><span class="sxs-lookup"><span data-stu-id="d1472-135">Exceptions</span></span>  
 <span data-ttu-id="d1472-136">このコントロール パターンに関連付けられた例外はありません。</span><span class="sxs-lookup"><span data-stu-id="d1472-136">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1472-137">参照</span><span class="sxs-lookup"><span data-stu-id="d1472-137">See also</span></span>

- [<span data-ttu-id="d1472-138">UI Automation コントロール パターンの概要</span><span class="sxs-lookup"><span data-stu-id="d1472-138">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="d1472-139">UI オートメーション プロバイダーでのコントロール パターンのサポート</span><span class="sxs-lookup"><span data-stu-id="d1472-139">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="d1472-140">UI Automation Control Patterns for Clients</span><span class="sxs-lookup"><span data-stu-id="d1472-140">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="d1472-141">UI オートメーション TableItem コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="d1472-141">Implementing the UI Automation TableItem Control Pattern</span></span>](implementing-the-ui-automation-tableitem-control-pattern.md)
- [<span data-ttu-id="d1472-142">UI オートメーション Grid コントロール パターンの実装</span><span class="sxs-lookup"><span data-stu-id="d1472-142">Implementing the UI Automation Grid Control Pattern</span></span>](implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="d1472-143">UI Automation ツリーの概要</span><span class="sxs-lookup"><span data-stu-id="d1472-143">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="d1472-144">UI オートメーションにおけるキャッシュの使用</span><span class="sxs-lookup"><span data-stu-id="d1472-144">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
