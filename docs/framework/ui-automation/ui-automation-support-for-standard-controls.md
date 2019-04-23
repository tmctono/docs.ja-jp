---
title: UI オートメーションによる標準コントロールのサポート
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 3fde9779205ea7d0902ddd99ed192f097a159d2c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59221480"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="aa65b-102">UI オートメーションによる標準コントロールのサポート</span><span class="sxs-lookup"><span data-stu-id="aa65b-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="aa65b-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="aa65b-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="aa65b-104">に関する最新情報については[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を参照してください[Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)します。</span><span class="sxs-lookup"><span data-stu-id="aa65b-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="aa65b-105">このトピックでは、 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 、 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]、および [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]フレームワーク向けに開発されたアプリケーションの標準コントロールに対する [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] サポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aa65b-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="aa65b-106">Windows Presentation Foundation コントロール</span><span class="sxs-lookup"><span data-stu-id="aa65b-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="aa65b-107">ユーザー操作に関する情報やサポートを提供するすべての [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] コントロール要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を全面的にネイティブ サポートしています。</span><span class="sxs-lookup"><span data-stu-id="aa65b-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="aa65b-108">パネルなどのその他の要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]からは認識できません。</span><span class="sxs-lookup"><span data-stu-id="aa65b-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="aa65b-109">Win32 コントロール</span><span class="sxs-lookup"><span data-stu-id="aa65b-109">Win32 Controls</span></span>  
 <span data-ttu-id="aa65b-110">ほとんどの [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] コントロールは、UIAutomationClientsideProviders.dll のクライアント側プロバイダーによって [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] に公開されています。</span><span class="sxs-lookup"><span data-stu-id="aa65b-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="aa65b-111">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="aa65b-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="aa65b-112">完全なサポートは、ComCtrl32.dll のバージョン 6 ( [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] 以降で使用可能) のコントロールに対してのみ提供されています。</span><span class="sxs-lookup"><span data-stu-id="aa65b-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="aa65b-113">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aa65b-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="aa65b-114">クラス名</span><span class="sxs-lookup"><span data-stu-id="aa65b-114">Class name</span></span>|<span data-ttu-id="aa65b-115">コントロール型</span><span class="sxs-lookup"><span data-stu-id="aa65b-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="aa65b-116">ボタン</span><span class="sxs-lookup"><span data-stu-id="aa65b-116">Button</span></span>|<span data-ttu-id="aa65b-117">ボタン</span><span class="sxs-lookup"><span data-stu-id="aa65b-117">Button</span></span>|  
|<span data-ttu-id="aa65b-118">ボタン</span><span class="sxs-lookup"><span data-stu-id="aa65b-118">Button</span></span>|<span data-ttu-id="aa65b-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="aa65b-119">RadioButton</span></span>|  
|<span data-ttu-id="aa65b-120">ボタン</span><span class="sxs-lookup"><span data-stu-id="aa65b-120">Button</span></span>|<span data-ttu-id="aa65b-121">グループ化</span><span class="sxs-lookup"><span data-stu-id="aa65b-121">Group</span></span>|  
|<span data-ttu-id="aa65b-122">ボタン</span><span class="sxs-lookup"><span data-stu-id="aa65b-122">Button</span></span>|<span data-ttu-id="aa65b-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-123">CheckBox</span></span>|  
|<span data-ttu-id="aa65b-124">ボタン</span><span class="sxs-lookup"><span data-stu-id="aa65b-124">Button</span></span>|<span data-ttu-id="aa65b-125">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="aa65b-125">Hyperlink</span></span>|  
|<span data-ttu-id="aa65b-126">ボタン</span><span class="sxs-lookup"><span data-stu-id="aa65b-126">Button</span></span>|<span data-ttu-id="aa65b-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="aa65b-127">SplitButton</span></span>|  
|<span data-ttu-id="aa65b-128">ボタン</span><span class="sxs-lookup"><span data-stu-id="aa65b-128">Button</span></span>|<span data-ttu-id="aa65b-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-129">CheckBox</span></span>|  
|<span data-ttu-id="aa65b-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="aa65b-130">ComboBoxEx32</span></span>|<span data-ttu-id="aa65b-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-131">ComboBox</span></span>|  
|<span data-ttu-id="aa65b-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-132">ComboBox</span></span>|<span data-ttu-id="aa65b-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-133">ComboBox</span></span>|  
|<span data-ttu-id="aa65b-134">編集</span><span class="sxs-lookup"><span data-stu-id="aa65b-134">Edit</span></span>|<span data-ttu-id="aa65b-135">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="aa65b-135">Document</span></span>|  
|<span data-ttu-id="aa65b-136">編集</span><span class="sxs-lookup"><span data-stu-id="aa65b-136">Edit</span></span>|<span data-ttu-id="aa65b-137">編集</span><span class="sxs-lookup"><span data-stu-id="aa65b-137">Edit</span></span>|  
|<span data-ttu-id="aa65b-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="aa65b-138">SysLink</span></span>|<span data-ttu-id="aa65b-139">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="aa65b-139">Hyperlink</span></span>|  
|<span data-ttu-id="aa65b-140">スタティック</span><span class="sxs-lookup"><span data-stu-id="aa65b-140">Static</span></span>|<span data-ttu-id="aa65b-141">テキスト</span><span class="sxs-lookup"><span data-stu-id="aa65b-141">Text</span></span>|  
|<span data-ttu-id="aa65b-142">スタティック</span><span class="sxs-lookup"><span data-stu-id="aa65b-142">Static</span></span>|<span data-ttu-id="aa65b-143">イメージ</span><span class="sxs-lookup"><span data-stu-id="aa65b-143">Image</span></span>|  
|<span data-ttu-id="aa65b-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="aa65b-144">SysIPAddress32</span></span>|<span data-ttu-id="aa65b-145">カスタム</span><span class="sxs-lookup"><span data-stu-id="aa65b-145">Custom</span></span>|  
|<span data-ttu-id="aa65b-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="aa65b-146">SysHeader32</span></span>|<span data-ttu-id="aa65b-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="aa65b-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="aa65b-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="aa65b-148">SysListView32</span></span>|<span data-ttu-id="aa65b-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="aa65b-149">DataGrid</span></span>|  
|<span data-ttu-id="aa65b-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="aa65b-150">SysListView32</span></span>|<span data-ttu-id="aa65b-151">リスト</span><span class="sxs-lookup"><span data-stu-id="aa65b-151">List</span></span>|  
|<span data-ttu-id="aa65b-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-152">ListBox</span></span>|<span data-ttu-id="aa65b-153">リスト</span><span class="sxs-lookup"><span data-stu-id="aa65b-153">List</span></span>|  
|<span data-ttu-id="aa65b-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-154">ListBox</span></span>|<span data-ttu-id="aa65b-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="aa65b-155">ListItem</span></span>|  
|<span data-ttu-id="aa65b-156">#32768</span><span class="sxs-lookup"><span data-stu-id="aa65b-156">#32768</span></span>|<span data-ttu-id="aa65b-157">メニュー</span><span class="sxs-lookup"><span data-stu-id="aa65b-157">Menu</span></span>|  
|<span data-ttu-id="aa65b-158">#32768</span><span class="sxs-lookup"><span data-stu-id="aa65b-158">#32768</span></span>|<span data-ttu-id="aa65b-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="aa65b-159">MenuItem</span></span>|  
|<span data-ttu-id="aa65b-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="aa65b-160">msctls_progress32</span></span>|<span data-ttu-id="aa65b-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="aa65b-161">ProgressBar</span></span>|  
|<span data-ttu-id="aa65b-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="aa65b-162">RichEdit</span></span>|<span data-ttu-id="aa65b-163">ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="aa65b-163">Document.</span></span> <span data-ttu-id="aa65b-164">注を参照。</span><span class="sxs-lookup"><span data-stu-id="aa65b-164">See note.</span></span>|  
|<span data-ttu-id="aa65b-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="aa65b-165">RichEdit20A</span></span>|<span data-ttu-id="aa65b-166">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="aa65b-166">Document</span></span>|  
|<span data-ttu-id="aa65b-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="aa65b-167">RichEdit20W</span></span>|<span data-ttu-id="aa65b-168">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="aa65b-168">Document</span></span>|  
|<span data-ttu-id="aa65b-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="aa65b-169">RichEdit50W</span></span>|<span data-ttu-id="aa65b-170">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="aa65b-170">Document</span></span>|  
|<span data-ttu-id="aa65b-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="aa65b-171">ScrollBar</span></span>|<span data-ttu-id="aa65b-172">スライダー</span><span class="sxs-lookup"><span data-stu-id="aa65b-172">Slider</span></span>|  
|<span data-ttu-id="aa65b-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="aa65b-173">msctls_trackbar32</span></span>|<span data-ttu-id="aa65b-174">スライダー</span><span class="sxs-lookup"><span data-stu-id="aa65b-174">Slider</span></span>|  
|<span data-ttu-id="aa65b-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="aa65b-175">msctls_updown32</span></span>|<span data-ttu-id="aa65b-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="aa65b-176">Spinner</span></span>|  
|<span data-ttu-id="aa65b-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="aa65b-177">msctls_statusbar32</span></span>|<span data-ttu-id="aa65b-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="aa65b-178">StatusBar</span></span>|  
|<span data-ttu-id="aa65b-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="aa65b-179">SysTabControl32</span></span>|<span data-ttu-id="aa65b-180">タブ</span><span class="sxs-lookup"><span data-stu-id="aa65b-180">Tab</span></span>|  
|<span data-ttu-id="aa65b-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="aa65b-181">SysTabControl32</span></span>|<span data-ttu-id="aa65b-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="aa65b-182">TabItem</span></span>|  
|<span data-ttu-id="aa65b-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="aa65b-183">ToolbarWindow32</span></span>|<span data-ttu-id="aa65b-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="aa65b-184">ToolBar</span></span>|  
|<span data-ttu-id="aa65b-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="aa65b-185">ToolbarWindow32</span></span>|<span data-ttu-id="aa65b-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="aa65b-186">MenuItem</span></span>|  
|<span data-ttu-id="aa65b-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="aa65b-187">ToolbarWindow32</span></span>|<span data-ttu-id="aa65b-188">ボタン</span><span class="sxs-lookup"><span data-stu-id="aa65b-188">Button</span></span>|  
|<span data-ttu-id="aa65b-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="aa65b-189">ToolbarWindow32</span></span>|<span data-ttu-id="aa65b-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-190">CheckBox</span></span>|  
|<span data-ttu-id="aa65b-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="aa65b-191">ToolbarWindow32</span></span>|<span data-ttu-id="aa65b-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="aa65b-192">RadioButton</span></span>|  
|<span data-ttu-id="aa65b-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="aa65b-193">ToolbarWindow32</span></span>|<span data-ttu-id="aa65b-194">区切り記号</span><span class="sxs-lookup"><span data-stu-id="aa65b-194">Separator</span></span>|  
|<span data-ttu-id="aa65b-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="aa65b-195">tooltips_class32</span></span>|<span data-ttu-id="aa65b-196">ヒント</span><span class="sxs-lookup"><span data-stu-id="aa65b-196">ToolTip</span></span>|  
|<span data-ttu-id="aa65b-197">#32774</span><span class="sxs-lookup"><span data-stu-id="aa65b-197">#32774</span></span>|<span data-ttu-id="aa65b-198">ヒント</span><span class="sxs-lookup"><span data-stu-id="aa65b-198">ToolTip</span></span>|  
|<span data-ttu-id="aa65b-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="aa65b-199">ReBarWindow32</span></span>|<span data-ttu-id="aa65b-200">ツール バー</span><span class="sxs-lookup"><span data-stu-id="aa65b-200">Toolbar</span></span>|  
|<span data-ttu-id="aa65b-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="aa65b-201">SysTreeView32</span></span>|<span data-ttu-id="aa65b-202">ツリー</span><span class="sxs-lookup"><span data-stu-id="aa65b-202">Tree</span></span>|  
|<span data-ttu-id="aa65b-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="aa65b-203">SysTreeView32</span></span>|<span data-ttu-id="aa65b-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="aa65b-204">TreeItem</span></span>|  
  
 <span data-ttu-id="aa65b-205">**注** RichEdit コントロールは、 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] に付属するバージョン (RichEd20.dll バージョン 3.1 以降、および MsftEdit.dll バージョン 4.1 以降) に対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="aa65b-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="aa65b-206">次のコントロールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aa65b-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="aa65b-207">クラス名</span><span class="sxs-lookup"><span data-stu-id="aa65b-207">Class name</span></span>|<span data-ttu-id="aa65b-208">コントロール型</span><span class="sxs-lookup"><span data-stu-id="aa65b-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="aa65b-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="aa65b-209">SysAnimate32</span></span>|<span data-ttu-id="aa65b-210">イメージ</span><span class="sxs-lookup"><span data-stu-id="aa65b-210">Image</span></span>|  
