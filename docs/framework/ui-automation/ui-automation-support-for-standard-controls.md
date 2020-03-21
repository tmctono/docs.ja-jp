---
title: UI オートメーションによる標準コントロールのサポート
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 36028d589e98177f6a0e83092edd656860b1a8d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179851"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="77c4b-102">UI オートメーションによる標準コントロールのサポート</span><span class="sxs-lookup"><span data-stu-id="77c4b-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="77c4b-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="77c4b-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="77c4b-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI オートメーション](/windows/win32/winauto/entry-uiauto-win32)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="77c4b-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="77c4b-105">このトピックでは、 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 、 Win32 、 Windows[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]フォーム の各フレームワーク用に開発されたアプリケーションでの標準コントロールのサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="77c4b-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="77c4b-106">Windows Presentation Foundation コントロール</span><span class="sxs-lookup"><span data-stu-id="77c4b-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="77c4b-107">ユーザー操作に関する情報やサポートを提供するすべての [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] コントロール要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を全面的にネイティブ サポートしています。</span><span class="sxs-lookup"><span data-stu-id="77c4b-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="77c4b-108">パネルなどのその他の要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]からは認識できません。</span><span class="sxs-lookup"><span data-stu-id="77c4b-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a><span data-ttu-id="77c4b-109">Win32 コントロール</span><span class="sxs-lookup"><span data-stu-id="77c4b-109">Win32 Controls</span></span>  
 <span data-ttu-id="77c4b-110">ほとんどの Win32 コントロールは、[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]クライアント側プロバイダーを通じて公開されます。</span><span class="sxs-lookup"><span data-stu-id="77c4b-110">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="77c4b-111">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="77c4b-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="77c4b-112">完全サポートは、バージョン 6 の*ComCtrl32.dll*のコントロールに対してのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="77c4b-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="77c4b-113">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="77c4b-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="77c4b-114">クラス名</span><span class="sxs-lookup"><span data-stu-id="77c4b-114">Class name</span></span>|<span data-ttu-id="77c4b-115">コントロール型</span><span class="sxs-lookup"><span data-stu-id="77c4b-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="77c4b-116">ボタン</span><span class="sxs-lookup"><span data-stu-id="77c4b-116">Button</span></span>|<span data-ttu-id="77c4b-117">ボタン</span><span class="sxs-lookup"><span data-stu-id="77c4b-117">Button</span></span>|  
