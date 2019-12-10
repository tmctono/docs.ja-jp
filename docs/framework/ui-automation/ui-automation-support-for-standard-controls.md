---
title: UI オートメーションによる標準コントロールのサポート
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 314526c1164f70e6b261df1a6f11ddce2b5fa240
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960072"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="bd432-102">UI オートメーションによる標準コントロールのサポート</span><span class="sxs-lookup"><span data-stu-id="bd432-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="bd432-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="bd432-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="bd432-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI Automation (Windows のオートメーション API: UI オートメーション)](/windows/win32/winauto/entry-uiauto-win32)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd432-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="bd432-105">このトピックでは、 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 、 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]、および [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]フレームワーク向けに開発されたアプリケーションの標準コントロールに対する [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] サポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bd432-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="bd432-106">Windows Presentation Foundation コントロール</span><span class="sxs-lookup"><span data-stu-id="bd432-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="bd432-107">ユーザー操作に関する情報やサポートを提供するすべての [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] コントロール要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を全面的にネイティブ サポートしています。</span><span class="sxs-lookup"><span data-stu-id="bd432-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="bd432-108">パネルなどのその他の要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]からは認識できません。</span><span class="sxs-lookup"><span data-stu-id="bd432-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="bd432-109">Win32 コントロール</span><span class="sxs-lookup"><span data-stu-id="bd432-109">Win32 Controls</span></span>  
 <span data-ttu-id="bd432-110">ほとんどの [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] コントロールは、UIAutomationClientsideProviders.dll のクライアント側プロバイダーによって [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] に公開されています。</span><span class="sxs-lookup"><span data-stu-id="bd432-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="bd432-111">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="bd432-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="bd432-112">完全サポートは、 *、comctrl32.dll*のバージョン6のコントロールに対してのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="bd432-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="bd432-113">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bd432-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="bd432-114">[クラス名]</span><span class="sxs-lookup"><span data-stu-id="bd432-114">Class name</span></span>|<span data-ttu-id="bd432-115">コントロール型</span><span class="sxs-lookup"><span data-stu-id="bd432-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="bd432-116">Button</span><span class="sxs-lookup"><span data-stu-id="bd432-116">Button</span></span>|<span data-ttu-id="bd432-117">Button</span><span class="sxs-lookup"><span data-stu-id="bd432-117">Button</span></span>|  
