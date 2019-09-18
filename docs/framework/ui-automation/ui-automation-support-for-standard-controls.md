---
title: UI オートメーションによる標準コントロールのサポート
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 6cbf31c8a1cdf6e853e56445d22f4a7513bd1859
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71042007"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="e8e12-102">UI オートメーションによる標準コントロールのサポート</span><span class="sxs-lookup"><span data-stu-id="e8e12-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="e8e12-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="e8e12-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e8e12-104">の最新情報[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]については[、「Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="e8e12-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="e8e12-105">このトピックでは、 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 、 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]、および [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]フレームワーク向けに開発されたアプリケーションの標準コントロールに対する [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] サポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e8e12-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="e8e12-106">Windows Presentation Foundation コントロール</span><span class="sxs-lookup"><span data-stu-id="e8e12-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="e8e12-107">ユーザー操作に関する情報やサポートを提供するすべての [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] コントロール要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を全面的にネイティブ サポートしています。</span><span class="sxs-lookup"><span data-stu-id="e8e12-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="e8e12-108">パネルなどのその他の要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]からは認識できません。</span><span class="sxs-lookup"><span data-stu-id="e8e12-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="e8e12-109">Win32 コントロール</span><span class="sxs-lookup"><span data-stu-id="e8e12-109">Win32 Controls</span></span>  
 <span data-ttu-id="e8e12-110">ほとんどの [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] コントロールは、UIAutomationClientsideProviders.dll のクライアント側プロバイダーによって [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] に公開されています。</span><span class="sxs-lookup"><span data-stu-id="e8e12-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="e8e12-111">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="e8e12-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="e8e12-112">完全なサポートは、ComCtrl32.dll のバージョン 6 ( [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] 以降で使用可能) のコントロールに対してのみ提供されています。</span><span class="sxs-lookup"><span data-stu-id="e8e12-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="e8e12-113">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e8e12-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="e8e12-114">クラス名</span><span class="sxs-lookup"><span data-stu-id="e8e12-114">Class name</span></span>|<span data-ttu-id="e8e12-115">コントロール型</span><span class="sxs-lookup"><span data-stu-id="e8e12-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="e8e12-116">ボタン</span><span class="sxs-lookup"><span data-stu-id="e8e12-116">Button</span></span>|<span data-ttu-id="e8e12-117">ボタン</span><span class="sxs-lookup"><span data-stu-id="e8e12-117">Button</span></span>|  
