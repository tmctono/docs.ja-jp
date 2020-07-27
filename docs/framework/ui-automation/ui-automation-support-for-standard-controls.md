---
title: UI オートメーションによる標準コントロールのサポート
description: Windows Presentation Foundation (WPF)、Win32、Windows フォーム用に開発されたアプリケーションの標準コントロールに対する UI オートメーションのサポートに関する情報を入手します。
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 17916a6978008439e91caae00d8b6f26045f9018
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166120"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="d5242-103">UI オートメーションによる標準コントロールのサポート</span><span class="sxs-lookup"><span data-stu-id="d5242-103">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="d5242-104">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="d5242-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d5242-105">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI オートメーション](/windows/win32/winauto/entry-uiauto-win32)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d5242-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="d5242-106">このトピックで [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] は [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 、、Win32、および Windows フォームフレームワーク用に開発されたアプリケーションの標準コントロールのサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d5242-106">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="d5242-107">Windows Presentation Foundation コントロール</span><span class="sxs-lookup"><span data-stu-id="d5242-107">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="d5242-108">ユーザー操作に関する情報やサポートを提供するすべての [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] コントロール要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を全面的にネイティブ サポートしています。</span><span class="sxs-lookup"><span data-stu-id="d5242-108">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="d5242-109">パネルなどのその他の要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]からは認識できません。</span><span class="sxs-lookup"><span data-stu-id="d5242-109">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a><span data-ttu-id="d5242-110">Win32 コントロール</span><span class="sxs-lookup"><span data-stu-id="d5242-110">Win32 Controls</span></span>  
 <span data-ttu-id="d5242-111">ほとんどの Win32 コントロールは、 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] UIAutomationClientsideProviders.dll のクライアント側プロバイダーを介してに公開されます。</span><span class="sxs-lookup"><span data-stu-id="d5242-111">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="d5242-112">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="d5242-112">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="d5242-113">完全サポートは、バージョン6の*ComCtrl32.dll*のコントロールに対してのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="d5242-113">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="d5242-114">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d5242-114">The following controls are supported.</span></span>  
  