|<span data-ttu-id="aa65b-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="aa65b-211">SysPager</span></span>|<span data-ttu-id="aa65b-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="aa65b-212">Spinner</span></span>|  
|<span data-ttu-id="aa65b-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="aa65b-213">SysDateTimePick32</span></span>|<span data-ttu-id="aa65b-214">カスタム</span><span class="sxs-lookup"><span data-stu-id="aa65b-214">Custom</span></span>|  
|<span data-ttu-id="aa65b-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="aa65b-215">SysMonthCal32</span></span>|<span data-ttu-id="aa65b-216">予定表</span><span class="sxs-lookup"><span data-stu-id="aa65b-216">Calendar</span></span>|  
|<span data-ttu-id="aa65b-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="aa65b-217">MS_WINNOTE</span></span>|<span data-ttu-id="aa65b-218">ヒント</span><span class="sxs-lookup"><span data-stu-id="aa65b-218">Tooltip</span></span>|  
|<span data-ttu-id="aa65b-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="aa65b-219">VBBubble</span></span>|<span data-ttu-id="aa65b-220">ヒント</span><span class="sxs-lookup"><span data-stu-id="aa65b-220">Tooltip</span></span>|  
|<span data-ttu-id="aa65b-221">ScrollBar (スタンドアロン コントロールとして使用される場合)</span><span class="sxs-lookup"><span data-stu-id="aa65b-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="aa65b-222">スライダー</span><span class="sxs-lookup"><span data-stu-id="aa65b-222">Slider</span></span>|  
|<span data-ttu-id="aa65b-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="aa65b-223">SuperGrid</span></span>|<span data-ttu-id="aa65b-224">カスタム</span><span class="sxs-lookup"><span data-stu-id="aa65b-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="aa65b-225">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="aa65b-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="aa65b-226">Windows フォーム コントロールに公開[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]UIAutomationClientsideProviders.dll のクライアント側プロバイダーを経由します。</span><span class="sxs-lookup"><span data-stu-id="aa65b-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="aa65b-227">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="aa65b-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="aa65b-228">通常、Windows フォーム コントロール用のマネージ ラッパー[!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]で一般的なコントロールがサポートされる[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="aa65b-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="aa65b-229">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aa65b-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="aa65b-230">クラス名</span><span class="sxs-lookup"><span data-stu-id="aa65b-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="aa65b-231">ボタン</span><span class="sxs-lookup"><span data-stu-id="aa65b-231">Button</span></span>|  
|<span data-ttu-id="aa65b-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-232">CheckBox</span></span>|  
|<span data-ttu-id="aa65b-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-233">CheckedListBox</span></span>|  
|<span data-ttu-id="aa65b-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="aa65b-234">ColorDialog</span></span>|  
|<span data-ttu-id="aa65b-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-235">ComboBox</span></span>|  
|<span data-ttu-id="aa65b-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="aa65b-236">FolderBrowser</span></span>|  
|<span data-ttu-id="aa65b-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="aa65b-237">FontDialog</span></span>|  
|<span data-ttu-id="aa65b-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-238">GroupBox</span></span>|  
|<span data-ttu-id="aa65b-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="aa65b-239">HscrollBar</span></span>|  
|<span data-ttu-id="aa65b-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="aa65b-240">ImageList</span></span>|  
|<span data-ttu-id="aa65b-241">group1</span><span class="sxs-lookup"><span data-stu-id="aa65b-241">Label</span></span>|  
|<span data-ttu-id="aa65b-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-242">ListBox</span></span>|  
|<span data-ttu-id="aa65b-243">ListView</span><span class="sxs-lookup"><span data-stu-id="aa65b-243">ListView</span></span>|  
|<span data-ttu-id="aa65b-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="aa65b-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="aa65b-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="aa65b-245">MonthCalendar</span></span>|  
|<span data-ttu-id="aa65b-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="aa65b-246">NotifyIcon</span></span>|  
|<span data-ttu-id="aa65b-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="aa65b-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="aa65b-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="aa65b-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="aa65b-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="aa65b-249">PrintDialog</span></span>|  
|<span data-ttu-id="aa65b-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="aa65b-250">ProgressBar</span></span>|  
|<span data-ttu-id="aa65b-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="aa65b-251">RadioButton</span></span>|  
|<span data-ttu-id="aa65b-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-252">RichTextBox</span></span>|  
|<span data-ttu-id="aa65b-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="aa65b-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="aa65b-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="aa65b-254">ScrollableControl</span></span>|  
|<span data-ttu-id="aa65b-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="aa65b-255">SoundPlayer</span></span>|  
|<span data-ttu-id="aa65b-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="aa65b-256">StatusBar</span></span>|  
|<span data-ttu-id="aa65b-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="aa65b-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="aa65b-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-258">TextBox</span></span>|  
|<span data-ttu-id="aa65b-259">タイマー</span><span class="sxs-lookup"><span data-stu-id="aa65b-259">Timer</span></span>|  
|<span data-ttu-id="aa65b-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="aa65b-260">Toolbar</span></span>|  
|<span data-ttu-id="aa65b-261">ヒント</span><span class="sxs-lookup"><span data-stu-id="aa65b-261">ToolTip</span></span>|  
|<span data-ttu-id="aa65b-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="aa65b-262">TrackBar</span></span>|  
|<span data-ttu-id="aa65b-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="aa65b-263">TreeView</span></span>|  
|<span data-ttu-id="aa65b-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="aa65b-264">VscrollBar</span></span>|  
|<span data-ttu-id="aa65b-265">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="aa65b-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="aa65b-266">次に示すコントロールは、 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] のサポートによってのみ、 [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)]に公開されています。</span><span class="sxs-lookup"><span data-stu-id="aa65b-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="aa65b-267">一部の機能が使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="aa65b-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="aa65b-268">コントロール名</span><span class="sxs-lookup"><span data-stu-id="aa65b-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="aa65b-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="aa65b-269">BindingSource</span></span>|  
|<span data-ttu-id="aa65b-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="aa65b-270">DataGrid</span></span>|  
|<span data-ttu-id="aa65b-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="aa65b-271">DataGridView</span></span>|  
|<span data-ttu-id="aa65b-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="aa65b-272">DataNavigator</span></span>|  
|<span data-ttu-id="aa65b-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="aa65b-273">DomainUpDown</span></span>|  
|<span data-ttu-id="aa65b-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="aa65b-274">ErrorProvider</span></span>|  
|<span data-ttu-id="aa65b-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="aa65b-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="aa65b-276">フォーム</span><span class="sxs-lookup"><span data-stu-id="aa65b-276">Form</span></span>|  
|<span data-ttu-id="aa65b-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="aa65b-277">LinkLabel</span></span>|  
|<span data-ttu-id="aa65b-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="aa65b-278">HelpProvider</span></span>|  
|<span data-ttu-id="aa65b-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="aa65b-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="aa65b-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="aa65b-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="aa65b-281">NumericUpDown</span></span>|  
|<span data-ttu-id="aa65b-282">パネル</span><span class="sxs-lookup"><span data-stu-id="aa65b-282">Panel</span></span>|  
|<span data-ttu-id="aa65b-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="aa65b-283">PictureBox</span></span>|  
|<span data-ttu-id="aa65b-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="aa65b-284">PrintDocument</span></span>|  
|<span data-ttu-id="aa65b-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="aa65b-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="aa65b-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="aa65b-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="aa65b-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="aa65b-287">PropertyGrid</span></span>|  
|<span data-ttu-id="aa65b-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="aa65b-288">UserControl</span></span>|  
|<span data-ttu-id="aa65b-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="aa65b-289">ToolStrip</span></span>|  
|<span data-ttu-id="aa65b-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="aa65b-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="aa65b-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="aa65b-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="aa65b-292">スプリッター</span><span class="sxs-lookup"><span data-stu-id="aa65b-292">Splitter</span></span>|  
|<span data-ttu-id="aa65b-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="aa65b-293">RaftingContainer</span></span>|  
|<span data-ttu-id="aa65b-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="aa65b-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa65b-295">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa65b-295">See also</span></span>

- [<span data-ttu-id="aa65b-296">UI オートメーション コントロール型</span><span class="sxs-lookup"><span data-stu-id="aa65b-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
