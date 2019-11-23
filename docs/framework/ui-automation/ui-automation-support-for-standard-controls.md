---
title: UI オートメーションによる標準コントロールのサポート
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: c59352f908c5f4a1fd2ca6dd631d26bb5d69f09a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441225"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="a877e-102">UI オートメーションによる標準コントロールのサポート</span><span class="sxs-lookup"><span data-stu-id="a877e-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="a877e-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="a877e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a877e-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI Automation (Windows のオートメーション API: UI オートメーション)](/windows/win32/winauto/entry-uiauto-win32)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a877e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="a877e-105">このトピックでは、 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 、 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]、および [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]フレームワーク向けに開発されたアプリケーションの標準コントロールに対する [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] サポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a877e-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="a877e-106">Windows Presentation Foundation コントロール</span><span class="sxs-lookup"><span data-stu-id="a877e-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="a877e-107">ユーザー操作に関する情報やサポートを提供するすべての [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] コントロール要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を全面的にネイティブ サポートしています。</span><span class="sxs-lookup"><span data-stu-id="a877e-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="a877e-108">パネルなどのその他の要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]からは認識できません。</span><span class="sxs-lookup"><span data-stu-id="a877e-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="a877e-109">Win32 コントロール</span><span class="sxs-lookup"><span data-stu-id="a877e-109">Win32 Controls</span></span>  
 <span data-ttu-id="a877e-110">ほとんどの [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] コントロールは、UIAutomationClientsideProviders.dll のクライアント側プロバイダーによって [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] に公開されています。</span><span class="sxs-lookup"><span data-stu-id="a877e-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="a877e-111">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="a877e-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="a877e-112">完全なサポートは、ComCtrl32.dll のバージョン 6 ( [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] 以降で使用可能) のコントロールに対してのみ提供されています。</span><span class="sxs-lookup"><span data-stu-id="a877e-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="a877e-113">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a877e-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="a877e-114">クラス名</span><span class="sxs-lookup"><span data-stu-id="a877e-114">Class name</span></span>|<span data-ttu-id="a877e-115">コントロール型</span><span class="sxs-lookup"><span data-stu-id="a877e-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="a877e-116">Button</span><span class="sxs-lookup"><span data-stu-id="a877e-116">Button</span></span>|<span data-ttu-id="a877e-117">Button</span><span class="sxs-lookup"><span data-stu-id="a877e-117">Button</span></span>|  