|<span data-ttu-id="bd432-118">Button</span><span class="sxs-lookup"><span data-stu-id="bd432-118">Button</span></span>|<span data-ttu-id="bd432-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="bd432-119">RadioButton</span></span>|  
|<span data-ttu-id="bd432-120">Button</span><span class="sxs-lookup"><span data-stu-id="bd432-120">Button</span></span>|<span data-ttu-id="bd432-121">グループ</span><span class="sxs-lookup"><span data-stu-id="bd432-121">Group</span></span>|  
|<span data-ttu-id="bd432-122">Button</span><span class="sxs-lookup"><span data-stu-id="bd432-122">Button</span></span>|<span data-ttu-id="bd432-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="bd432-123">CheckBox</span></span>|  
|<span data-ttu-id="bd432-124">Button</span><span class="sxs-lookup"><span data-stu-id="bd432-124">Button</span></span>|<span data-ttu-id="bd432-125">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="bd432-125">Hyperlink</span></span>|  
|<span data-ttu-id="bd432-126">Button</span><span class="sxs-lookup"><span data-stu-id="bd432-126">Button</span></span>|<span data-ttu-id="bd432-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="bd432-127">SplitButton</span></span>|  
|<span data-ttu-id="bd432-128">Button</span><span class="sxs-lookup"><span data-stu-id="bd432-128">Button</span></span>|<span data-ttu-id="bd432-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="bd432-129">CheckBox</span></span>|  
|<span data-ttu-id="bd432-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="bd432-130">ComboBoxEx32</span></span>|<span data-ttu-id="bd432-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="bd432-131">ComboBox</span></span>|  
|<span data-ttu-id="bd432-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="bd432-132">ComboBox</span></span>|<span data-ttu-id="bd432-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="bd432-133">ComboBox</span></span>|  
|<span data-ttu-id="bd432-134">[編集]</span><span class="sxs-lookup"><span data-stu-id="bd432-134">Edit</span></span>|<span data-ttu-id="bd432-135">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="bd432-135">Document</span></span>|  
|<span data-ttu-id="bd432-136">[編集]</span><span class="sxs-lookup"><span data-stu-id="bd432-136">Edit</span></span>|<span data-ttu-id="bd432-137">[編集]</span><span class="sxs-lookup"><span data-stu-id="bd432-137">Edit</span></span>|  
|<span data-ttu-id="bd432-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="bd432-138">SysLink</span></span>|<span data-ttu-id="bd432-139">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="bd432-139">Hyperlink</span></span>|  
|<span data-ttu-id="bd432-140">スタティック</span><span class="sxs-lookup"><span data-stu-id="bd432-140">Static</span></span>|<span data-ttu-id="bd432-141">テキスト</span><span class="sxs-lookup"><span data-stu-id="bd432-141">Text</span></span>|  
|<span data-ttu-id="bd432-142">スタティック</span><span class="sxs-lookup"><span data-stu-id="bd432-142">Static</span></span>|<span data-ttu-id="bd432-143">Image</span><span class="sxs-lookup"><span data-stu-id="bd432-143">Image</span></span>|  
|<span data-ttu-id="bd432-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="bd432-144">SysIPAddress32</span></span>|<span data-ttu-id="bd432-145">カスタム</span><span class="sxs-lookup"><span data-stu-id="bd432-145">Custom</span></span>|  
|<span data-ttu-id="bd432-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="bd432-146">SysHeader32</span></span>|<span data-ttu-id="bd432-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="bd432-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="bd432-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="bd432-148">SysListView32</span></span>|<span data-ttu-id="bd432-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="bd432-149">DataGrid</span></span>|  
|<span data-ttu-id="bd432-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="bd432-150">SysListView32</span></span>|<span data-ttu-id="bd432-151">リスト型</span><span class="sxs-lookup"><span data-stu-id="bd432-151">List</span></span>|  
|<span data-ttu-id="bd432-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="bd432-152">ListBox</span></span>|<span data-ttu-id="bd432-153">リスト型</span><span class="sxs-lookup"><span data-stu-id="bd432-153">List</span></span>|  
|<span data-ttu-id="bd432-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="bd432-154">ListBox</span></span>|<span data-ttu-id="bd432-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="bd432-155">ListItem</span></span>|  
|<span data-ttu-id="bd432-156">#32768</span><span class="sxs-lookup"><span data-stu-id="bd432-156">#32768</span></span>|<span data-ttu-id="bd432-157">メニュー</span><span class="sxs-lookup"><span data-stu-id="bd432-157">Menu</span></span>|  
|<span data-ttu-id="bd432-158">#32768</span><span class="sxs-lookup"><span data-stu-id="bd432-158">#32768</span></span>|<span data-ttu-id="bd432-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="bd432-159">MenuItem</span></span>|  
|<span data-ttu-id="bd432-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="bd432-160">msctls_progress32</span></span>|<span data-ttu-id="bd432-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="bd432-161">ProgressBar</span></span>|  
|<span data-ttu-id="bd432-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="bd432-162">RichEdit</span></span>|<span data-ttu-id="bd432-163">ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="bd432-163">Document.</span></span> <span data-ttu-id="bd432-164">注を参照。</span><span class="sxs-lookup"><span data-stu-id="bd432-164">See note.</span></span>|  
|<span data-ttu-id="bd432-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="bd432-165">RichEdit20A</span></span>|<span data-ttu-id="bd432-166">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="bd432-166">Document</span></span>|  
|<span data-ttu-id="bd432-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="bd432-167">RichEdit20W</span></span>|<span data-ttu-id="bd432-168">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="bd432-168">Document</span></span>|  
|<span data-ttu-id="bd432-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="bd432-169">RichEdit50W</span></span>|<span data-ttu-id="bd432-170">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="bd432-170">Document</span></span>|  
|<span data-ttu-id="bd432-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="bd432-171">ScrollBar</span></span>|<span data-ttu-id="bd432-172">[スライダー]</span><span class="sxs-lookup"><span data-stu-id="bd432-172">Slider</span></span>|  
|<span data-ttu-id="bd432-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="bd432-173">msctls_trackbar32</span></span>|<span data-ttu-id="bd432-174">[スライダー]</span><span class="sxs-lookup"><span data-stu-id="bd432-174">Slider</span></span>|  
|<span data-ttu-id="bd432-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="bd432-175">msctls_updown32</span></span>|<span data-ttu-id="bd432-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="bd432-176">Spinner</span></span>|  
|<span data-ttu-id="bd432-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="bd432-177">msctls_statusbar32</span></span>|<span data-ttu-id="bd432-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="bd432-178">StatusBar</span></span>|  
|<span data-ttu-id="bd432-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="bd432-179">SysTabControl32</span></span>|<span data-ttu-id="bd432-180">タブ</span><span class="sxs-lookup"><span data-stu-id="bd432-180">Tab</span></span>|  
|<span data-ttu-id="bd432-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="bd432-181">SysTabControl32</span></span>|<span data-ttu-id="bd432-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="bd432-182">TabItem</span></span>|  
|<span data-ttu-id="bd432-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="bd432-183">ToolbarWindow32</span></span>|<span data-ttu-id="bd432-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="bd432-184">ToolBar</span></span>|  
|<span data-ttu-id="bd432-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="bd432-185">ToolbarWindow32</span></span>|<span data-ttu-id="bd432-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="bd432-186">MenuItem</span></span>|  
|<span data-ttu-id="bd432-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="bd432-187">ToolbarWindow32</span></span>|<span data-ttu-id="bd432-188">Button</span><span class="sxs-lookup"><span data-stu-id="bd432-188">Button</span></span>|  
|<span data-ttu-id="bd432-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="bd432-189">ToolbarWindow32</span></span>|<span data-ttu-id="bd432-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="bd432-190">CheckBox</span></span>|  
|<span data-ttu-id="bd432-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="bd432-191">ToolbarWindow32</span></span>|<span data-ttu-id="bd432-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="bd432-192">RadioButton</span></span>|  
|<span data-ttu-id="bd432-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="bd432-193">ToolbarWindow32</span></span>|<span data-ttu-id="bd432-194">[区切り文字]</span><span class="sxs-lookup"><span data-stu-id="bd432-194">Separator</span></span>|  
|<span data-ttu-id="bd432-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="bd432-195">tooltips_class32</span></span>|<span data-ttu-id="bd432-196">ToolTip</span><span class="sxs-lookup"><span data-stu-id="bd432-196">ToolTip</span></span>|  
|<span data-ttu-id="bd432-197">#32774</span><span class="sxs-lookup"><span data-stu-id="bd432-197">#32774</span></span>|<span data-ttu-id="bd432-198">ToolTip</span><span class="sxs-lookup"><span data-stu-id="bd432-198">ToolTip</span></span>|  
|<span data-ttu-id="bd432-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="bd432-199">ReBarWindow32</span></span>|<span data-ttu-id="bd432-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="bd432-200">Toolbar</span></span>|  
|<span data-ttu-id="bd432-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="bd432-201">SysTreeView32</span></span>|<span data-ttu-id="bd432-202">ツリー</span><span class="sxs-lookup"><span data-stu-id="bd432-202">Tree</span></span>|  
|<span data-ttu-id="bd432-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="bd432-203">SysTreeView32</span></span>|<span data-ttu-id="bd432-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="bd432-204">TreeItem</span></span>|  
  
 <span data-ttu-id="bd432-205">**メモ**RichEdit コントロールは、Windows Vista に付属するバージョン (Riched20.dll バージョン3.1 以降では、MsftEdit .dll バージョン4.1 以降) でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bd432-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="bd432-206">次のコントロールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bd432-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="bd432-207">[クラス名]</span><span class="sxs-lookup"><span data-stu-id="bd432-207">Class name</span></span>|<span data-ttu-id="bd432-208">コントロール型</span><span class="sxs-lookup"><span data-stu-id="bd432-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="bd432-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="bd432-209">SysAnimate32</span></span>|<span data-ttu-id="bd432-210">Image</span><span class="sxs-lookup"><span data-stu-id="bd432-210">Image</span></span>|  
