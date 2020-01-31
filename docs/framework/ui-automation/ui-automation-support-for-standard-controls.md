---
title: UI オートメーションによる標準コントロールのサポート
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 49277073706444fd611ae41e762442388ac50b71
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789601"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="67784-102">UI オートメーションによる標準コントロールのサポート</span><span class="sxs-lookup"><span data-stu-id="67784-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="67784-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="67784-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="67784-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI オートメーション](/windows/win32/winauto/entry-uiauto-win32)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67784-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="67784-105">このトピックでは、[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]、Win32、および Windows フォームフレームワーク用に開発されたアプリケーションの標準コントロールに対する [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="67784-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="67784-106">Windows Presentation Foundation コントロール</span><span class="sxs-lookup"><span data-stu-id="67784-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="67784-107">ユーザー操作に関する情報やサポートを提供するすべての [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] コントロール要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を全面的にネイティブ サポートしています。</span><span class="sxs-lookup"><span data-stu-id="67784-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="67784-108">パネルなどのその他の要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]からは認識できません。</span><span class="sxs-lookup"><span data-stu-id="67784-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="67784-109">Win32 コントロール</span><span class="sxs-lookup"><span data-stu-id="67784-109">Win32 Controls</span></span>  
 <span data-ttu-id="67784-110">ほとんどの Win32 コントロールは、、Uiautomationclientsideproviders.dll のクライアント側プロバイダーを通じて [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] に公開されます。</span><span class="sxs-lookup"><span data-stu-id="67784-110">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="67784-111">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="67784-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="67784-112">完全サポートは、 *、comctrl32.dll*のバージョン6のコントロールに対してのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="67784-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="67784-113">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="67784-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="67784-114">[クラス名]</span><span class="sxs-lookup"><span data-stu-id="67784-114">Class name</span></span>|<span data-ttu-id="67784-115">コントロール型</span><span class="sxs-lookup"><span data-stu-id="67784-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="67784-116">Button</span><span class="sxs-lookup"><span data-stu-id="67784-116">Button</span></span>|<span data-ttu-id="67784-117">Button</span><span class="sxs-lookup"><span data-stu-id="67784-117">Button</span></span>|  