|<span data-ttu-id="a877e-118">Button</span><span class="sxs-lookup"><span data-stu-id="a877e-118">Button</span></span>|<span data-ttu-id="a877e-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a877e-119">RadioButton</span></span>|  
|<span data-ttu-id="a877e-120">Button</span><span class="sxs-lookup"><span data-stu-id="a877e-120">Button</span></span>|<span data-ttu-id="a877e-121">グループ化</span><span class="sxs-lookup"><span data-stu-id="a877e-121">Group</span></span>|  
|<span data-ttu-id="a877e-122">Button</span><span class="sxs-lookup"><span data-stu-id="a877e-122">Button</span></span>|<span data-ttu-id="a877e-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a877e-123">CheckBox</span></span>|  
|<span data-ttu-id="a877e-124">Button</span><span class="sxs-lookup"><span data-stu-id="a877e-124">Button</span></span>|<span data-ttu-id="a877e-125">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="a877e-125">Hyperlink</span></span>|  
|<span data-ttu-id="a877e-126">Button</span><span class="sxs-lookup"><span data-stu-id="a877e-126">Button</span></span>|<span data-ttu-id="a877e-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="a877e-127">SplitButton</span></span>|  
|<span data-ttu-id="a877e-128">Button</span><span class="sxs-lookup"><span data-stu-id="a877e-128">Button</span></span>|<span data-ttu-id="a877e-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a877e-129">CheckBox</span></span>|  
|<span data-ttu-id="a877e-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="a877e-130">ComboBoxEx32</span></span>|<span data-ttu-id="a877e-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a877e-131">ComboBox</span></span>|  
|<span data-ttu-id="a877e-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a877e-132">ComboBox</span></span>|<span data-ttu-id="a877e-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a877e-133">ComboBox</span></span>|  
|<span data-ttu-id="a877e-134">編集</span><span class="sxs-lookup"><span data-stu-id="a877e-134">Edit</span></span>|<span data-ttu-id="a877e-135">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="a877e-135">Document</span></span>|  
|<span data-ttu-id="a877e-136">編集</span><span class="sxs-lookup"><span data-stu-id="a877e-136">Edit</span></span>|<span data-ttu-id="a877e-137">編集</span><span class="sxs-lookup"><span data-stu-id="a877e-137">Edit</span></span>|  
|<span data-ttu-id="a877e-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="a877e-138">SysLink</span></span>|<span data-ttu-id="a877e-139">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="a877e-139">Hyperlink</span></span>|  
|<span data-ttu-id="a877e-140">スタティック</span><span class="sxs-lookup"><span data-stu-id="a877e-140">Static</span></span>|<span data-ttu-id="a877e-141">テキスト</span><span class="sxs-lookup"><span data-stu-id="a877e-141">Text</span></span>|  
|<span data-ttu-id="a877e-142">スタティック</span><span class="sxs-lookup"><span data-stu-id="a877e-142">Static</span></span>|<span data-ttu-id="a877e-143">Image</span><span class="sxs-lookup"><span data-stu-id="a877e-143">Image</span></span>|  
|<span data-ttu-id="a877e-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="a877e-144">SysIPAddress32</span></span>|<span data-ttu-id="a877e-145">カスタム</span><span class="sxs-lookup"><span data-stu-id="a877e-145">Custom</span></span>|  
|<span data-ttu-id="a877e-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="a877e-146">SysHeader32</span></span>|<span data-ttu-id="a877e-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="a877e-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="a877e-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="a877e-148">SysListView32</span></span>|<span data-ttu-id="a877e-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="a877e-149">DataGrid</span></span>|  
|<span data-ttu-id="a877e-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="a877e-150">SysListView32</span></span>|<span data-ttu-id="a877e-151">リスト</span><span class="sxs-lookup"><span data-stu-id="a877e-151">List</span></span>|  
|<span data-ttu-id="a877e-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="a877e-152">ListBox</span></span>|<span data-ttu-id="a877e-153">リスト</span><span class="sxs-lookup"><span data-stu-id="a877e-153">List</span></span>|  
|<span data-ttu-id="a877e-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="a877e-154">ListBox</span></span>|<span data-ttu-id="a877e-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="a877e-155">ListItem</span></span>|  
|<span data-ttu-id="a877e-156">#32768</span><span class="sxs-lookup"><span data-stu-id="a877e-156">#32768</span></span>|<span data-ttu-id="a877e-157">メニュー</span><span class="sxs-lookup"><span data-stu-id="a877e-157">Menu</span></span>|  
|<span data-ttu-id="a877e-158">#32768</span><span class="sxs-lookup"><span data-stu-id="a877e-158">#32768</span></span>|<span data-ttu-id="a877e-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="a877e-159">MenuItem</span></span>|  
|<span data-ttu-id="a877e-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="a877e-160">msctls_progress32</span></span>|<span data-ttu-id="a877e-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="a877e-161">ProgressBar</span></span>|  
|<span data-ttu-id="a877e-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="a877e-162">RichEdit</span></span>|<span data-ttu-id="a877e-163">ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="a877e-163">Document.</span></span> <span data-ttu-id="a877e-164">注を参照。</span><span class="sxs-lookup"><span data-stu-id="a877e-164">See note.</span></span>|  
|<span data-ttu-id="a877e-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="a877e-165">RichEdit20A</span></span>|<span data-ttu-id="a877e-166">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="a877e-166">Document</span></span>|  
|<span data-ttu-id="a877e-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="a877e-167">RichEdit20W</span></span>|<span data-ttu-id="a877e-168">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="a877e-168">Document</span></span>|  
|<span data-ttu-id="a877e-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="a877e-169">RichEdit50W</span></span>|<span data-ttu-id="a877e-170">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="a877e-170">Document</span></span>|  
|<span data-ttu-id="a877e-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="a877e-171">ScrollBar</span></span>|<span data-ttu-id="a877e-172">Slider</span><span class="sxs-lookup"><span data-stu-id="a877e-172">Slider</span></span>|  
|<span data-ttu-id="a877e-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="a877e-173">msctls_trackbar32</span></span>|<span data-ttu-id="a877e-174">Slider</span><span class="sxs-lookup"><span data-stu-id="a877e-174">Slider</span></span>|  
|<span data-ttu-id="a877e-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="a877e-175">msctls_updown32</span></span>|<span data-ttu-id="a877e-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="a877e-176">Spinner</span></span>|  
|<span data-ttu-id="a877e-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="a877e-177">msctls_statusbar32</span></span>|<span data-ttu-id="a877e-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="a877e-178">StatusBar</span></span>|  
|<span data-ttu-id="a877e-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="a877e-179">SysTabControl32</span></span>|<span data-ttu-id="a877e-180">タブ</span><span class="sxs-lookup"><span data-stu-id="a877e-180">Tab</span></span>|  
|<span data-ttu-id="a877e-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="a877e-181">SysTabControl32</span></span>|<span data-ttu-id="a877e-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="a877e-182">TabItem</span></span>|  
|<span data-ttu-id="a877e-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a877e-183">ToolbarWindow32</span></span>|<span data-ttu-id="a877e-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="a877e-184">ToolBar</span></span>|  
|<span data-ttu-id="a877e-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a877e-185">ToolbarWindow32</span></span>|<span data-ttu-id="a877e-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="a877e-186">MenuItem</span></span>|  
|<span data-ttu-id="a877e-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a877e-187">ToolbarWindow32</span></span>|<span data-ttu-id="a877e-188">Button</span><span class="sxs-lookup"><span data-stu-id="a877e-188">Button</span></span>|  
|<span data-ttu-id="a877e-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a877e-189">ToolbarWindow32</span></span>|<span data-ttu-id="a877e-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a877e-190">CheckBox</span></span>|  
|<span data-ttu-id="a877e-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a877e-191">ToolbarWindow32</span></span>|<span data-ttu-id="a877e-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a877e-192">RadioButton</span></span>|  
|<span data-ttu-id="a877e-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="a877e-193">ToolbarWindow32</span></span>|<span data-ttu-id="a877e-194">区切り記号</span><span class="sxs-lookup"><span data-stu-id="a877e-194">Separator</span></span>|  
|<span data-ttu-id="a877e-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="a877e-195">tooltips_class32</span></span>|<span data-ttu-id="a877e-196">ヒント</span><span class="sxs-lookup"><span data-stu-id="a877e-196">ToolTip</span></span>|  
|<span data-ttu-id="a877e-197">#32774</span><span class="sxs-lookup"><span data-stu-id="a877e-197">#32774</span></span>|<span data-ttu-id="a877e-198">ヒント</span><span class="sxs-lookup"><span data-stu-id="a877e-198">ToolTip</span></span>|  
|<span data-ttu-id="a877e-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="a877e-199">ReBarWindow32</span></span>|<span data-ttu-id="a877e-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="a877e-200">Toolbar</span></span>|  
|<span data-ttu-id="a877e-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="a877e-201">SysTreeView32</span></span>|<span data-ttu-id="a877e-202">ツリー</span><span class="sxs-lookup"><span data-stu-id="a877e-202">Tree</span></span>|  
|<span data-ttu-id="a877e-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="a877e-203">SysTreeView32</span></span>|<span data-ttu-id="a877e-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="a877e-204">TreeItem</span></span>|  
  
 <span data-ttu-id="a877e-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span><span class="sxs-lookup"><span data-stu-id="a877e-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="a877e-206">次のコントロールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a877e-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="a877e-207">クラス名</span><span class="sxs-lookup"><span data-stu-id="a877e-207">Class name</span></span>|<span data-ttu-id="a877e-208">コントロール型</span><span class="sxs-lookup"><span data-stu-id="a877e-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="a877e-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="a877e-209">SysAnimate32</span></span>|<span data-ttu-id="a877e-210">Image</span><span class="sxs-lookup"><span data-stu-id="a877e-210">Image</span></span>|  