|<span data-ttu-id="bd432-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="bd432-211">SysPager</span></span>|<span data-ttu-id="bd432-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="bd432-212">Spinner</span></span>|  
|<span data-ttu-id="bd432-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="bd432-213">SysDateTimePick32</span></span>|<span data-ttu-id="bd432-214">カスタム</span><span class="sxs-lookup"><span data-stu-id="bd432-214">Custom</span></span>|  
|<span data-ttu-id="bd432-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="bd432-215">SysMonthCal32</span></span>|<span data-ttu-id="bd432-216">予定表</span><span class="sxs-lookup"><span data-stu-id="bd432-216">Calendar</span></span>|  
|<span data-ttu-id="bd432-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="bd432-217">MS_WINNOTE</span></span>|<span data-ttu-id="bd432-218">Tooltip</span><span class="sxs-lookup"><span data-stu-id="bd432-218">Tooltip</span></span>|  
|<span data-ttu-id="bd432-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="bd432-219">VBBubble</span></span>|<span data-ttu-id="bd432-220">Tooltip</span><span class="sxs-lookup"><span data-stu-id="bd432-220">Tooltip</span></span>|  
|<span data-ttu-id="bd432-221">ScrollBar (スタンドアロン コントロールとして使用される場合)</span><span class="sxs-lookup"><span data-stu-id="bd432-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="bd432-222">[スライダー]</span><span class="sxs-lookup"><span data-stu-id="bd432-222">Slider</span></span>|  
|<span data-ttu-id="bd432-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="bd432-223">SuperGrid</span></span>|<span data-ttu-id="bd432-224">カスタム</span><span class="sxs-lookup"><span data-stu-id="bd432-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="bd432-225">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="bd432-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="bd432-226">Windows フォームコントロールは、、Uiautomationclientsideproviders.dll のクライアント側プロバイダーを介して [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] に公開されます。</span><span class="sxs-lookup"><span data-stu-id="bd432-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="bd432-227">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="bd432-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="bd432-228">通常、[!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] コモンコントロールのマネージラッパーである Windows フォームコントロールは [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]によってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="bd432-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="bd432-229">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bd432-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="bd432-230">クラス名</span><span class="sxs-lookup"><span data-stu-id="bd432-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="bd432-231">Button</span><span class="sxs-lookup"><span data-stu-id="bd432-231">Button</span></span>|  
|<span data-ttu-id="bd432-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="bd432-232">CheckBox</span></span>|  
|<span data-ttu-id="bd432-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="bd432-233">CheckedListBox</span></span>|  
|<span data-ttu-id="bd432-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="bd432-234">ColorDialog</span></span>|  
|<span data-ttu-id="bd432-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="bd432-235">ComboBox</span></span>|  
|<span data-ttu-id="bd432-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="bd432-236">FolderBrowser</span></span>|  
|<span data-ttu-id="bd432-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="bd432-237">FontDialog</span></span>|  
|<span data-ttu-id="bd432-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="bd432-238">GroupBox</span></span>|  
|<span data-ttu-id="bd432-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="bd432-239">HscrollBar</span></span>|  
|<span data-ttu-id="bd432-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="bd432-240">ImageList</span></span>|  
|<span data-ttu-id="bd432-241">[ラベル]</span><span class="sxs-lookup"><span data-stu-id="bd432-241">Label</span></span>|  
|<span data-ttu-id="bd432-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="bd432-242">ListBox</span></span>|  
|<span data-ttu-id="bd432-243">ListView</span><span class="sxs-lookup"><span data-stu-id="bd432-243">ListView</span></span>|  
|<span data-ttu-id="bd432-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="bd432-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="bd432-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="bd432-245">MonthCalendar</span></span>|  
|<span data-ttu-id="bd432-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="bd432-246">NotifyIcon</span></span>|  
|<span data-ttu-id="bd432-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="bd432-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="bd432-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="bd432-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="bd432-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="bd432-249">PrintDialog</span></span>|  
|<span data-ttu-id="bd432-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="bd432-250">ProgressBar</span></span>|  
|<span data-ttu-id="bd432-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="bd432-251">RadioButton</span></span>|  
|<span data-ttu-id="bd432-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="bd432-252">RichTextBox</span></span>|  
|<span data-ttu-id="bd432-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="bd432-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="bd432-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="bd432-254">ScrollableControl</span></span>|  
|<span data-ttu-id="bd432-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="bd432-255">SoundPlayer</span></span>|  
|<span data-ttu-id="bd432-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="bd432-256">StatusBar</span></span>|  
|<span data-ttu-id="bd432-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="bd432-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="bd432-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="bd432-258">TextBox</span></span>|  
|<span data-ttu-id="bd432-259">タイマ</span><span class="sxs-lookup"><span data-stu-id="bd432-259">Timer</span></span>|  
|<span data-ttu-id="bd432-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="bd432-260">Toolbar</span></span>|  
|<span data-ttu-id="bd432-261">ToolTip</span><span class="sxs-lookup"><span data-stu-id="bd432-261">ToolTip</span></span>|  
|<span data-ttu-id="bd432-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="bd432-262">TrackBar</span></span>|  
|<span data-ttu-id="bd432-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="bd432-263">TreeView</span></span>|  
|<span data-ttu-id="bd432-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="bd432-264">VscrollBar</span></span>|  
|<span data-ttu-id="bd432-265">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="bd432-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="bd432-266">次のコントロールは、Microsoft Active Accessibility のサポートを通じてのみ [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] に公開されます。</span><span class="sxs-lookup"><span data-stu-id="bd432-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="bd432-267">一部の機能が使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="bd432-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="bd432-268">コントロール名</span><span class="sxs-lookup"><span data-stu-id="bd432-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="bd432-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="bd432-269">BindingSource</span></span>|  
|<span data-ttu-id="bd432-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="bd432-270">DataGrid</span></span>|  
|<span data-ttu-id="bd432-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="bd432-271">DataGridView</span></span>|  
|<span data-ttu-id="bd432-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="bd432-272">DataNavigator</span></span>|  
|<span data-ttu-id="bd432-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="bd432-273">DomainUpDown</span></span>|  
|<span data-ttu-id="bd432-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="bd432-274">ErrorProvider</span></span>|  
|<span data-ttu-id="bd432-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="bd432-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="bd432-276">フォーム</span><span class="sxs-lookup"><span data-stu-id="bd432-276">Form</span></span>|  
|<span data-ttu-id="bd432-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="bd432-277">LinkLabel</span></span>|  
|<span data-ttu-id="bd432-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="bd432-278">HelpProvider</span></span>|  
|<span data-ttu-id="bd432-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="bd432-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="bd432-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="bd432-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="bd432-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="bd432-281">NumericUpDown</span></span>|  
|<span data-ttu-id="bd432-282">パネル</span><span class="sxs-lookup"><span data-stu-id="bd432-282">Panel</span></span>|  
|<span data-ttu-id="bd432-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="bd432-283">PictureBox</span></span>|  
|<span data-ttu-id="bd432-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="bd432-284">PrintDocument</span></span>|  
|<span data-ttu-id="bd432-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="bd432-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="bd432-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="bd432-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="bd432-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="bd432-287">PropertyGrid</span></span>|  
|<span data-ttu-id="bd432-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="bd432-288">UserControl</span></span>|  
|<span data-ttu-id="bd432-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="bd432-289">ToolStrip</span></span>|  
|<span data-ttu-id="bd432-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="bd432-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="bd432-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="bd432-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="bd432-292">スプリッター</span><span class="sxs-lookup"><span data-stu-id="bd432-292">Splitter</span></span>|  
|<span data-ttu-id="bd432-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="bd432-293">RaftingContainer</span></span>|  
|<span data-ttu-id="bd432-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="bd432-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd432-295">参照</span><span class="sxs-lookup"><span data-stu-id="bd432-295">See also</span></span>

- [<span data-ttu-id="bd432-296">UI オートメーション コントロール型</span><span class="sxs-lookup"><span data-stu-id="bd432-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