|<span data-ttu-id="67784-118">Button</span><span class="sxs-lookup"><span data-stu-id="67784-118">Button</span></span>|<span data-ttu-id="67784-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="67784-119">RadioButton</span></span>|  
|<span data-ttu-id="67784-120">Button</span><span class="sxs-lookup"><span data-stu-id="67784-120">Button</span></span>|<span data-ttu-id="67784-121">グループ</span><span class="sxs-lookup"><span data-stu-id="67784-121">Group</span></span>|  
|<span data-ttu-id="67784-122">Button</span><span class="sxs-lookup"><span data-stu-id="67784-122">Button</span></span>|<span data-ttu-id="67784-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="67784-123">CheckBox</span></span>|  
|<span data-ttu-id="67784-124">Button</span><span class="sxs-lookup"><span data-stu-id="67784-124">Button</span></span>|<span data-ttu-id="67784-125">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="67784-125">Hyperlink</span></span>|  
|<span data-ttu-id="67784-126">Button</span><span class="sxs-lookup"><span data-stu-id="67784-126">Button</span></span>|<span data-ttu-id="67784-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="67784-127">SplitButton</span></span>|  
|<span data-ttu-id="67784-128">Button</span><span class="sxs-lookup"><span data-stu-id="67784-128">Button</span></span>|<span data-ttu-id="67784-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="67784-129">CheckBox</span></span>|  
|<span data-ttu-id="67784-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="67784-130">ComboBoxEx32</span></span>|<span data-ttu-id="67784-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="67784-131">ComboBox</span></span>|  
|<span data-ttu-id="67784-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="67784-132">ComboBox</span></span>|<span data-ttu-id="67784-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="67784-133">ComboBox</span></span>|  
|<span data-ttu-id="67784-134">[編集]</span><span class="sxs-lookup"><span data-stu-id="67784-134">Edit</span></span>|<span data-ttu-id="67784-135">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="67784-135">Document</span></span>|  
|<span data-ttu-id="67784-136">[編集]</span><span class="sxs-lookup"><span data-stu-id="67784-136">Edit</span></span>|<span data-ttu-id="67784-137">[編集]</span><span class="sxs-lookup"><span data-stu-id="67784-137">Edit</span></span>|  
|<span data-ttu-id="67784-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="67784-138">SysLink</span></span>|<span data-ttu-id="67784-139">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="67784-139">Hyperlink</span></span>|  
|<span data-ttu-id="67784-140">スタティック</span><span class="sxs-lookup"><span data-stu-id="67784-140">Static</span></span>|<span data-ttu-id="67784-141">テキスト</span><span class="sxs-lookup"><span data-stu-id="67784-141">Text</span></span>|  
|<span data-ttu-id="67784-142">スタティック</span><span class="sxs-lookup"><span data-stu-id="67784-142">Static</span></span>|<span data-ttu-id="67784-143">イメージ</span><span class="sxs-lookup"><span data-stu-id="67784-143">Image</span></span>|  
|<span data-ttu-id="67784-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="67784-144">SysIPAddress32</span></span>|<span data-ttu-id="67784-145">カスタム</span><span class="sxs-lookup"><span data-stu-id="67784-145">Custom</span></span>|  
|<span data-ttu-id="67784-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="67784-146">SysHeader32</span></span>|<span data-ttu-id="67784-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="67784-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="67784-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="67784-148">SysListView32</span></span>|<span data-ttu-id="67784-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="67784-149">DataGrid</span></span>|  
|<span data-ttu-id="67784-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="67784-150">SysListView32</span></span>|<span data-ttu-id="67784-151">リスト型</span><span class="sxs-lookup"><span data-stu-id="67784-151">List</span></span>|  
|<span data-ttu-id="67784-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="67784-152">ListBox</span></span>|<span data-ttu-id="67784-153">リスト型</span><span class="sxs-lookup"><span data-stu-id="67784-153">List</span></span>|  
|<span data-ttu-id="67784-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="67784-154">ListBox</span></span>|<span data-ttu-id="67784-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="67784-155">ListItem</span></span>|  
|<span data-ttu-id="67784-156">#32768</span><span class="sxs-lookup"><span data-stu-id="67784-156">#32768</span></span>|<span data-ttu-id="67784-157">メニュー</span><span class="sxs-lookup"><span data-stu-id="67784-157">Menu</span></span>|  
|<span data-ttu-id="67784-158">#32768</span><span class="sxs-lookup"><span data-stu-id="67784-158">#32768</span></span>|<span data-ttu-id="67784-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="67784-159">MenuItem</span></span>|  
|<span data-ttu-id="67784-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="67784-160">msctls_progress32</span></span>|<span data-ttu-id="67784-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="67784-161">ProgressBar</span></span>|  
|<span data-ttu-id="67784-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="67784-162">RichEdit</span></span>|<span data-ttu-id="67784-163">ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="67784-163">Document.</span></span> <span data-ttu-id="67784-164">注を参照。</span><span class="sxs-lookup"><span data-stu-id="67784-164">See note.</span></span>|  
|<span data-ttu-id="67784-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="67784-165">RichEdit20A</span></span>|<span data-ttu-id="67784-166">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="67784-166">Document</span></span>|  
|<span data-ttu-id="67784-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="67784-167">RichEdit20W</span></span>|<span data-ttu-id="67784-168">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="67784-168">Document</span></span>|  
|<span data-ttu-id="67784-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="67784-169">RichEdit50W</span></span>|<span data-ttu-id="67784-170">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="67784-170">Document</span></span>|  
|<span data-ttu-id="67784-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="67784-171">ScrollBar</span></span>|<span data-ttu-id="67784-172">[スライダー]</span><span class="sxs-lookup"><span data-stu-id="67784-172">Slider</span></span>|  
|<span data-ttu-id="67784-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="67784-173">msctls_trackbar32</span></span>|<span data-ttu-id="67784-174">[スライダー]</span><span class="sxs-lookup"><span data-stu-id="67784-174">Slider</span></span>|  
|<span data-ttu-id="67784-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="67784-175">msctls_updown32</span></span>|<span data-ttu-id="67784-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="67784-176">Spinner</span></span>|  
|<span data-ttu-id="67784-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="67784-177">msctls_statusbar32</span></span>|<span data-ttu-id="67784-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="67784-178">StatusBar</span></span>|  
|<span data-ttu-id="67784-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="67784-179">SysTabControl32</span></span>|<span data-ttu-id="67784-180">タブ</span><span class="sxs-lookup"><span data-stu-id="67784-180">Tab</span></span>|  
|<span data-ttu-id="67784-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="67784-181">SysTabControl32</span></span>|<span data-ttu-id="67784-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="67784-182">TabItem</span></span>|  
|<span data-ttu-id="67784-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="67784-183">ToolbarWindow32</span></span>|<span data-ttu-id="67784-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="67784-184">ToolBar</span></span>|  
|<span data-ttu-id="67784-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="67784-185">ToolbarWindow32</span></span>|<span data-ttu-id="67784-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="67784-186">MenuItem</span></span>|  
|<span data-ttu-id="67784-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="67784-187">ToolbarWindow32</span></span>|<span data-ttu-id="67784-188">Button</span><span class="sxs-lookup"><span data-stu-id="67784-188">Button</span></span>|  
|<span data-ttu-id="67784-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="67784-189">ToolbarWindow32</span></span>|<span data-ttu-id="67784-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="67784-190">CheckBox</span></span>|  
|<span data-ttu-id="67784-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="67784-191">ToolbarWindow32</span></span>|<span data-ttu-id="67784-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="67784-192">RadioButton</span></span>|  
|<span data-ttu-id="67784-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="67784-193">ToolbarWindow32</span></span>|<span data-ttu-id="67784-194">[区切り文字]</span><span class="sxs-lookup"><span data-stu-id="67784-194">Separator</span></span>|  
|<span data-ttu-id="67784-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="67784-195">tooltips_class32</span></span>|<span data-ttu-id="67784-196">ToolTip</span><span class="sxs-lookup"><span data-stu-id="67784-196">ToolTip</span></span>|  
|<span data-ttu-id="67784-197">#32774</span><span class="sxs-lookup"><span data-stu-id="67784-197">#32774</span></span>|<span data-ttu-id="67784-198">ToolTip</span><span class="sxs-lookup"><span data-stu-id="67784-198">ToolTip</span></span>|  
|<span data-ttu-id="67784-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="67784-199">ReBarWindow32</span></span>|<span data-ttu-id="67784-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="67784-200">Toolbar</span></span>|  
|<span data-ttu-id="67784-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="67784-201">SysTreeView32</span></span>|<span data-ttu-id="67784-202">ツリー</span><span class="sxs-lookup"><span data-stu-id="67784-202">Tree</span></span>|  
|<span data-ttu-id="67784-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="67784-203">SysTreeView32</span></span>|<span data-ttu-id="67784-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="67784-204">TreeItem</span></span>|  
  
 <span data-ttu-id="67784-205">**メモ**RichEdit コントロールは、Windows Vista に付属するバージョン (Riched20.dll バージョン3.1 以降では、MsftEdit .dll バージョン4.1 以降) でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="67784-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="67784-206">次のコントロールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="67784-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="67784-207">[クラス名]</span><span class="sxs-lookup"><span data-stu-id="67784-207">Class name</span></span>|<span data-ttu-id="67784-208">コントロール型</span><span class="sxs-lookup"><span data-stu-id="67784-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="67784-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="67784-209">SysAnimate32</span></span>|<span data-ttu-id="67784-210">イメージ</span><span class="sxs-lookup"><span data-stu-id="67784-210">Image</span></span>|  