|<span data-ttu-id="77c4b-118">ボタン</span><span class="sxs-lookup"><span data-stu-id="77c4b-118">Button</span></span>|<span data-ttu-id="77c4b-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="77c4b-119">RadioButton</span></span>|  
|<span data-ttu-id="77c4b-120">ボタン</span><span class="sxs-lookup"><span data-stu-id="77c4b-120">Button</span></span>|<span data-ttu-id="77c4b-121">グループ</span><span class="sxs-lookup"><span data-stu-id="77c4b-121">Group</span></span>|  
|<span data-ttu-id="77c4b-122">ボタン</span><span class="sxs-lookup"><span data-stu-id="77c4b-122">Button</span></span>|<span data-ttu-id="77c4b-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="77c4b-123">CheckBox</span></span>|  
|<span data-ttu-id="77c4b-124">ボタン</span><span class="sxs-lookup"><span data-stu-id="77c4b-124">Button</span></span>|<span data-ttu-id="77c4b-125">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="77c4b-125">Hyperlink</span></span>|  
|<span data-ttu-id="77c4b-126">ボタン</span><span class="sxs-lookup"><span data-stu-id="77c4b-126">Button</span></span>|<span data-ttu-id="77c4b-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="77c4b-127">SplitButton</span></span>|  
|<span data-ttu-id="77c4b-128">ボタン</span><span class="sxs-lookup"><span data-stu-id="77c4b-128">Button</span></span>|<span data-ttu-id="77c4b-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="77c4b-129">CheckBox</span></span>|  
|<span data-ttu-id="77c4b-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="77c4b-130">ComboBoxEx32</span></span>|<span data-ttu-id="77c4b-131">コンボ ボックス</span><span class="sxs-lookup"><span data-stu-id="77c4b-131">ComboBox</span></span>|  
|<span data-ttu-id="77c4b-132">コンボ ボックス</span><span class="sxs-lookup"><span data-stu-id="77c4b-132">ComboBox</span></span>|<span data-ttu-id="77c4b-133">コンボ ボックス</span><span class="sxs-lookup"><span data-stu-id="77c4b-133">ComboBox</span></span>|  
|<span data-ttu-id="77c4b-134">[編集]</span><span class="sxs-lookup"><span data-stu-id="77c4b-134">Edit</span></span>|<span data-ttu-id="77c4b-135">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="77c4b-135">Document</span></span>|  
|<span data-ttu-id="77c4b-136">[編集]</span><span class="sxs-lookup"><span data-stu-id="77c4b-136">Edit</span></span>|<span data-ttu-id="77c4b-137">[編集]</span><span class="sxs-lookup"><span data-stu-id="77c4b-137">Edit</span></span>|  
|<span data-ttu-id="77c4b-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="77c4b-138">SysLink</span></span>|<span data-ttu-id="77c4b-139">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="77c4b-139">Hyperlink</span></span>|  
|<span data-ttu-id="77c4b-140">静的</span><span class="sxs-lookup"><span data-stu-id="77c4b-140">Static</span></span>|<span data-ttu-id="77c4b-141">Text</span><span class="sxs-lookup"><span data-stu-id="77c4b-141">Text</span></span>|  
|<span data-ttu-id="77c4b-142">静的</span><span class="sxs-lookup"><span data-stu-id="77c4b-142">Static</span></span>|<span data-ttu-id="77c4b-143">Image</span><span class="sxs-lookup"><span data-stu-id="77c4b-143">Image</span></span>|  
|<span data-ttu-id="77c4b-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="77c4b-144">SysIPAddress32</span></span>|<span data-ttu-id="77c4b-145">Custom</span><span class="sxs-lookup"><span data-stu-id="77c4b-145">Custom</span></span>|  
|<span data-ttu-id="77c4b-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="77c4b-146">SysHeader32</span></span>|<span data-ttu-id="77c4b-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="77c4b-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="77c4b-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="77c4b-148">SysListView32</span></span>|<span data-ttu-id="77c4b-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="77c4b-149">DataGrid</span></span>|  
|<span data-ttu-id="77c4b-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="77c4b-150">SysListView32</span></span>|<span data-ttu-id="77c4b-151">List</span><span class="sxs-lookup"><span data-stu-id="77c4b-151">List</span></span>|  
|<span data-ttu-id="77c4b-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="77c4b-152">ListBox</span></span>|<span data-ttu-id="77c4b-153">List</span><span class="sxs-lookup"><span data-stu-id="77c4b-153">List</span></span>|  
|<span data-ttu-id="77c4b-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="77c4b-154">ListBox</span></span>|<span data-ttu-id="77c4b-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="77c4b-155">ListItem</span></span>|  
|<span data-ttu-id="77c4b-156">#32768</span><span class="sxs-lookup"><span data-stu-id="77c4b-156">#32768</span></span>|<span data-ttu-id="77c4b-157">メニュー</span><span class="sxs-lookup"><span data-stu-id="77c4b-157">Menu</span></span>|  
|<span data-ttu-id="77c4b-158">#32768</span><span class="sxs-lookup"><span data-stu-id="77c4b-158">#32768</span></span>|<span data-ttu-id="77c4b-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="77c4b-159">MenuItem</span></span>|  
|<span data-ttu-id="77c4b-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="77c4b-160">msctls_progress32</span></span>|<span data-ttu-id="77c4b-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="77c4b-161">ProgressBar</span></span>|  
|<span data-ttu-id="77c4b-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="77c4b-162">RichEdit</span></span>|<span data-ttu-id="77c4b-163">ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="77c4b-163">Document.</span></span> <span data-ttu-id="77c4b-164">注を参照。</span><span class="sxs-lookup"><span data-stu-id="77c4b-164">See note.</span></span>|  
|<span data-ttu-id="77c4b-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="77c4b-165">RichEdit20A</span></span>|<span data-ttu-id="77c4b-166">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="77c4b-166">Document</span></span>|  
|<span data-ttu-id="77c4b-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="77c4b-167">RichEdit20W</span></span>|<span data-ttu-id="77c4b-168">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="77c4b-168">Document</span></span>|  
|<span data-ttu-id="77c4b-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="77c4b-169">RichEdit50W</span></span>|<span data-ttu-id="77c4b-170">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="77c4b-170">Document</span></span>|  
|<span data-ttu-id="77c4b-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="77c4b-171">ScrollBar</span></span>|<span data-ttu-id="77c4b-172">スライダー</span><span class="sxs-lookup"><span data-stu-id="77c4b-172">Slider</span></span>|  
|<span data-ttu-id="77c4b-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="77c4b-173">msctls_trackbar32</span></span>|<span data-ttu-id="77c4b-174">スライダー</span><span class="sxs-lookup"><span data-stu-id="77c4b-174">Slider</span></span>|  
|<span data-ttu-id="77c4b-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="77c4b-175">msctls_updown32</span></span>|<span data-ttu-id="77c4b-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="77c4b-176">Spinner</span></span>|  
|<span data-ttu-id="77c4b-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="77c4b-177">msctls_statusbar32</span></span>|<span data-ttu-id="77c4b-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="77c4b-178">StatusBar</span></span>|  
|<span data-ttu-id="77c4b-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="77c4b-179">SysTabControl32</span></span>|<span data-ttu-id="77c4b-180">タブ</span><span class="sxs-lookup"><span data-stu-id="77c4b-180">Tab</span></span>|  
|<span data-ttu-id="77c4b-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="77c4b-181">SysTabControl32</span></span>|<span data-ttu-id="77c4b-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="77c4b-182">TabItem</span></span>|  
|<span data-ttu-id="77c4b-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="77c4b-183">ToolbarWindow32</span></span>|<span data-ttu-id="77c4b-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="77c4b-184">ToolBar</span></span>|  
|<span data-ttu-id="77c4b-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="77c4b-185">ToolbarWindow32</span></span>|<span data-ttu-id="77c4b-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="77c4b-186">MenuItem</span></span>|  
|<span data-ttu-id="77c4b-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="77c4b-187">ToolbarWindow32</span></span>|<span data-ttu-id="77c4b-188">ボタン</span><span class="sxs-lookup"><span data-stu-id="77c4b-188">Button</span></span>|  
|<span data-ttu-id="77c4b-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="77c4b-189">ToolbarWindow32</span></span>|<span data-ttu-id="77c4b-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="77c4b-190">CheckBox</span></span>|  
|<span data-ttu-id="77c4b-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="77c4b-191">ToolbarWindow32</span></span>|<span data-ttu-id="77c4b-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="77c4b-192">RadioButton</span></span>|  
|<span data-ttu-id="77c4b-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="77c4b-193">ToolbarWindow32</span></span>|<span data-ttu-id="77c4b-194">区切り記号</span><span class="sxs-lookup"><span data-stu-id="77c4b-194">Separator</span></span>|  
|<span data-ttu-id="77c4b-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="77c4b-195">tooltips_class32</span></span>|<span data-ttu-id="77c4b-196">ヒント</span><span class="sxs-lookup"><span data-stu-id="77c4b-196">ToolTip</span></span>|  
|<span data-ttu-id="77c4b-197">#32774</span><span class="sxs-lookup"><span data-stu-id="77c4b-197">#32774</span></span>|<span data-ttu-id="77c4b-198">ヒント</span><span class="sxs-lookup"><span data-stu-id="77c4b-198">ToolTip</span></span>|  
|<span data-ttu-id="77c4b-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="77c4b-199">ReBarWindow32</span></span>|<span data-ttu-id="77c4b-200">ツール バー</span><span class="sxs-lookup"><span data-stu-id="77c4b-200">Toolbar</span></span>|  
|<span data-ttu-id="77c4b-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="77c4b-201">SysTreeView32</span></span>|<span data-ttu-id="77c4b-202">ツリー</span><span class="sxs-lookup"><span data-stu-id="77c4b-202">Tree</span></span>|  
|<span data-ttu-id="77c4b-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="77c4b-203">SysTreeView32</span></span>|<span data-ttu-id="77c4b-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="77c4b-204">TreeItem</span></span>|  
  
 <span data-ttu-id="77c4b-205">**注**コントロールは、Windows Vista に同梱されているバージョン (リッチエディット 3.1 以降、および MsftEdit.dll バージョン 4.1 以降) でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="77c4b-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="77c4b-206">次のコントロールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="77c4b-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="77c4b-207">クラス名</span><span class="sxs-lookup"><span data-stu-id="77c4b-207">Class name</span></span>|<span data-ttu-id="77c4b-208">コントロール型</span><span class="sxs-lookup"><span data-stu-id="77c4b-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="77c4b-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="77c4b-209">SysAnimate32</span></span>|<span data-ttu-id="77c4b-210">Image</span><span class="sxs-lookup"><span data-stu-id="77c4b-210">Image</span></span>|  
