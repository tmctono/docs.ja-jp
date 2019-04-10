---
title: UI オートメーションによる標準コントロールのサポート
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 3fde9779205ea7d0902ddd99ed192f097a159d2c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221480"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="a4412-102">UI オートメーションによる標準コントロールのサポート</span><span class="sxs-lookup"><span data-stu-id="a4412-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="a4412-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="a4412-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a4412-104">に関する最新情報については[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を参照してください[Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)します。</span><span class="sxs-lookup"><span data-stu-id="a4412-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="a4412-105">このトピックでは、 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 、 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]、および [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]フレームワーク向けに開発されたアプリケーションの標準コントロールに対する [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] サポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a4412-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="a4412-106">Windows Presentation Foundation コントロール</span><span class="sxs-lookup"><span data-stu-id="a4412-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="a4412-107">ユーザー操作に関する情報やサポートを提供するすべての [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] コントロール要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を全面的にネイティブ サポートしています。</span><span class="sxs-lookup"><span data-stu-id="a4412-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="a4412-108">パネルなどのその他の要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]からは認識できません。</span><span class="sxs-lookup"><span data-stu-id="a4412-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="a4412-109">Win32 コントロール</span><span class="sxs-lookup"><span data-stu-id="a4412-109">Win32 Controls</span></span>  
 <span data-ttu-id="a4412-110">ほとんどの [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] コントロールは、UIAutomationClientsideProviders.dll のクライアント側プロバイダーによって [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] に公開されています。</span><span class="sxs-lookup"><span data-stu-id="a4412-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="a4412-111">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="a4412-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="a4412-112">完全なサポートは、ComCtrl32.dll のバージョン 6 ( [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] 以降で使用可能) のコントロールに対してのみ提供されています。</span><span class="sxs-lookup"><span data-stu-id="a4412-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="a4412-113">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a4412-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="a4412-114">クラス名</span><span class="sxs-lookup"><span data-stu-id="a4412-114">Class name</span></span>|<span data-ttu-id="a4412-115">コントロール型</span><span class="sxs-lookup"><span data-stu-id="a4412-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="a4412-116">ボタン</span><span class="sxs-lookup"><span data-stu-id="a4412-116">Button</span></span>|<span data-ttu-id="a4412-117">ボタン</span><span class="sxs-lookup"><span data-stu-id="a4412-117">Button</span></span>|  