|<span data-ttu-id="a877e-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="a877e-211">SysPager</span></span>|<span data-ttu-id="a877e-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="a877e-212">Spinner</span></span>|  
|<span data-ttu-id="a877e-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="a877e-213">SysDateTimePick32</span></span>|<span data-ttu-id="a877e-214">カスタム</span><span class="sxs-lookup"><span data-stu-id="a877e-214">Custom</span></span>|  
|<span data-ttu-id="a877e-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="a877e-215">SysMonthCal32</span></span>|<span data-ttu-id="a877e-216">予定表</span><span class="sxs-lookup"><span data-stu-id="a877e-216">Calendar</span></span>|  
|<span data-ttu-id="a877e-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="a877e-217">MS_WINNOTE</span></span>|<span data-ttu-id="a877e-218">ヒント</span><span class="sxs-lookup"><span data-stu-id="a877e-218">Tooltip</span></span>|  
|<span data-ttu-id="a877e-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="a877e-219">VBBubble</span></span>|<span data-ttu-id="a877e-220">ヒント</span><span class="sxs-lookup"><span data-stu-id="a877e-220">Tooltip</span></span>|  
|<span data-ttu-id="a877e-221">ScrollBar (スタンドアロン コントロールとして使用される場合)</span><span class="sxs-lookup"><span data-stu-id="a877e-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="a877e-222">Slider</span><span class="sxs-lookup"><span data-stu-id="a877e-222">Slider</span></span>|  
|<span data-ttu-id="a877e-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="a877e-223">SuperGrid</span></span>|<span data-ttu-id="a877e-224">カスタム</span><span class="sxs-lookup"><span data-stu-id="a877e-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="a877e-225">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="a877e-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="a877e-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="a877e-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="a877e-227">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="a877e-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="a877e-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a877e-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="a877e-229">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a877e-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="a877e-230">クラス名</span><span class="sxs-lookup"><span data-stu-id="a877e-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="a877e-231">Button</span><span class="sxs-lookup"><span data-stu-id="a877e-231">Button</span></span>|  
|<span data-ttu-id="a877e-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="a877e-232">CheckBox</span></span>|  
|<span data-ttu-id="a877e-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="a877e-233">CheckedListBox</span></span>|  
|<span data-ttu-id="a877e-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="a877e-234">ColorDialog</span></span>|  
|<span data-ttu-id="a877e-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="a877e-235">ComboBox</span></span>|  
|<span data-ttu-id="a877e-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="a877e-236">FolderBrowser</span></span>|  
|<span data-ttu-id="a877e-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="a877e-237">FontDialog</span></span>|  
|<span data-ttu-id="a877e-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="a877e-238">GroupBox</span></span>|  
|<span data-ttu-id="a877e-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="a877e-239">HscrollBar</span></span>|  
|<span data-ttu-id="a877e-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="a877e-240">ImageList</span></span>|  
|<span data-ttu-id="a877e-241">group1</span><span class="sxs-lookup"><span data-stu-id="a877e-241">Label</span></span>|  
|<span data-ttu-id="a877e-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="a877e-242">ListBox</span></span>|  
|<span data-ttu-id="a877e-243">ListView</span><span class="sxs-lookup"><span data-stu-id="a877e-243">ListView</span></span>|  
|<span data-ttu-id="a877e-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="a877e-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="a877e-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="a877e-245">MonthCalendar</span></span>|  
|<span data-ttu-id="a877e-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="a877e-246">NotifyIcon</span></span>|  
|<span data-ttu-id="a877e-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="a877e-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="a877e-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="a877e-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="a877e-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="a877e-249">PrintDialog</span></span>|  
|<span data-ttu-id="a877e-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="a877e-250">ProgressBar</span></span>|  
|<span data-ttu-id="a877e-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a877e-251">RadioButton</span></span>|  
|<span data-ttu-id="a877e-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="a877e-252">RichTextBox</span></span>|  
|<span data-ttu-id="a877e-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="a877e-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="a877e-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="a877e-254">ScrollableControl</span></span>|  
|<span data-ttu-id="a877e-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="a877e-255">SoundPlayer</span></span>|  
|<span data-ttu-id="a877e-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="a877e-256">StatusBar</span></span>|  
|<span data-ttu-id="a877e-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="a877e-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="a877e-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="a877e-258">TextBox</span></span>|  
|<span data-ttu-id="a877e-259">タイマー</span><span class="sxs-lookup"><span data-stu-id="a877e-259">Timer</span></span>|  
|<span data-ttu-id="a877e-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="a877e-260">Toolbar</span></span>|  
|<span data-ttu-id="a877e-261">ヒント</span><span class="sxs-lookup"><span data-stu-id="a877e-261">ToolTip</span></span>|  
|<span data-ttu-id="a877e-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="a877e-262">TrackBar</span></span>|  
|<span data-ttu-id="a877e-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="a877e-263">TreeView</span></span>|  
|<span data-ttu-id="a877e-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="a877e-264">VscrollBar</span></span>|  
|<span data-ttu-id="a877e-265">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="a877e-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="a877e-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="a877e-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="a877e-267">一部の機能が使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="a877e-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="a877e-268">コントロール名</span><span class="sxs-lookup"><span data-stu-id="a877e-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="a877e-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="a877e-269">BindingSource</span></span>|  
|<span data-ttu-id="a877e-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="a877e-270">DataGrid</span></span>|  
|<span data-ttu-id="a877e-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="a877e-271">DataGridView</span></span>|  
|<span data-ttu-id="a877e-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="a877e-272">DataNavigator</span></span>|  
|<span data-ttu-id="a877e-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="a877e-273">DomainUpDown</span></span>|  
|<span data-ttu-id="a877e-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="a877e-274">ErrorProvider</span></span>|  
|<span data-ttu-id="a877e-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a877e-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="a877e-276">フォーム</span><span class="sxs-lookup"><span data-stu-id="a877e-276">Form</span></span>|  
|<span data-ttu-id="a877e-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="a877e-277">LinkLabel</span></span>|  
|<span data-ttu-id="a877e-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="a877e-278">HelpProvider</span></span>|  
|<span data-ttu-id="a877e-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="a877e-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="a877e-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="a877e-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="a877e-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="a877e-281">NumericUpDown</span></span>|  
|<span data-ttu-id="a877e-282">パネル</span><span class="sxs-lookup"><span data-stu-id="a877e-282">Panel</span></span>|  
|<span data-ttu-id="a877e-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="a877e-283">PictureBox</span></span>|  
|<span data-ttu-id="a877e-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="a877e-284">PrintDocument</span></span>|  
|<span data-ttu-id="a877e-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="a877e-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="a877e-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="a877e-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="a877e-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="a877e-287">PropertyGrid</span></span>|  
|<span data-ttu-id="a877e-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="a877e-288">UserControl</span></span>|  
|<span data-ttu-id="a877e-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="a877e-289">ToolStrip</span></span>|  
|<span data-ttu-id="a877e-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a877e-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="a877e-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="a877e-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="a877e-292">スプリッター</span><span class="sxs-lookup"><span data-stu-id="a877e-292">Splitter</span></span>|  
|<span data-ttu-id="a877e-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="a877e-293">RaftingContainer</span></span>|  
|<span data-ttu-id="a877e-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="a877e-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a877e-295">関連項目</span><span class="sxs-lookup"><span data-stu-id="a877e-295">See also</span></span>

- [<span data-ttu-id="a877e-296">UI オートメーション コントロール型</span><span class="sxs-lookup"><span data-stu-id="a877e-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