|<span data-ttu-id="d5242-115">クラス名</span><span class="sxs-lookup"><span data-stu-id="d5242-115">Class name</span></span>|<span data-ttu-id="d5242-116">コントロール型</span><span class="sxs-lookup"><span data-stu-id="d5242-116">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="d5242-117">Button</span><span class="sxs-lookup"><span data-stu-id="d5242-117">Button</span></span>|<span data-ttu-id="d5242-118">Button</span><span class="sxs-lookup"><span data-stu-id="d5242-118">Button</span></span>|  
|<span data-ttu-id="d5242-119">Button</span><span class="sxs-lookup"><span data-stu-id="d5242-119">Button</span></span>|<span data-ttu-id="d5242-120">RadioButton</span><span class="sxs-lookup"><span data-stu-id="d5242-120">RadioButton</span></span>|  
|<span data-ttu-id="d5242-121">Button</span><span class="sxs-lookup"><span data-stu-id="d5242-121">Button</span></span>|<span data-ttu-id="d5242-122">グループ</span><span class="sxs-lookup"><span data-stu-id="d5242-122">Group</span></span>|  
|<span data-ttu-id="d5242-123">Button</span><span class="sxs-lookup"><span data-stu-id="d5242-123">Button</span></span>|<span data-ttu-id="d5242-124">CheckBox</span><span class="sxs-lookup"><span data-stu-id="d5242-124">CheckBox</span></span>|  
|<span data-ttu-id="d5242-125">Button</span><span class="sxs-lookup"><span data-stu-id="d5242-125">Button</span></span>|<span data-ttu-id="d5242-126">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="d5242-126">Hyperlink</span></span>|  
|<span data-ttu-id="d5242-127">Button</span><span class="sxs-lookup"><span data-stu-id="d5242-127">Button</span></span>|<span data-ttu-id="d5242-128">SplitButton</span><span class="sxs-lookup"><span data-stu-id="d5242-128">SplitButton</span></span>|  
|<span data-ttu-id="d5242-129">Button</span><span class="sxs-lookup"><span data-stu-id="d5242-129">Button</span></span>|<span data-ttu-id="d5242-130">CheckBox</span><span class="sxs-lookup"><span data-stu-id="d5242-130">CheckBox</span></span>|  
|<span data-ttu-id="d5242-131">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="d5242-131">ComboBoxEx32</span></span>|<span data-ttu-id="d5242-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="d5242-132">ComboBox</span></span>|  
|<span data-ttu-id="d5242-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="d5242-133">ComboBox</span></span>|<span data-ttu-id="d5242-134">ComboBox</span><span class="sxs-lookup"><span data-stu-id="d5242-134">ComboBox</span></span>|  
|<span data-ttu-id="d5242-135">編集</span><span class="sxs-lookup"><span data-stu-id="d5242-135">Edit</span></span>|<span data-ttu-id="d5242-136">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="d5242-136">Document</span></span>|  
|<span data-ttu-id="d5242-137">編集</span><span class="sxs-lookup"><span data-stu-id="d5242-137">Edit</span></span>|<span data-ttu-id="d5242-138">編集</span><span class="sxs-lookup"><span data-stu-id="d5242-138">Edit</span></span>|  
|<span data-ttu-id="d5242-139">SysLink</span><span class="sxs-lookup"><span data-stu-id="d5242-139">SysLink</span></span>|<span data-ttu-id="d5242-140">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="d5242-140">Hyperlink</span></span>|  
|<span data-ttu-id="d5242-141">静的</span><span class="sxs-lookup"><span data-stu-id="d5242-141">Static</span></span>|<span data-ttu-id="d5242-142">テキスト</span><span class="sxs-lookup"><span data-stu-id="d5242-142">Text</span></span>|  
|<span data-ttu-id="d5242-143">静的</span><span class="sxs-lookup"><span data-stu-id="d5242-143">Static</span></span>|<span data-ttu-id="d5242-144">Image</span><span class="sxs-lookup"><span data-stu-id="d5242-144">Image</span></span>|  
|<span data-ttu-id="d5242-145">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="d5242-145">SysIPAddress32</span></span>|<span data-ttu-id="d5242-146">カスタム</span><span class="sxs-lookup"><span data-stu-id="d5242-146">Custom</span></span>|  
|<span data-ttu-id="d5242-147">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="d5242-147">SysHeader32</span></span>|<span data-ttu-id="d5242-148">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="d5242-148">Header/HeaderItem</span></span>|  
|<span data-ttu-id="d5242-149">SysListView32</span><span class="sxs-lookup"><span data-stu-id="d5242-149">SysListView32</span></span>|<span data-ttu-id="d5242-150">DataGrid</span><span class="sxs-lookup"><span data-stu-id="d5242-150">DataGrid</span></span>|  
|<span data-ttu-id="d5242-151">SysListView32</span><span class="sxs-lookup"><span data-stu-id="d5242-151">SysListView32</span></span>|<span data-ttu-id="d5242-152">List</span><span class="sxs-lookup"><span data-stu-id="d5242-152">List</span></span>|  
|<span data-ttu-id="d5242-153">ListBox</span><span class="sxs-lookup"><span data-stu-id="d5242-153">ListBox</span></span>|<span data-ttu-id="d5242-154">List</span><span class="sxs-lookup"><span data-stu-id="d5242-154">List</span></span>|  
|<span data-ttu-id="d5242-155">ListBox</span><span class="sxs-lookup"><span data-stu-id="d5242-155">ListBox</span></span>|<span data-ttu-id="d5242-156">ListItem</span><span class="sxs-lookup"><span data-stu-id="d5242-156">ListItem</span></span>|  
|<span data-ttu-id="d5242-157">#32768</span><span class="sxs-lookup"><span data-stu-id="d5242-157">#32768</span></span>|<span data-ttu-id="d5242-158">メニュー</span><span class="sxs-lookup"><span data-stu-id="d5242-158">Menu</span></span>|  
|<span data-ttu-id="d5242-159">#32768</span><span class="sxs-lookup"><span data-stu-id="d5242-159">#32768</span></span>|<span data-ttu-id="d5242-160">MenuItem</span><span class="sxs-lookup"><span data-stu-id="d5242-160">MenuItem</span></span>|  
|<span data-ttu-id="d5242-161">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="d5242-161">msctls_progress32</span></span>|<span data-ttu-id="d5242-162">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="d5242-162">ProgressBar</span></span>|  
|<span data-ttu-id="d5242-163">RichEdit</span><span class="sxs-lookup"><span data-stu-id="d5242-163">RichEdit</span></span>|<span data-ttu-id="d5242-164">ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="d5242-164">Document.</span></span> <span data-ttu-id="d5242-165">「注」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5242-165">See note.</span></span>|  
|<span data-ttu-id="d5242-166">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="d5242-166">RichEdit20A</span></span>|<span data-ttu-id="d5242-167">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="d5242-167">Document</span></span>|  
|<span data-ttu-id="d5242-168">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="d5242-168">RichEdit20W</span></span>|<span data-ttu-id="d5242-169">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="d5242-169">Document</span></span>|  
|<span data-ttu-id="d5242-170">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="d5242-170">RichEdit50W</span></span>|<span data-ttu-id="d5242-171">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="d5242-171">Document</span></span>|  
|<span data-ttu-id="d5242-172">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="d5242-172">ScrollBar</span></span>|<span data-ttu-id="d5242-173">スライダー</span><span class="sxs-lookup"><span data-stu-id="d5242-173">Slider</span></span>|  
|<span data-ttu-id="d5242-174">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="d5242-174">msctls_trackbar32</span></span>|<span data-ttu-id="d5242-175">スライダー</span><span class="sxs-lookup"><span data-stu-id="d5242-175">Slider</span></span>|  
|<span data-ttu-id="d5242-176">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="d5242-176">msctls_updown32</span></span>|<span data-ttu-id="d5242-177">Spinner</span><span class="sxs-lookup"><span data-stu-id="d5242-177">Spinner</span></span>|  
|<span data-ttu-id="d5242-178">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="d5242-178">msctls_statusbar32</span></span>|<span data-ttu-id="d5242-179">StatusBar</span><span class="sxs-lookup"><span data-stu-id="d5242-179">StatusBar</span></span>|  
|<span data-ttu-id="d5242-180">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="d5242-180">SysTabControl32</span></span>|<span data-ttu-id="d5242-181">タブ</span><span class="sxs-lookup"><span data-stu-id="d5242-181">Tab</span></span>|  
|<span data-ttu-id="d5242-182">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="d5242-182">SysTabControl32</span></span>|<span data-ttu-id="d5242-183">TabItem</span><span class="sxs-lookup"><span data-stu-id="d5242-183">TabItem</span></span>|  
|<span data-ttu-id="d5242-184">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d5242-184">ToolbarWindow32</span></span>|<span data-ttu-id="d5242-185">ToolBar</span><span class="sxs-lookup"><span data-stu-id="d5242-185">ToolBar</span></span>|  
|<span data-ttu-id="d5242-186">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d5242-186">ToolbarWindow32</span></span>|<span data-ttu-id="d5242-187">MenuItem</span><span class="sxs-lookup"><span data-stu-id="d5242-187">MenuItem</span></span>|  
|<span data-ttu-id="d5242-188">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d5242-188">ToolbarWindow32</span></span>|<span data-ttu-id="d5242-189">Button</span><span class="sxs-lookup"><span data-stu-id="d5242-189">Button</span></span>|  
|<span data-ttu-id="d5242-190">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d5242-190">ToolbarWindow32</span></span>|<span data-ttu-id="d5242-191">CheckBox</span><span class="sxs-lookup"><span data-stu-id="d5242-191">CheckBox</span></span>|  
|<span data-ttu-id="d5242-192">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d5242-192">ToolbarWindow32</span></span>|<span data-ttu-id="d5242-193">RadioButton</span><span class="sxs-lookup"><span data-stu-id="d5242-193">RadioButton</span></span>|  
|<span data-ttu-id="d5242-194">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="d5242-194">ToolbarWindow32</span></span>|<span data-ttu-id="d5242-195">区切り記号</span><span class="sxs-lookup"><span data-stu-id="d5242-195">Separator</span></span>|  
|<span data-ttu-id="d5242-196">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="d5242-196">tooltips_class32</span></span>|<span data-ttu-id="d5242-197">ヒント</span><span class="sxs-lookup"><span data-stu-id="d5242-197">ToolTip</span></span>|  
|<span data-ttu-id="d5242-198">#32774</span><span class="sxs-lookup"><span data-stu-id="d5242-198">#32774</span></span>|<span data-ttu-id="d5242-199">ヒント</span><span class="sxs-lookup"><span data-stu-id="d5242-199">ToolTip</span></span>|  
|<span data-ttu-id="d5242-200">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="d5242-200">ReBarWindow32</span></span>|<span data-ttu-id="d5242-201">ツール バー</span><span class="sxs-lookup"><span data-stu-id="d5242-201">Toolbar</span></span>|  
|<span data-ttu-id="d5242-202">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="d5242-202">SysTreeView32</span></span>|<span data-ttu-id="d5242-203">ツリー</span><span class="sxs-lookup"><span data-stu-id="d5242-203">Tree</span></span>|  
|<span data-ttu-id="d5242-204">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="d5242-204">SysTreeView32</span></span>|<span data-ttu-id="d5242-205">TreeItem</span><span class="sxs-lookup"><span data-stu-id="d5242-205">TreeItem</span></span>|  
  
 <span data-ttu-id="d5242-206">**メモ**RichEdit コントロールは、Windows Vista に付属しているバージョン (RichEd20.dll バージョン3.1 以降では MsftEdit.dll バージョン4.1 以降) でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d5242-206">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="d5242-207">次のコントロールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d5242-207">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="d5242-208">クラス名</span><span class="sxs-lookup"><span data-stu-id="d5242-208">Class name</span></span>|<span data-ttu-id="d5242-209">コントロール型</span><span class="sxs-lookup"><span data-stu-id="d5242-209">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="d5242-210">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="d5242-210">SysAnimate32</span></span>|<span data-ttu-id="d5242-211">Image</span><span class="sxs-lookup"><span data-stu-id="d5242-211">Image</span></span>|  