|<span data-ttu-id="a4412-118">ボタン</span><span class="sxs-lookup"><span data-stu-id="a4412-118">Button</span></span>|<span data-ttu-id="a4412-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a4412-119">RadioButton</span></span>|  
|<span data-ttu-id="a4412-120">ボタン</span><span class="sxs-lookup"><span data-stu-id="a4412-120">Button</span></span>|<span data-ttu-id="a4412-121">グループ化</span><span class="sxs-lookup"><span data-stu-id="a4412-121">Group</span></span>|  
|<span data-ttu-id="a4412-122">ボタン</span><span class="sxs-lookup"><span data-stu-id="a4412-122">Button</span></span>|<span data-ttu-id="a4412-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a4412-123">CheckBox</span></span>|  
|<span data-ttu-id="a4412-124">ボタン</span><span class="sxs-lookup"><span data-stu-id="a4412-124">Button</span></span>|<span data-ttu-id="a4412-125">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="a4412-125">Hyperlink</span></span>|  
|<span data-ttu-id="a4412-126">ボタン</span><span class="sxs-lookup"><span data-stu-id="a4412-126">Button</span></span>|<span data-ttu-id="a4412-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="a4412-127">SplitButton</span></span>|  
|<span data-ttu-id="a4412-128">ボタン</span><span class="sxs-lookup"><span data-stu-id="a4412-128">Button</span></span>|<span data-ttu-id="a4412-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a4412-129">CheckBox</span></span>|  
|<span data-ttu-id="a4412-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="a4412-130">ComboBoxEx32</span></span>|<span data-ttu-id="a4412-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a4412-131">ComboBox</span></span>|  
|<span data-ttu-id="a4412-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a4412-132">ComboBox</span></span>|<span data-ttu-id="a4412-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a4412-133">ComboBox</span></span>|  
|<span data-ttu-id="a4412-134">編集</span><span class="sxs-lookup"><span data-stu-id="a4412-134">Edit</span></span>|<span data-ttu-id="a4412-135">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="a4412-135">Document</span></span>|  
|<span data-ttu-id="a4412-136">編集</span><span class="sxs-lookup"><span data-stu-id="a4412-136">Edit</span></span>|<span data-ttu-id="a4412-137">編集</span><span class="sxs-lookup"><span data-stu-id="a4412-137">Edit</span></span>|  
|<span data-ttu-id="a4412-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="a4412-138">SysLink</span></span>|<span data-ttu-id="a4412-139">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="a4412-139">Hyperlink</span></span>|  
|<span data-ttu-id="a4412-140">スタティック</span><span class="sxs-lookup"><span data-stu-id="a4412-140">Static</span></span>|<span data-ttu-id="a4412-141">テキスト</span><span class="sxs-lookup"><span data-stu-id="a4412-141">Text</span></span>|  
|<span data-ttu-id="a4412-142">スタティック</span><span class="sxs-lookup"><span data-stu-id="a4412-142">Static</span></span>|<span data-ttu-id="a4412-143">イメージ</span><span class="sxs-lookup"><span data-stu-id="a4412-143">Image</span></span>|  
|<span data-ttu-id="a4412-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="a4412-144">SysIPAddress32</span></span>|<span data-ttu-id="a4412-145">カスタム</span><span class="sxs-lookup"><span data-stu-id="a4412-145">Custom</span></span>|  
|<span data-ttu-id="a4412-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="a4412-146">SysHeader32</span></span>|<span data-ttu-id="a4412-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="a4412-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="a4412-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="a4412-148">SysListView32</span></span>|<span data-ttu-id="a4412-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="a4412-149">DataGrid</span></span>|  
|<span data-ttu-id="a4412-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="a4412-150">SysListView32</span></span>|<span data-ttu-id="a4412-151">リスト</span><span class="sxs-lookup"><span data-stu-id="a4412-151">List</span></span>|  
|<span data-ttu-id="a4412-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="a4412-152">ListBox</span></span>|<span data-ttu-id="a4412-153">リスト</span><span class="sxs-lookup"><span data-stu-id="a4412-153">List</span></span>|  
|<span data-ttu-id="a4412-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="a4412-154">ListBox</span></span>|<span data-ttu-id="a4412-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="a4412-155">ListItem</span></span>|  
|<span data-ttu-id="a4412-156">#32768</span><span class="sxs-lookup"><span data-stu-id="a4412-156">#32768</span></span>|<span data-ttu-id="a4412-157">メニュー</span><span class="sxs-lookup"><span data-stu-id="a4412-157">Menu</span></span>|  
|<span data-ttu-id="a4412-158">#32768</span><span class="sxs-lookup"><span data-stu-id="a4412-158">#32768</span></span>|<span data-ttu-id="a4412-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="a4412-159">MenuItem</span></span>|  
|<span data-ttu-id="a4412-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="a4412-160">msctls_progress32</span></span>|<span data-ttu-id="a4412-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="a4412-161">ProgressBar</span></span>|  
|<span data-ttu-id="a4412-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="a4412-162">RichEdit</span></span>|<span data-ttu-id="a4412-163">ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="a4412-163">Document.</span></span> <span data-ttu-id="a4412-164">注を参照。</span><span class="sxs-lookup"><span data-stu-id="a4412-164">See note.</span></span>|  
|<span data-ttu-id="a4412-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="a4412-165">RichEdit20A</span></span>|<span data-ttu-id="a4412-166">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="a4412-166">Document</span></span>|  
|<span data-ttu-id="a4412-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="a4412-167">RichEdit20W</span></span>|<span data-ttu-id="a4412-168">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="a4412-168">Document</span></span>|  
|<span data-ttu-id="a4412-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="a4412-169">RichEdit50W</span></span>|<span data-ttu-id="a4412-170">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="a4412-170">Document</span></span>|  
|<span data-ttu-id="a4412-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="a4412-171">ScrollBar</span></span>|<span data-ttu-id="a4412-172">スライダー</span><span class="sxs-lookup"><span data-stu-id="a4412-172">Slider</span></span>|  
|<span data-ttu-id="a4412-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="a4412-173">msctls_trackbar32</span></span>|<span data-ttu-id="a4412-174">スライダー</span><span class="sxs-lookup"><span data-stu-id="a4412-174">Slider</span></span>|  
|<span data-ttu-id="a4412-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="a4412-175">msctls_updown32</span></span>|<span data-ttu-id="a4412-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="a4412-176">Spinner</span></span>|  
|<span data-ttu-id="a4412-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="a4412-177">msctls_statusbar32</span></span>|<span data-ttu-id="a4412-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="a4412-178">StatusBar</span></span>|  
|<span data-ttu-id="a4412-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="a4412-179">SysTabControl32</span></span>|<span data-ttu-id="a4412-180">タブ</span><span class="sxs-lookup"><span data-stu-id="a4412-180">Tab</span></span>|  
|<span data-ttu-id="a4412-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="a4412-181">SysTabControl32</span></span>|<span data-ttu-id="a4412-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="a4412-182">TabItem</span></span>|  
|<span data-ttu-id="a4412-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a4412-183">ToolbarWindow32</span></span>|<span data-ttu-id="a4412-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="a4412-184">ToolBar</span></span>|  
|<span data-ttu-id="a4412-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a4412-185">ToolbarWindow32</span></span>|<span data-ttu-id="a4412-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="a4412-186">MenuItem</span></span>|  
|<span data-ttu-id="a4412-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a4412-187">ToolbarWindow32</span></span>|<span data-ttu-id="a4412-188">ボタン</span><span class="sxs-lookup"><span data-stu-id="a4412-188">Button</span></span>|  
|<span data-ttu-id="a4412-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a4412-189">ToolbarWindow32</span></span>|<span data-ttu-id="a4412-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a4412-190">CheckBox</span></span>|  
|<span data-ttu-id="a4412-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a4412-191">ToolbarWindow32</span></span>|<span data-ttu-id="a4412-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a4412-192">RadioButton</span></span>|  
|<span data-ttu-id="a4412-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a4412-193">ToolbarWindow32</span></span>|<span data-ttu-id="a4412-194">区切り記号</span><span class="sxs-lookup"><span data-stu-id="a4412-194">Separator</span></span>|  
|<span data-ttu-id="a4412-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="a4412-195">tooltips_class32</span></span>|<span data-ttu-id="a4412-196">ヒント</span><span class="sxs-lookup"><span data-stu-id="a4412-196">ToolTip</span></span>|  
|<span data-ttu-id="a4412-197">#32774</span><span class="sxs-lookup"><span data-stu-id="a4412-197">#32774</span></span>|<span data-ttu-id="a4412-198">ヒント</span><span class="sxs-lookup"><span data-stu-id="a4412-198">ToolTip</span></span>|  
|<span data-ttu-id="a4412-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="a4412-199">ReBarWindow32</span></span>|<span data-ttu-id="a4412-200">ツール バー</span><span class="sxs-lookup"><span data-stu-id="a4412-200">Toolbar</span></span>|  
|<span data-ttu-id="a4412-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="a4412-201">SysTreeView32</span></span>|<span data-ttu-id="a4412-202">ツリー</span><span class="sxs-lookup"><span data-stu-id="a4412-202">Tree</span></span>|  
|<span data-ttu-id="a4412-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="a4412-203">SysTreeView32</span></span>|<span data-ttu-id="a4412-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="a4412-204">TreeItem</span></span>|  
  
 <span data-ttu-id="a4412-205">**注** RichEdit コントロールは、 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] に付属するバージョン (RichEd20.dll バージョン 3.1 以降、および MsftEdit.dll バージョン 4.1 以降) に対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a4412-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="a4412-206">次のコントロールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a4412-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="a4412-207">クラス名</span><span class="sxs-lookup"><span data-stu-id="a4412-207">Class name</span></span>|<span data-ttu-id="a4412-208">コントロール型</span><span class="sxs-lookup"><span data-stu-id="a4412-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="a4412-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="a4412-209">SysAnimate32</span></span>|<span data-ttu-id="a4412-210">イメージ</span><span class="sxs-lookup"><span data-stu-id="a4412-210">Image</span></span>|  