|<span data-ttu-id="e8e12-118">ボタン</span><span class="sxs-lookup"><span data-stu-id="e8e12-118">Button</span></span>|<span data-ttu-id="e8e12-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="e8e12-119">RadioButton</span></span>|  
|<span data-ttu-id="e8e12-120">ボタン</span><span class="sxs-lookup"><span data-stu-id="e8e12-120">Button</span></span>|<span data-ttu-id="e8e12-121">グループ化</span><span class="sxs-lookup"><span data-stu-id="e8e12-121">Group</span></span>|  
|<span data-ttu-id="e8e12-122">ボタン</span><span class="sxs-lookup"><span data-stu-id="e8e12-122">Button</span></span>|<span data-ttu-id="e8e12-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-123">CheckBox</span></span>|  
|<span data-ttu-id="e8e12-124">ボタン</span><span class="sxs-lookup"><span data-stu-id="e8e12-124">Button</span></span>|<span data-ttu-id="e8e12-125">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="e8e12-125">Hyperlink</span></span>|  
|<span data-ttu-id="e8e12-126">ボタン</span><span class="sxs-lookup"><span data-stu-id="e8e12-126">Button</span></span>|<span data-ttu-id="e8e12-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="e8e12-127">SplitButton</span></span>|  
|<span data-ttu-id="e8e12-128">ボタン</span><span class="sxs-lookup"><span data-stu-id="e8e12-128">Button</span></span>|<span data-ttu-id="e8e12-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-129">CheckBox</span></span>|  
|<span data-ttu-id="e8e12-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="e8e12-130">ComboBoxEx32</span></span>|<span data-ttu-id="e8e12-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-131">ComboBox</span></span>|  
|<span data-ttu-id="e8e12-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-132">ComboBox</span></span>|<span data-ttu-id="e8e12-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-133">ComboBox</span></span>|  
|<span data-ttu-id="e8e12-134">編集</span><span class="sxs-lookup"><span data-stu-id="e8e12-134">Edit</span></span>|<span data-ttu-id="e8e12-135">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="e8e12-135">Document</span></span>|  
|<span data-ttu-id="e8e12-136">編集</span><span class="sxs-lookup"><span data-stu-id="e8e12-136">Edit</span></span>|<span data-ttu-id="e8e12-137">編集</span><span class="sxs-lookup"><span data-stu-id="e8e12-137">Edit</span></span>|  
|<span data-ttu-id="e8e12-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="e8e12-138">SysLink</span></span>|<span data-ttu-id="e8e12-139">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="e8e12-139">Hyperlink</span></span>|  
|<span data-ttu-id="e8e12-140">スタティック</span><span class="sxs-lookup"><span data-stu-id="e8e12-140">Static</span></span>|<span data-ttu-id="e8e12-141">テキスト</span><span class="sxs-lookup"><span data-stu-id="e8e12-141">Text</span></span>|  
|<span data-ttu-id="e8e12-142">スタティック</span><span class="sxs-lookup"><span data-stu-id="e8e12-142">Static</span></span>|<span data-ttu-id="e8e12-143">イメージ</span><span class="sxs-lookup"><span data-stu-id="e8e12-143">Image</span></span>|  
|<span data-ttu-id="e8e12-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="e8e12-144">SysIPAddress32</span></span>|<span data-ttu-id="e8e12-145">カスタム</span><span class="sxs-lookup"><span data-stu-id="e8e12-145">Custom</span></span>|  
|<span data-ttu-id="e8e12-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="e8e12-146">SysHeader32</span></span>|<span data-ttu-id="e8e12-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="e8e12-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="e8e12-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="e8e12-148">SysListView32</span></span>|<span data-ttu-id="e8e12-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="e8e12-149">DataGrid</span></span>|  
|<span data-ttu-id="e8e12-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="e8e12-150">SysListView32</span></span>|<span data-ttu-id="e8e12-151">List</span><span class="sxs-lookup"><span data-stu-id="e8e12-151">List</span></span>|  
|<span data-ttu-id="e8e12-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-152">ListBox</span></span>|<span data-ttu-id="e8e12-153">List</span><span class="sxs-lookup"><span data-stu-id="e8e12-153">List</span></span>|  
|<span data-ttu-id="e8e12-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-154">ListBox</span></span>|<span data-ttu-id="e8e12-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="e8e12-155">ListItem</span></span>|  
|<span data-ttu-id="e8e12-156">#32768</span><span class="sxs-lookup"><span data-stu-id="e8e12-156">#32768</span></span>|<span data-ttu-id="e8e12-157">メニュー</span><span class="sxs-lookup"><span data-stu-id="e8e12-157">Menu</span></span>|  
|<span data-ttu-id="e8e12-158">#32768</span><span class="sxs-lookup"><span data-stu-id="e8e12-158">#32768</span></span>|<span data-ttu-id="e8e12-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="e8e12-159">MenuItem</span></span>|  
|<span data-ttu-id="e8e12-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="e8e12-160">msctls_progress32</span></span>|<span data-ttu-id="e8e12-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="e8e12-161">ProgressBar</span></span>|  
|<span data-ttu-id="e8e12-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="e8e12-162">RichEdit</span></span>|<span data-ttu-id="e8e12-163">ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="e8e12-163">Document.</span></span> <span data-ttu-id="e8e12-164">注を参照。</span><span class="sxs-lookup"><span data-stu-id="e8e12-164">See note.</span></span>|  
|<span data-ttu-id="e8e12-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="e8e12-165">RichEdit20A</span></span>|<span data-ttu-id="e8e12-166">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="e8e12-166">Document</span></span>|  
|<span data-ttu-id="e8e12-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="e8e12-167">RichEdit20W</span></span>|<span data-ttu-id="e8e12-168">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="e8e12-168">Document</span></span>|  
|<span data-ttu-id="e8e12-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="e8e12-169">RichEdit50W</span></span>|<span data-ttu-id="e8e12-170">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="e8e12-170">Document</span></span>|  
|<span data-ttu-id="e8e12-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="e8e12-171">ScrollBar</span></span>|<span data-ttu-id="e8e12-172">スライダー</span><span class="sxs-lookup"><span data-stu-id="e8e12-172">Slider</span></span>|  
|<span data-ttu-id="e8e12-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="e8e12-173">msctls_trackbar32</span></span>|<span data-ttu-id="e8e12-174">スライダー</span><span class="sxs-lookup"><span data-stu-id="e8e12-174">Slider</span></span>|  
|<span data-ttu-id="e8e12-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="e8e12-175">msctls_updown32</span></span>|<span data-ttu-id="e8e12-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="e8e12-176">Spinner</span></span>|  
|<span data-ttu-id="e8e12-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="e8e12-177">msctls_statusbar32</span></span>|<span data-ttu-id="e8e12-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="e8e12-178">StatusBar</span></span>|  
|<span data-ttu-id="e8e12-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="e8e12-179">SysTabControl32</span></span>|<span data-ttu-id="e8e12-180">Tab</span><span class="sxs-lookup"><span data-stu-id="e8e12-180">Tab</span></span>|  
|<span data-ttu-id="e8e12-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="e8e12-181">SysTabControl32</span></span>|<span data-ttu-id="e8e12-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="e8e12-182">TabItem</span></span>|  
|<span data-ttu-id="e8e12-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="e8e12-183">ToolbarWindow32</span></span>|<span data-ttu-id="e8e12-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="e8e12-184">ToolBar</span></span>|  
|<span data-ttu-id="e8e12-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="e8e12-185">ToolbarWindow32</span></span>|<span data-ttu-id="e8e12-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="e8e12-186">MenuItem</span></span>|  
|<span data-ttu-id="e8e12-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="e8e12-187">ToolbarWindow32</span></span>|<span data-ttu-id="e8e12-188">ボタン</span><span class="sxs-lookup"><span data-stu-id="e8e12-188">Button</span></span>|  
|<span data-ttu-id="e8e12-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="e8e12-189">ToolbarWindow32</span></span>|<span data-ttu-id="e8e12-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-190">CheckBox</span></span>|  
|<span data-ttu-id="e8e12-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="e8e12-191">ToolbarWindow32</span></span>|<span data-ttu-id="e8e12-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="e8e12-192">RadioButton</span></span>|  
|<span data-ttu-id="e8e12-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="e8e12-193">ToolbarWindow32</span></span>|<span data-ttu-id="e8e12-194">区切り記号</span><span class="sxs-lookup"><span data-stu-id="e8e12-194">Separator</span></span>|  
|<span data-ttu-id="e8e12-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="e8e12-195">tooltips_class32</span></span>|<span data-ttu-id="e8e12-196">ヒント</span><span class="sxs-lookup"><span data-stu-id="e8e12-196">ToolTip</span></span>|  
|<span data-ttu-id="e8e12-197">#32774</span><span class="sxs-lookup"><span data-stu-id="e8e12-197">#32774</span></span>|<span data-ttu-id="e8e12-198">ヒント</span><span class="sxs-lookup"><span data-stu-id="e8e12-198">ToolTip</span></span>|  
|<span data-ttu-id="e8e12-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="e8e12-199">ReBarWindow32</span></span>|<span data-ttu-id="e8e12-200">ツール バー</span><span class="sxs-lookup"><span data-stu-id="e8e12-200">Toolbar</span></span>|  
|<span data-ttu-id="e8e12-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="e8e12-201">SysTreeView32</span></span>|<span data-ttu-id="e8e12-202">ツリー</span><span class="sxs-lookup"><span data-stu-id="e8e12-202">Tree</span></span>|  
|<span data-ttu-id="e8e12-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="e8e12-203">SysTreeView32</span></span>|<span data-ttu-id="e8e12-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="e8e12-204">TreeItem</span></span>|  
  
 <span data-ttu-id="e8e12-205">**注** RichEdit コントロールは、 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] に付属するバージョン (RichEd20.dll バージョン 3.1 以降、および MsftEdit.dll バージョン 4.1 以降) に対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e8e12-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="e8e12-206">次のコントロールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e8e12-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="e8e12-207">クラス名</span><span class="sxs-lookup"><span data-stu-id="e8e12-207">Class name</span></span>|<span data-ttu-id="e8e12-208">コントロール型</span><span class="sxs-lookup"><span data-stu-id="e8e12-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="e8e12-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="e8e12-209">SysAnimate32</span></span>|<span data-ttu-id="e8e12-210">イメージ</span><span class="sxs-lookup"><span data-stu-id="e8e12-210">Image</span></span>|  