|<span data-ttu-id="d5242-212">SysPager</span><span class="sxs-lookup"><span data-stu-id="d5242-212">SysPager</span></span>|<span data-ttu-id="d5242-213">Spinner</span><span class="sxs-lookup"><span data-stu-id="d5242-213">Spinner</span></span>|  
|<span data-ttu-id="d5242-214">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="d5242-214">SysDateTimePick32</span></span>|<span data-ttu-id="d5242-215">カスタム</span><span class="sxs-lookup"><span data-stu-id="d5242-215">Custom</span></span>|  
|<span data-ttu-id="d5242-216">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="d5242-216">SysMonthCal32</span></span>|<span data-ttu-id="d5242-217">予定表</span><span class="sxs-lookup"><span data-stu-id="d5242-217">Calendar</span></span>|  
|<span data-ttu-id="d5242-218">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="d5242-218">MS_WINNOTE</span></span>|<span data-ttu-id="d5242-219">ヒント</span><span class="sxs-lookup"><span data-stu-id="d5242-219">Tooltip</span></span>|  
|<span data-ttu-id="d5242-220">VBBubble</span><span class="sxs-lookup"><span data-stu-id="d5242-220">VBBubble</span></span>|<span data-ttu-id="d5242-221">ヒント</span><span class="sxs-lookup"><span data-stu-id="d5242-221">Tooltip</span></span>|  
|<span data-ttu-id="d5242-222">ScrollBar (スタンドアロン コントロールとして使用される場合)</span><span class="sxs-lookup"><span data-stu-id="d5242-222">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="d5242-223">スライダー</span><span class="sxs-lookup"><span data-stu-id="d5242-223">Slider</span></span>|  
|<span data-ttu-id="d5242-224">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="d5242-224">SuperGrid</span></span>|<span data-ttu-id="d5242-225">カスタム</span><span class="sxs-lookup"><span data-stu-id="d5242-225">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a><span data-ttu-id="d5242-226">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="d5242-226">Windows Forms Controls</span></span>  
 <span data-ttu-id="d5242-227">Windows フォームコントロールは、 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] UIAutomationClientsideProviders.dll のクライアント側プロバイダーを介してに公開されます。</span><span class="sxs-lookup"><span data-stu-id="d5242-227">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="d5242-228">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="d5242-228">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="d5242-229">通常、Win32 コモンコントロールのマネージラッパーである Windows フォームコントロールは、でサポートされてい [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ます。</span><span class="sxs-lookup"><span data-stu-id="d5242-229">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="d5242-230">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d5242-230">The following controls are supported.</span></span>  
  
|<span data-ttu-id="d5242-231">Class Name (クラス名)</span><span class="sxs-lookup"><span data-stu-id="d5242-231">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="d5242-232">Button</span><span class="sxs-lookup"><span data-stu-id="d5242-232">Button</span></span>|  
|<span data-ttu-id="d5242-233">CheckBox</span><span class="sxs-lookup"><span data-stu-id="d5242-233">CheckBox</span></span>|  
|<span data-ttu-id="d5242-234">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="d5242-234">CheckedListBox</span></span>|  
|<span data-ttu-id="d5242-235">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="d5242-235">ColorDialog</span></span>|  
|<span data-ttu-id="d5242-236">ComboBox</span><span class="sxs-lookup"><span data-stu-id="d5242-236">ComboBox</span></span>|  
|<span data-ttu-id="d5242-237">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="d5242-237">FolderBrowser</span></span>|  
|<span data-ttu-id="d5242-238">FontDialog</span><span class="sxs-lookup"><span data-stu-id="d5242-238">FontDialog</span></span>|  
|<span data-ttu-id="d5242-239">GroupBox</span><span class="sxs-lookup"><span data-stu-id="d5242-239">GroupBox</span></span>|  
|<span data-ttu-id="d5242-240">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="d5242-240">HscrollBar</span></span>|  
|<span data-ttu-id="d5242-241">ImageList</span><span class="sxs-lookup"><span data-stu-id="d5242-241">ImageList</span></span>|  
|<span data-ttu-id="d5242-242">ラベル</span><span class="sxs-lookup"><span data-stu-id="d5242-242">Label</span></span>|  
|<span data-ttu-id="d5242-243">ListBox</span><span class="sxs-lookup"><span data-stu-id="d5242-243">ListBox</span></span>|  
|<span data-ttu-id="d5242-244">ListView</span><span class="sxs-lookup"><span data-stu-id="d5242-244">ListView</span></span>|  
|<span data-ttu-id="d5242-245">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="d5242-245">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="d5242-246">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="d5242-246">MonthCalendar</span></span>|  
|<span data-ttu-id="d5242-247">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="d5242-247">NotifyIcon</span></span>|  
|<span data-ttu-id="d5242-248">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="d5242-248">OpenFileDialog</span></span>|  
|<span data-ttu-id="d5242-249">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="d5242-249">PageSetupDialog</span></span>|  
|<span data-ttu-id="d5242-250">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="d5242-250">PrintDialog</span></span>|  
|<span data-ttu-id="d5242-251">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="d5242-251">ProgressBar</span></span>|  
|<span data-ttu-id="d5242-252">RadioButton</span><span class="sxs-lookup"><span data-stu-id="d5242-252">RadioButton</span></span>|  
|<span data-ttu-id="d5242-253">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="d5242-253">RichTextBox</span></span>|  
|<span data-ttu-id="d5242-254">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="d5242-254">SaveFileDialog</span></span>|  
|<span data-ttu-id="d5242-255">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="d5242-255">ScrollableControl</span></span>|  
|<span data-ttu-id="d5242-256">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="d5242-256">SoundPlayer</span></span>|  
|<span data-ttu-id="d5242-257">StatusBar</span><span class="sxs-lookup"><span data-stu-id="d5242-257">StatusBar</span></span>|  
|<span data-ttu-id="d5242-258">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="d5242-258">TabControl/TabPage</span></span>|  
|<span data-ttu-id="d5242-259">TextBox</span><span class="sxs-lookup"><span data-stu-id="d5242-259">TextBox</span></span>|  
|<span data-ttu-id="d5242-260">Timer</span><span class="sxs-lookup"><span data-stu-id="d5242-260">Timer</span></span>|  
|<span data-ttu-id="d5242-261">ツール バー</span><span class="sxs-lookup"><span data-stu-id="d5242-261">Toolbar</span></span>|  
|<span data-ttu-id="d5242-262">ヒント</span><span class="sxs-lookup"><span data-stu-id="d5242-262">ToolTip</span></span>|  
|<span data-ttu-id="d5242-263">TrackBar</span><span class="sxs-lookup"><span data-stu-id="d5242-263">TrackBar</span></span>|  
|<span data-ttu-id="d5242-264">TreeView</span><span class="sxs-lookup"><span data-stu-id="d5242-264">TreeView</span></span>|  
|<span data-ttu-id="d5242-265">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="d5242-265">VscrollBar</span></span>|  
|<span data-ttu-id="d5242-266">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="d5242-266">WebBrowser</span></span>|  
  
 <span data-ttu-id="d5242-267">次のコントロールは、 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Microsoft Active Accessibility のサポートを通じてのみに公開されます。</span><span class="sxs-lookup"><span data-stu-id="d5242-267">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="d5242-268">一部の機能が使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d5242-268">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="d5242-269">コントロール名</span><span class="sxs-lookup"><span data-stu-id="d5242-269">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="d5242-270">BindingSource</span><span class="sxs-lookup"><span data-stu-id="d5242-270">BindingSource</span></span>|  
|<span data-ttu-id="d5242-271">DataGrid</span><span class="sxs-lookup"><span data-stu-id="d5242-271">DataGrid</span></span>|  
|<span data-ttu-id="d5242-272">DataGridView</span><span class="sxs-lookup"><span data-stu-id="d5242-272">DataGridView</span></span>|  
|<span data-ttu-id="d5242-273">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="d5242-273">DataNavigator</span></span>|  
|<span data-ttu-id="d5242-274">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="d5242-274">DomainUpDown</span></span>|  
|<span data-ttu-id="d5242-275">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="d5242-275">ErrorProvider</span></span>|  
|<span data-ttu-id="d5242-276">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d5242-276">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="d5242-277">フォーム</span><span class="sxs-lookup"><span data-stu-id="d5242-277">Form</span></span>|  
|<span data-ttu-id="d5242-278">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="d5242-278">LinkLabel</span></span>|  
|<span data-ttu-id="d5242-279">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="d5242-279">HelpProvider</span></span>|  
|<span data-ttu-id="d5242-280">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="d5242-280">MaskedTextBox</span></span>|  
|<span data-ttu-id="d5242-281">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="d5242-281">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="d5242-282">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="d5242-282">NumericUpDown</span></span>|  
|<span data-ttu-id="d5242-283">パネル</span><span class="sxs-lookup"><span data-stu-id="d5242-283">Panel</span></span>|  
|<span data-ttu-id="d5242-284">PictureBox</span><span class="sxs-lookup"><span data-stu-id="d5242-284">PictureBox</span></span>|  
|<span data-ttu-id="d5242-285">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="d5242-285">PrintDocument</span></span>|  
|<span data-ttu-id="d5242-286">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="d5242-286">PrintPreview-Control</span></span>|  
|<span data-ttu-id="d5242-287">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="d5242-287">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="d5242-288">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="d5242-288">PropertyGrid</span></span>|  
|<span data-ttu-id="d5242-289">UserControl</span><span class="sxs-lookup"><span data-stu-id="d5242-289">UserControl</span></span>|  
|<span data-ttu-id="d5242-290">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d5242-290">ToolStrip</span></span>|  
|<span data-ttu-id="d5242-291">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d5242-291">TableLayoutPanel</span></span>|  
|<span data-ttu-id="d5242-292">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="d5242-292">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="d5242-293">スプリッター</span><span class="sxs-lookup"><span data-stu-id="d5242-293">Splitter</span></span>|  
|<span data-ttu-id="d5242-294">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="d5242-294">RaftingContainer</span></span>|  
|<span data-ttu-id="d5242-295">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="d5242-295">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5242-296">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5242-296">See also</span></span>

- [<span data-ttu-id="d5242-297">UI オートメーション コントロール型</span><span class="sxs-lookup"><span data-stu-id="d5242-297">UI Automation Control Types</span></span>](ui-automation-control-types.md)