|<span data-ttu-id="77c4b-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="77c4b-211">SysPager</span></span>|<span data-ttu-id="77c4b-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="77c4b-212">Spinner</span></span>|  
|<span data-ttu-id="77c4b-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="77c4b-213">SysDateTimePick32</span></span>|<span data-ttu-id="77c4b-214">Custom</span><span class="sxs-lookup"><span data-stu-id="77c4b-214">Custom</span></span>|  
|<span data-ttu-id="77c4b-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="77c4b-215">SysMonthCal32</span></span>|<span data-ttu-id="77c4b-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="77c4b-216">Calendar</span></span>|  
|<span data-ttu-id="77c4b-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="77c4b-217">MS_WINNOTE</span></span>|<span data-ttu-id="77c4b-218">[ツールヒント]</span><span class="sxs-lookup"><span data-stu-id="77c4b-218">Tooltip</span></span>|  
|<span data-ttu-id="77c4b-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="77c4b-219">VBBubble</span></span>|<span data-ttu-id="77c4b-220">[ツールヒント]</span><span class="sxs-lookup"><span data-stu-id="77c4b-220">Tooltip</span></span>|  
|<span data-ttu-id="77c4b-221">ScrollBar (スタンドアロン コントロールとして使用される場合)</span><span class="sxs-lookup"><span data-stu-id="77c4b-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="77c4b-222">スライダー</span><span class="sxs-lookup"><span data-stu-id="77c4b-222">Slider</span></span>|  
|<span data-ttu-id="77c4b-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="77c4b-223">SuperGrid</span></span>|<span data-ttu-id="77c4b-224">Custom</span><span class="sxs-lookup"><span data-stu-id="77c4b-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a><span data-ttu-id="77c4b-225">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="77c4b-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="77c4b-226">Windows フォーム コントロールは、[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]クライアント側プロバイダーを通じて公開されます。</span><span class="sxs-lookup"><span data-stu-id="77c4b-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="77c4b-227">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="77c4b-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="77c4b-228">通常、Win32 コモン コントロールのマネージ ラッパーである Windows フォーム[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]コントロールは、 でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="77c4b-228">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="77c4b-229">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="77c4b-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="77c4b-230">Class Name (クラス名)</span><span class="sxs-lookup"><span data-stu-id="77c4b-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="77c4b-231">ボタン</span><span class="sxs-lookup"><span data-stu-id="77c4b-231">Button</span></span>|  
|<span data-ttu-id="77c4b-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="77c4b-232">CheckBox</span></span>|  
|<span data-ttu-id="77c4b-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="77c4b-233">CheckedListBox</span></span>|  
|<span data-ttu-id="77c4b-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="77c4b-234">ColorDialog</span></span>|  
|<span data-ttu-id="77c4b-235">コンボ ボックス</span><span class="sxs-lookup"><span data-stu-id="77c4b-235">ComboBox</span></span>|  
|<span data-ttu-id="77c4b-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="77c4b-236">FolderBrowser</span></span>|  
|<span data-ttu-id="77c4b-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="77c4b-237">FontDialog</span></span>|  
|<span data-ttu-id="77c4b-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="77c4b-238">GroupBox</span></span>|  
|<span data-ttu-id="77c4b-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="77c4b-239">HscrollBar</span></span>|  
|<span data-ttu-id="77c4b-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="77c4b-240">ImageList</span></span>|  
|<span data-ttu-id="77c4b-241">Label</span><span class="sxs-lookup"><span data-stu-id="77c4b-241">Label</span></span>|  
|<span data-ttu-id="77c4b-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="77c4b-242">ListBox</span></span>|  
|<span data-ttu-id="77c4b-243">ListView</span><span class="sxs-lookup"><span data-stu-id="77c4b-243">ListView</span></span>|  
|<span data-ttu-id="77c4b-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="77c4b-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="77c4b-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="77c4b-245">MonthCalendar</span></span>|  
|<span data-ttu-id="77c4b-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="77c4b-246">NotifyIcon</span></span>|  
|<span data-ttu-id="77c4b-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="77c4b-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="77c4b-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="77c4b-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="77c4b-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="77c4b-249">PrintDialog</span></span>|  
|<span data-ttu-id="77c4b-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="77c4b-250">ProgressBar</span></span>|  
|<span data-ttu-id="77c4b-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="77c4b-251">RadioButton</span></span>|  
|<span data-ttu-id="77c4b-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="77c4b-252">RichTextBox</span></span>|  
|<span data-ttu-id="77c4b-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="77c4b-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="77c4b-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="77c4b-254">ScrollableControl</span></span>|  
|<span data-ttu-id="77c4b-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="77c4b-255">SoundPlayer</span></span>|  
|<span data-ttu-id="77c4b-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="77c4b-256">StatusBar</span></span>|  
|<span data-ttu-id="77c4b-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="77c4b-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="77c4b-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="77c4b-258">TextBox</span></span>|  
|<span data-ttu-id="77c4b-259">Timer</span><span class="sxs-lookup"><span data-stu-id="77c4b-259">Timer</span></span>|  
|<span data-ttu-id="77c4b-260">ツール バー</span><span class="sxs-lookup"><span data-stu-id="77c4b-260">Toolbar</span></span>|  
|<span data-ttu-id="77c4b-261">ヒント</span><span class="sxs-lookup"><span data-stu-id="77c4b-261">ToolTip</span></span>|  
|<span data-ttu-id="77c4b-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="77c4b-262">TrackBar</span></span>|  
|<span data-ttu-id="77c4b-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="77c4b-263">TreeView</span></span>|  
|<span data-ttu-id="77c4b-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="77c4b-264">VscrollBar</span></span>|  
|<span data-ttu-id="77c4b-265">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="77c4b-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="77c4b-266">次のコントロールは、Microsoft[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]のアクティブ なユーザー補助機能のサポートを通じてのみ公開されます。</span><span class="sxs-lookup"><span data-stu-id="77c4b-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="77c4b-267">一部の機能が使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="77c4b-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="77c4b-268">コントロール名</span><span class="sxs-lookup"><span data-stu-id="77c4b-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="77c4b-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="77c4b-269">BindingSource</span></span>|  
|<span data-ttu-id="77c4b-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="77c4b-270">DataGrid</span></span>|  
|<span data-ttu-id="77c4b-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="77c4b-271">DataGridView</span></span>|  
|<span data-ttu-id="77c4b-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="77c4b-272">DataNavigator</span></span>|  
|<span data-ttu-id="77c4b-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="77c4b-273">DomainUpDown</span></span>|  
|<span data-ttu-id="77c4b-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="77c4b-274">ErrorProvider</span></span>|  
|<span data-ttu-id="77c4b-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="77c4b-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="77c4b-276">Form</span><span class="sxs-lookup"><span data-stu-id="77c4b-276">Form</span></span>|  
|<span data-ttu-id="77c4b-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="77c4b-277">LinkLabel</span></span>|  
|<span data-ttu-id="77c4b-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="77c4b-278">HelpProvider</span></span>|  
|<span data-ttu-id="77c4b-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="77c4b-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="77c4b-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="77c4b-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="77c4b-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="77c4b-281">NumericUpDown</span></span>|  
|<span data-ttu-id="77c4b-282">パネル</span><span class="sxs-lookup"><span data-stu-id="77c4b-282">Panel</span></span>|  
|<span data-ttu-id="77c4b-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="77c4b-283">PictureBox</span></span>|  
|<span data-ttu-id="77c4b-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="77c4b-284">PrintDocument</span></span>|  
|<span data-ttu-id="77c4b-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="77c4b-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="77c4b-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="77c4b-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="77c4b-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="77c4b-287">PropertyGrid</span></span>|  
|<span data-ttu-id="77c4b-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="77c4b-288">UserControl</span></span>|  
|<span data-ttu-id="77c4b-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="77c4b-289">ToolStrip</span></span>|  
|<span data-ttu-id="77c4b-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="77c4b-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="77c4b-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="77c4b-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="77c4b-292">スプリッター</span><span class="sxs-lookup"><span data-stu-id="77c4b-292">Splitter</span></span>|  
|<span data-ttu-id="77c4b-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="77c4b-293">RaftingContainer</span></span>|  
|<span data-ttu-id="77c4b-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="77c4b-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77c4b-295">関連項目</span><span class="sxs-lookup"><span data-stu-id="77c4b-295">See also</span></span>

- [<span data-ttu-id="77c4b-296">UI オートメーション コントロール型</span><span class="sxs-lookup"><span data-stu-id="77c4b-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