|<span data-ttu-id="e8e12-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="e8e12-211">SysPager</span></span>|<span data-ttu-id="e8e12-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="e8e12-212">Spinner</span></span>|  
|<span data-ttu-id="e8e12-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="e8e12-213">SysDateTimePick32</span></span>|<span data-ttu-id="e8e12-214">カスタム</span><span class="sxs-lookup"><span data-stu-id="e8e12-214">Custom</span></span>|  
|<span data-ttu-id="e8e12-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="e8e12-215">SysMonthCal32</span></span>|<span data-ttu-id="e8e12-216">予定表</span><span class="sxs-lookup"><span data-stu-id="e8e12-216">Calendar</span></span>|  
|<span data-ttu-id="e8e12-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="e8e12-217">MS_WINNOTE</span></span>|<span data-ttu-id="e8e12-218">ヒント</span><span class="sxs-lookup"><span data-stu-id="e8e12-218">Tooltip</span></span>|  
|<span data-ttu-id="e8e12-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="e8e12-219">VBBubble</span></span>|<span data-ttu-id="e8e12-220">ヒント</span><span class="sxs-lookup"><span data-stu-id="e8e12-220">Tooltip</span></span>|  
|<span data-ttu-id="e8e12-221">ScrollBar (スタンドアロン コントロールとして使用される場合)</span><span class="sxs-lookup"><span data-stu-id="e8e12-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="e8e12-222">スライダー</span><span class="sxs-lookup"><span data-stu-id="e8e12-222">Slider</span></span>|  
|<span data-ttu-id="e8e12-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="e8e12-223">SuperGrid</span></span>|<span data-ttu-id="e8e12-224">カスタム</span><span class="sxs-lookup"><span data-stu-id="e8e12-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="e8e12-225">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="e8e12-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="e8e12-226">Windows フォームコントロールは、、uiautomationclientsideproviders.dll [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]のクライアント側プロバイダーを介してに公開されます。</span><span class="sxs-lookup"><span data-stu-id="e8e12-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="e8e12-227">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="e8e12-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="e8e12-228">通常、コモンコントロールの[!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]マネージラッパーである Windows フォームコントロールは、で[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]サポートされています。</span><span class="sxs-lookup"><span data-stu-id="e8e12-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="e8e12-229">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e8e12-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="e8e12-230">クラス名</span><span class="sxs-lookup"><span data-stu-id="e8e12-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="e8e12-231">ボタン</span><span class="sxs-lookup"><span data-stu-id="e8e12-231">Button</span></span>|  
|<span data-ttu-id="e8e12-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-232">CheckBox</span></span>|  
|<span data-ttu-id="e8e12-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-233">CheckedListBox</span></span>|  
|<span data-ttu-id="e8e12-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="e8e12-234">ColorDialog</span></span>|  
|<span data-ttu-id="e8e12-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-235">ComboBox</span></span>|  
|<span data-ttu-id="e8e12-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="e8e12-236">FolderBrowser</span></span>|  
|<span data-ttu-id="e8e12-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="e8e12-237">FontDialog</span></span>|  
|<span data-ttu-id="e8e12-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-238">GroupBox</span></span>|  
|<span data-ttu-id="e8e12-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="e8e12-239">HscrollBar</span></span>|  
|<span data-ttu-id="e8e12-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="e8e12-240">ImageList</span></span>|  
|<span data-ttu-id="e8e12-241">group1</span><span class="sxs-lookup"><span data-stu-id="e8e12-241">Label</span></span>|  
|<span data-ttu-id="e8e12-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-242">ListBox</span></span>|  
|<span data-ttu-id="e8e12-243">ListView</span><span class="sxs-lookup"><span data-stu-id="e8e12-243">ListView</span></span>|  
|<span data-ttu-id="e8e12-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="e8e12-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="e8e12-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="e8e12-245">MonthCalendar</span></span>|  
|<span data-ttu-id="e8e12-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="e8e12-246">NotifyIcon</span></span>|  
|<span data-ttu-id="e8e12-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="e8e12-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="e8e12-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="e8e12-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="e8e12-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="e8e12-249">PrintDialog</span></span>|  
|<span data-ttu-id="e8e12-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="e8e12-250">ProgressBar</span></span>|  
|<span data-ttu-id="e8e12-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="e8e12-251">RadioButton</span></span>|  
|<span data-ttu-id="e8e12-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-252">RichTextBox</span></span>|  
|<span data-ttu-id="e8e12-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="e8e12-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="e8e12-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="e8e12-254">ScrollableControl</span></span>|  
|<span data-ttu-id="e8e12-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="e8e12-255">SoundPlayer</span></span>|  
|<span data-ttu-id="e8e12-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="e8e12-256">StatusBar</span></span>|  
|<span data-ttu-id="e8e12-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="e8e12-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="e8e12-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-258">TextBox</span></span>|  
|<span data-ttu-id="e8e12-259">タイマー</span><span class="sxs-lookup"><span data-stu-id="e8e12-259">Timer</span></span>|  
|<span data-ttu-id="e8e12-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="e8e12-260">Toolbar</span></span>|  
|<span data-ttu-id="e8e12-261">ヒント</span><span class="sxs-lookup"><span data-stu-id="e8e12-261">ToolTip</span></span>|  
|<span data-ttu-id="e8e12-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="e8e12-262">TrackBar</span></span>|  
|<span data-ttu-id="e8e12-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="e8e12-263">TreeView</span></span>|  
|<span data-ttu-id="e8e12-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="e8e12-264">VscrollBar</span></span>|  
|<span data-ttu-id="e8e12-265">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="e8e12-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="e8e12-266">次のコントロールは、Microsoft [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Active Accessibility のサポートを通じてのみに公開されます。</span><span class="sxs-lookup"><span data-stu-id="e8e12-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="e8e12-267">一部の機能が使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="e8e12-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="e8e12-268">コントロール名</span><span class="sxs-lookup"><span data-stu-id="e8e12-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="e8e12-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="e8e12-269">BindingSource</span></span>|  
|<span data-ttu-id="e8e12-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="e8e12-270">DataGrid</span></span>|  
|<span data-ttu-id="e8e12-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="e8e12-271">DataGridView</span></span>|  
|<span data-ttu-id="e8e12-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="e8e12-272">DataNavigator</span></span>|  
|<span data-ttu-id="e8e12-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="e8e12-273">DomainUpDown</span></span>|  
|<span data-ttu-id="e8e12-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="e8e12-274">ErrorProvider</span></span>|  
|<span data-ttu-id="e8e12-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="e8e12-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="e8e12-276">フォーム</span><span class="sxs-lookup"><span data-stu-id="e8e12-276">Form</span></span>|  
|<span data-ttu-id="e8e12-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="e8e12-277">LinkLabel</span></span>|  
|<span data-ttu-id="e8e12-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="e8e12-278">HelpProvider</span></span>|  
|<span data-ttu-id="e8e12-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="e8e12-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="e8e12-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="e8e12-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="e8e12-281">NumericUpDown</span></span>|  
|<span data-ttu-id="e8e12-282">パネル</span><span class="sxs-lookup"><span data-stu-id="e8e12-282">Panel</span></span>|  
|<span data-ttu-id="e8e12-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="e8e12-283">PictureBox</span></span>|  
|<span data-ttu-id="e8e12-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="e8e12-284">PrintDocument</span></span>|  
|<span data-ttu-id="e8e12-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="e8e12-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="e8e12-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="e8e12-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="e8e12-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="e8e12-287">PropertyGrid</span></span>|  
|<span data-ttu-id="e8e12-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="e8e12-288">UserControl</span></span>|  
|<span data-ttu-id="e8e12-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="e8e12-289">ToolStrip</span></span>|  
|<span data-ttu-id="e8e12-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="e8e12-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="e8e12-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="e8e12-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="e8e12-292">スプリッター</span><span class="sxs-lookup"><span data-stu-id="e8e12-292">Splitter</span></span>|  
|<span data-ttu-id="e8e12-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="e8e12-293">RaftingContainer</span></span>|  
|<span data-ttu-id="e8e12-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="e8e12-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8e12-295">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8e12-295">See also</span></span>

- [<span data-ttu-id="e8e12-296">UI オートメーション コントロール型</span><span class="sxs-lookup"><span data-stu-id="e8e12-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