|<span data-ttu-id="a4412-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="a4412-211">SysPager</span></span>|<span data-ttu-id="a4412-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="a4412-212">Spinner</span></span>|  
|<span data-ttu-id="a4412-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="a4412-213">SysDateTimePick32</span></span>|<span data-ttu-id="a4412-214">カスタム</span><span class="sxs-lookup"><span data-stu-id="a4412-214">Custom</span></span>|  
|<span data-ttu-id="a4412-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="a4412-215">SysMonthCal32</span></span>|<span data-ttu-id="a4412-216">予定表</span><span class="sxs-lookup"><span data-stu-id="a4412-216">Calendar</span></span>|  
|<span data-ttu-id="a4412-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="a4412-217">MS_WINNOTE</span></span>|<span data-ttu-id="a4412-218">ヒント</span><span class="sxs-lookup"><span data-stu-id="a4412-218">Tooltip</span></span>|  
|<span data-ttu-id="a4412-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="a4412-219">VBBubble</span></span>|<span data-ttu-id="a4412-220">ヒント</span><span class="sxs-lookup"><span data-stu-id="a4412-220">Tooltip</span></span>|  
|<span data-ttu-id="a4412-221">ScrollBar (スタンドアロン コントロールとして使用される場合)</span><span class="sxs-lookup"><span data-stu-id="a4412-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="a4412-222">スライダー</span><span class="sxs-lookup"><span data-stu-id="a4412-222">Slider</span></span>|  
|<span data-ttu-id="a4412-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="a4412-223">SuperGrid</span></span>|<span data-ttu-id="a4412-224">カスタム</span><span class="sxs-lookup"><span data-stu-id="a4412-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="a4412-225">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="a4412-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="a4412-226">Windows フォーム コントロールに公開[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]UIAutomationClientsideProviders.dll のクライアント側プロバイダーを経由します。</span><span class="sxs-lookup"><span data-stu-id="a4412-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="a4412-227">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="a4412-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="a4412-228">通常、Windows フォーム コントロール用のマネージ ラッパー[!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]で一般的なコントロールがサポートされる[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a4412-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="a4412-229">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a4412-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="a4412-230">クラス名</span><span class="sxs-lookup"><span data-stu-id="a4412-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="a4412-231">ボタン</span><span class="sxs-lookup"><span data-stu-id="a4412-231">Button</span></span>|  
|<span data-ttu-id="a4412-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a4412-232">CheckBox</span></span>|  
|<span data-ttu-id="a4412-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="a4412-233">CheckedListBox</span></span>|  
|<span data-ttu-id="a4412-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="a4412-234">ColorDialog</span></span>|  
|<span data-ttu-id="a4412-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a4412-235">ComboBox</span></span>|  
|<span data-ttu-id="a4412-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="a4412-236">FolderBrowser</span></span>|  
|<span data-ttu-id="a4412-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="a4412-237">FontDialog</span></span>|  
|<span data-ttu-id="a4412-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="a4412-238">GroupBox</span></span>|  
|<span data-ttu-id="a4412-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="a4412-239">HscrollBar</span></span>|  
|<span data-ttu-id="a4412-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="a4412-240">ImageList</span></span>|  
|<span data-ttu-id="a4412-241">group1</span><span class="sxs-lookup"><span data-stu-id="a4412-241">Label</span></span>|  
|<span data-ttu-id="a4412-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="a4412-242">ListBox</span></span>|  
|<span data-ttu-id="a4412-243">ListView</span><span class="sxs-lookup"><span data-stu-id="a4412-243">ListView</span></span>|  
|<span data-ttu-id="a4412-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="a4412-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="a4412-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="a4412-245">MonthCalendar</span></span>|  
|<span data-ttu-id="a4412-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="a4412-246">NotifyIcon</span></span>|  
|<span data-ttu-id="a4412-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="a4412-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="a4412-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="a4412-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="a4412-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="a4412-249">PrintDialog</span></span>|  
|<span data-ttu-id="a4412-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="a4412-250">ProgressBar</span></span>|  
|<span data-ttu-id="a4412-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a4412-251">RadioButton</span></span>|  
|<span data-ttu-id="a4412-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="a4412-252">RichTextBox</span></span>|  
|<span data-ttu-id="a4412-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="a4412-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="a4412-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="a4412-254">ScrollableControl</span></span>|  
|<span data-ttu-id="a4412-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="a4412-255">SoundPlayer</span></span>|  
|<span data-ttu-id="a4412-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="a4412-256">StatusBar</span></span>|  
|<span data-ttu-id="a4412-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="a4412-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="a4412-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="a4412-258">TextBox</span></span>|  
|<span data-ttu-id="a4412-259">タイマー</span><span class="sxs-lookup"><span data-stu-id="a4412-259">Timer</span></span>|  
|<span data-ttu-id="a4412-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="a4412-260">Toolbar</span></span>|  
|<span data-ttu-id="a4412-261">ヒント</span><span class="sxs-lookup"><span data-stu-id="a4412-261">ToolTip</span></span>|  
|<span data-ttu-id="a4412-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="a4412-262">TrackBar</span></span>|  
|<span data-ttu-id="a4412-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="a4412-263">TreeView</span></span>|  
|<span data-ttu-id="a4412-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="a4412-264">VscrollBar</span></span>|  
|<span data-ttu-id="a4412-265">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="a4412-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="a4412-266">次に示すコントロールは、 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] のサポートによってのみ、 [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)]に公開されています。</span><span class="sxs-lookup"><span data-stu-id="a4412-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="a4412-267">一部の機能が使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="a4412-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="a4412-268">コントロール名</span><span class="sxs-lookup"><span data-stu-id="a4412-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="a4412-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="a4412-269">BindingSource</span></span>|  
|<span data-ttu-id="a4412-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="a4412-270">DataGrid</span></span>|  
|<span data-ttu-id="a4412-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="a4412-271">DataGridView</span></span>|  
|<span data-ttu-id="a4412-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="a4412-272">DataNavigator</span></span>|  
|<span data-ttu-id="a4412-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="a4412-273">DomainUpDown</span></span>|  
|<span data-ttu-id="a4412-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="a4412-274">ErrorProvider</span></span>|  
|<span data-ttu-id="a4412-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a4412-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="a4412-276">フォーム</span><span class="sxs-lookup"><span data-stu-id="a4412-276">Form</span></span>|  
|<span data-ttu-id="a4412-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="a4412-277">LinkLabel</span></span>|  
|<span data-ttu-id="a4412-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="a4412-278">HelpProvider</span></span>|  
|<span data-ttu-id="a4412-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="a4412-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="a4412-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="a4412-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="a4412-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="a4412-281">NumericUpDown</span></span>|  
|<span data-ttu-id="a4412-282">パネル</span><span class="sxs-lookup"><span data-stu-id="a4412-282">Panel</span></span>|  
|<span data-ttu-id="a4412-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="a4412-283">PictureBox</span></span>|  
|<span data-ttu-id="a4412-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="a4412-284">PrintDocument</span></span>|  
|<span data-ttu-id="a4412-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="a4412-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="a4412-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="a4412-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="a4412-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="a4412-287">PropertyGrid</span></span>|  
|<span data-ttu-id="a4412-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="a4412-288">UserControl</span></span>|  
|<span data-ttu-id="a4412-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="a4412-289">ToolStrip</span></span>|  
|<span data-ttu-id="a4412-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a4412-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="a4412-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="a4412-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="a4412-292">スプリッター</span><span class="sxs-lookup"><span data-stu-id="a4412-292">Splitter</span></span>|  
|<span data-ttu-id="a4412-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="a4412-293">RaftingContainer</span></span>|  
|<span data-ttu-id="a4412-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="a4412-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4412-295">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4412-295">See also</span></span>

- [<span data-ttu-id="a4412-296">UI オートメーション コントロール型</span><span class="sxs-lookup"><span data-stu-id="a4412-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