|<span data-ttu-id="67784-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="67784-211">SysPager</span></span>|<span data-ttu-id="67784-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="67784-212">Spinner</span></span>|  
|<span data-ttu-id="67784-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="67784-213">SysDateTimePick32</span></span>|<span data-ttu-id="67784-214">カスタム</span><span class="sxs-lookup"><span data-stu-id="67784-214">Custom</span></span>|  
|<span data-ttu-id="67784-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="67784-215">SysMonthCal32</span></span>|<span data-ttu-id="67784-216">カレンダー</span><span class="sxs-lookup"><span data-stu-id="67784-216">Calendar</span></span>|  
|<span data-ttu-id="67784-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="67784-217">MS_WINNOTE</span></span>|<span data-ttu-id="67784-218">Tooltip</span><span class="sxs-lookup"><span data-stu-id="67784-218">Tooltip</span></span>|  
|<span data-ttu-id="67784-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="67784-219">VBBubble</span></span>|<span data-ttu-id="67784-220">Tooltip</span><span class="sxs-lookup"><span data-stu-id="67784-220">Tooltip</span></span>|  
|<span data-ttu-id="67784-221">ScrollBar (スタンドアロン コントロールとして使用される場合)</span><span class="sxs-lookup"><span data-stu-id="67784-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="67784-222">[スライダー]</span><span class="sxs-lookup"><span data-stu-id="67784-222">Slider</span></span>|  
|<span data-ttu-id="67784-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="67784-223">SuperGrid</span></span>|<span data-ttu-id="67784-224">カスタム</span><span class="sxs-lookup"><span data-stu-id="67784-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="67784-225">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="67784-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="67784-226">Windows フォームコントロールは、、Uiautomationclientsideproviders.dll のクライアント側プロバイダーを介して [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] に公開されます。</span><span class="sxs-lookup"><span data-stu-id="67784-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="67784-227">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="67784-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="67784-228">通常、Win32 コモンコントロールのマネージラッパーである Windows フォームコントロールは [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]によってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="67784-228">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="67784-229">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="67784-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="67784-230">クラス名</span><span class="sxs-lookup"><span data-stu-id="67784-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="67784-231">Button</span><span class="sxs-lookup"><span data-stu-id="67784-231">Button</span></span>|  
|<span data-ttu-id="67784-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="67784-232">CheckBox</span></span>|  
|<span data-ttu-id="67784-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="67784-233">CheckedListBox</span></span>|  
|<span data-ttu-id="67784-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="67784-234">ColorDialog</span></span>|  
|<span data-ttu-id="67784-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="67784-235">ComboBox</span></span>|  
|<span data-ttu-id="67784-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="67784-236">FolderBrowser</span></span>|  
|<span data-ttu-id="67784-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="67784-237">FontDialog</span></span>|  
|<span data-ttu-id="67784-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="67784-238">GroupBox</span></span>|  
|<span data-ttu-id="67784-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="67784-239">HscrollBar</span></span>|  
|<span data-ttu-id="67784-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="67784-240">ImageList</span></span>|  
|<span data-ttu-id="67784-241">[ラベル]</span><span class="sxs-lookup"><span data-stu-id="67784-241">Label</span></span>|  
|<span data-ttu-id="67784-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="67784-242">ListBox</span></span>|  
|<span data-ttu-id="67784-243">ListView</span><span class="sxs-lookup"><span data-stu-id="67784-243">ListView</span></span>|  
|<span data-ttu-id="67784-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="67784-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="67784-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="67784-245">MonthCalendar</span></span>|  
|<span data-ttu-id="67784-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="67784-246">NotifyIcon</span></span>|  
|<span data-ttu-id="67784-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="67784-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="67784-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="67784-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="67784-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="67784-249">PrintDialog</span></span>|  
|<span data-ttu-id="67784-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="67784-250">ProgressBar</span></span>|  
|<span data-ttu-id="67784-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="67784-251">RadioButton</span></span>|  
|<span data-ttu-id="67784-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="67784-252">RichTextBox</span></span>|  
|<span data-ttu-id="67784-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="67784-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="67784-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="67784-254">ScrollableControl</span></span>|  
|<span data-ttu-id="67784-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="67784-255">SoundPlayer</span></span>|  
|<span data-ttu-id="67784-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="67784-256">StatusBar</span></span>|  
|<span data-ttu-id="67784-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="67784-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="67784-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="67784-258">TextBox</span></span>|  
|<span data-ttu-id="67784-259">タイマ</span><span class="sxs-lookup"><span data-stu-id="67784-259">Timer</span></span>|  
|<span data-ttu-id="67784-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="67784-260">Toolbar</span></span>|  
|<span data-ttu-id="67784-261">ToolTip</span><span class="sxs-lookup"><span data-stu-id="67784-261">ToolTip</span></span>|  
|<span data-ttu-id="67784-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="67784-262">TrackBar</span></span>|  
|<span data-ttu-id="67784-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="67784-263">TreeView</span></span>|  
|<span data-ttu-id="67784-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="67784-264">VscrollBar</span></span>|  
|<span data-ttu-id="67784-265">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="67784-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="67784-266">次のコントロールは、Microsoft Active Accessibility のサポートを通じてのみ [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] に公開されます。</span><span class="sxs-lookup"><span data-stu-id="67784-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="67784-267">一部の機能が使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="67784-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="67784-268">コントロール名</span><span class="sxs-lookup"><span data-stu-id="67784-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="67784-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="67784-269">BindingSource</span></span>|  
|<span data-ttu-id="67784-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="67784-270">DataGrid</span></span>|  
|<span data-ttu-id="67784-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="67784-271">DataGridView</span></span>|  
|<span data-ttu-id="67784-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="67784-272">DataNavigator</span></span>|  
|<span data-ttu-id="67784-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="67784-273">DomainUpDown</span></span>|  
|<span data-ttu-id="67784-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="67784-274">ErrorProvider</span></span>|  
|<span data-ttu-id="67784-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="67784-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="67784-276">フォーム</span><span class="sxs-lookup"><span data-stu-id="67784-276">Form</span></span>|  
|<span data-ttu-id="67784-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="67784-277">LinkLabel</span></span>|  
|<span data-ttu-id="67784-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="67784-278">HelpProvider</span></span>|  
|<span data-ttu-id="67784-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="67784-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="67784-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="67784-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="67784-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="67784-281">NumericUpDown</span></span>|  
|<span data-ttu-id="67784-282">パネル</span><span class="sxs-lookup"><span data-stu-id="67784-282">Panel</span></span>|  
|<span data-ttu-id="67784-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="67784-283">PictureBox</span></span>|  
|<span data-ttu-id="67784-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="67784-284">PrintDocument</span></span>|  
|<span data-ttu-id="67784-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="67784-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="67784-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="67784-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="67784-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="67784-287">PropertyGrid</span></span>|  
|<span data-ttu-id="67784-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="67784-288">UserControl</span></span>|  
|<span data-ttu-id="67784-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="67784-289">ToolStrip</span></span>|  
|<span data-ttu-id="67784-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="67784-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="67784-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="67784-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="67784-292">スプリッター</span><span class="sxs-lookup"><span data-stu-id="67784-292">Splitter</span></span>|  
|<span data-ttu-id="67784-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="67784-293">RaftingContainer</span></span>|  
|<span data-ttu-id="67784-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="67784-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67784-295">関連項目</span><span class="sxs-lookup"><span data-stu-id="67784-295">See also</span></span>

- [<span data-ttu-id="67784-296">UI Automation Control Types</span><span class="sxs-lookup"><span data-stu-id="67784-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
