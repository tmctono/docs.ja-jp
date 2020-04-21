---
title: Windows フォームのアクセシビリティの向上
description: .NET Core Windows フォームが .NET Framework の Windows フォームと比較して、アクセシビリティを向上させる方法について説明します。
ms.date: 04/20/2020
helpviewer_keywords:
- Windows Forms accessibility
- accessibility
author: M-Lipin
ms.openlocfilehash: 30eb8b3bd0aaf646ea23f4f036e822f9bba78dc4
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739764"
---
# <a name="accessibility-improvements-in-windows-forms-controls-for-net-core-30"></a><span data-ttu-id="f0f08-103">NET Core 3.0 の Windows フォーム コントロールのアクセシビリティの向上</span><span class="sxs-lookup"><span data-stu-id="f0f08-103">Accessibility improvements in Windows Forms controls for .NET Core 3.0</span></span>

<span data-ttu-id="f0f08-104">Windows フォームでは、ユーザー補助テクノロジの使用方法を改善し、Windows フォームの顧客をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f0f08-104">Windows Forms is continuing to improve how it works with accessibility technologies to better support Windows Forms customers.</span></span> <span data-ttu-id="f0f08-105">次のような改善点があります。</span><span class="sxs-lookup"><span data-stu-id="f0f08-105">These improvements include the following changes:</span></span>

- <span data-ttu-id="f0f08-106">ナレーターを含む、ユーザー補助クライアント アプリケーションとの対話のさまざまな領域の変更。</span><span class="sxs-lookup"><span data-stu-id="f0f08-106">Changes in various areas of interaction with accessibility client applications, including Narrator.</span></span>
- <span data-ttu-id="f0f08-107">アクセス可能な階層の変更 (UI オートメーション ツリー間の移動の改善)。</span><span class="sxs-lookup"><span data-stu-id="f0f08-107">Changes in the Accessible hierarchy (improving navigation through the UI Automation tree).</span></span>
- <span data-ttu-id="f0f08-108">キーボード ナビゲーションの変更点。</span><span class="sxs-lookup"><span data-stu-id="f0f08-108">Changes in keyboard navigation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0f08-109">NET Framework 4.7.1 から .NET Framework 4.8 で行われたアクセシビリティの変更は、.NET Core 3.0 以降に含まれており、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="f0f08-109">Accessibility changes made in .NET Framework 4.7.1 through .NET Framework 4.8 are included in .NET Core 3.0 and above, and are enabled by default.</span></span> <span data-ttu-id="f0f08-110">.NET Framework では、アプリケーションが新しいユーザー補助動作を無効にできる互換性スイッチがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f0f08-110">The .NET Framework supported compatibility switches that allowed applications to opt out of the new accessibility behavior.</span></span> <span data-ttu-id="f0f08-111">一方、.NET Core はこれらの設定をサポートせず、アプリケーションがユーザー補助動作を無効にすることを許可しません。</span><span class="sxs-lookup"><span data-stu-id="f0f08-111">On the other hand, .NET Core doesn't support these settings and doesn't allow applications to opt out of accessibility behavior.</span></span>
  
<span data-ttu-id="f0f08-112">NET Core 3.0 以降、Windows フォーム アプリケーションは、追加の構成を行わずに、すべての新しいアクセシビリティ機能 (.NET Framework 4.7.1 ~ 4.8 で導入) を活用しています。</span><span class="sxs-lookup"><span data-stu-id="f0f08-112">Starting with .NET Core 3.0, Windows Forms applications benefit from all the new accessibility features (introduced in .NET Framework 4.7.1 - 4.8) without additional configuration.</span></span>

## <a name="listbox-accessibility-support"></a><span data-ttu-id="f0f08-113">リスト ボックス のアクセシビリティ のサポート</span><span class="sxs-lookup"><span data-stu-id="f0f08-113">ListBox Accessibility support</span></span>

<span data-ttu-id="f0f08-114">コントロールには、次の変更<xref:System.Windows.Forms.ListBox>が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0f08-114">The following changes apply to the <xref:System.Windows.Forms.ListBox> control:</span></span>

- <span data-ttu-id="f0f08-115">コントロールの UI`ListBox`オートメーション サポートを有効にしました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-115">Enabled UI Automation support for `ListBox` control.</span></span>
- <span data-ttu-id="f0f08-116">項目`ListBox`<xref:System.Windows.Automation.ScrollItemPattern>に`ListBox`を追加し、アクセシビリティ イベントの発生と処理、および項目を介したナレーター のナビゲーションを強化することで、アクセシビリティのサポートが向上しました (CapsLock のナビゲーションが正しくなく、コントロールの外部にナビゲーションが意図せずスローされません)。</span><span class="sxs-lookup"><span data-stu-id="f0f08-116">Improved `ListBox` accessibility support by adding the <xref:System.Windows.Automation.ScrollItemPattern> to `ListBox` items and by enhancing the accessibility event raising and handling and Narrator navigation through the items (caps lock navigation isn't correct and doesn't throw the navigation outside the control unintentionally).</span></span>

## <a name="checkedlistbox-accessibility-support"></a><span data-ttu-id="f0f08-117">チェックリストボックスアクセシビリティサポート</span><span class="sxs-lookup"><span data-stu-id="f0f08-117">CheckedListBox Accessibility support</span></span>

<span data-ttu-id="f0f08-118">コントロールには、次の変更<xref:System.Windows.Forms.CheckedListBox>が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0f08-118">The following changes apply to the <xref:System.Windows.Forms.CheckedListBox> control:</span></span>

- <span data-ttu-id="f0f08-119">エントリの`CheckedListBox`ユーザー補助プロパティによって提供される制限を修正しました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-119">Corrected `CheckedListBox` Bounds provided by accessibility properties for entries.</span></span>
- <span data-ttu-id="f0f08-120">全体的な`ListBox`改善`CheckedListBox`とアクセシビリティ: プロパティ値とイベント モデルを修正しました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-120">Improved overall `ListBox` and `CheckedListBox` accessibility: corrected property values and event model.</span></span>

## <a name="combobox-accessibility-support"></a><span data-ttu-id="f0f08-121">コンボ ボックス のアクセシビリティ サポート</span><span class="sxs-lookup"><span data-stu-id="f0f08-121">ComboBox Accessibility support</span></span>

<span data-ttu-id="f0f08-122">コントロールには、次の変更<xref:System.Windows.Forms.ComboBox>が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0f08-122">The following changes apply to the <xref:System.Windows.Forms.ComboBox> control:</span></span>

- <span data-ttu-id="f0f08-123">項目のアクセシビリティ オブジェクト`ComboBox`を取得するプロセスを更新し、項目からハッシュ コードを取得する代わりにアイテムの ID を<xref:System.Object.GetHashCode%2A>生成できるようにしました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-123">Updated the process of getting `ComboBox` items' accessibility objects to enable generating IDs for items instead of getting hash codes from items, which may be unsafe in case the <xref:System.Object.GetHashCode%2A> function is overridden.</span></span>

## <a name="datagridview-accessibility-support"></a><span data-ttu-id="f0f08-124">アクセシビリティサポート</span><span class="sxs-lookup"><span data-stu-id="f0f08-124">DataGridView Accessibility support</span></span>

<span data-ttu-id="f0f08-125">コントロールには、次の変更<xref:System.Windows.Forms.DataGridView>が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0f08-125">The following changes apply to the <xref:System.Windows.Forms.DataGridView> control:</span></span>

- <span data-ttu-id="f0f08-126">列、`DataGridView.Bounds`行、セル、および対応するヘッダーのアクセシビリティ プロパティによって提供される修正により、外接する四角形の計算のパフォーマンスが向上しました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-126">Corrected `DataGridView.Bounds` provided by accessibility properties for columns, rows, cells and corresponding headers, improved performance of bounding rectangle calculation.</span></span> <span data-ttu-id="f0f08-127">すべてのアクセシビリティの境界は、コントロール全体の境界とビューポートを考慮して、正しく表現されます。</span><span class="sxs-lookup"><span data-stu-id="f0f08-127">All accessibility bounds are represented correctly taking into account the bounds of entire control, along with its viewport.</span></span>
- <span data-ttu-id="f0f08-128">アクセス可能`Value.IsReadOnly`なクライアント アプリケーションの提供を修正したプロパティ値。</span><span class="sxs-lookup"><span data-stu-id="f0f08-128">Corrected `Value.IsReadOnly` property value providing for accessible client applications.</span></span> <span data-ttu-id="f0f08-129">プロパティにセルの状態`IsReadOnly`が正しく表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-129">The property now shows correct `IsReadOnly` status for cells.</span></span>
- <span data-ttu-id="f0f08-130">最初のセル変更<xref:System.Windows.Forms.DataGridView.CellParsing>のイベント発生に関する問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-130">Fixed the issue with <xref:System.Windows.Forms.DataGridView.CellParsing> event raising for the first cell change.</span></span> <span data-ttu-id="f0f08-131">セル値は、最初`DataGridView`のコントロールの相互作用を含め、問題なく変更できます。</span><span class="sxs-lookup"><span data-stu-id="f0f08-131">Cell value can be changed without any issues including the first `DataGridView` control interaction.</span></span>
- <span data-ttu-id="f0f08-132">Windows`DataGridView`ハイ コントラスト テーマを使用する場合の背景色のコントラストが改善されました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-132">Improved `DataGridView` background color contrast when using Windows High Contrast themes.</span></span> <span data-ttu-id="f0f08-133">HC#1、HC#2、およびHCブラックのテーマを使用する場合のデフォルトの背景色を変更`DataGridView`しました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-133">Changed `DataGridView` default back color when using HC#1, HC#2, and HC Black themes.</span></span>

## <a name="propertygrid-accessibility-support"></a><span data-ttu-id="f0f08-134">プロパティ グリッド アクセシビリティ のサポート</span><span class="sxs-lookup"><span data-stu-id="f0f08-134">PropertyGrid Accessibility support</span></span>

<span data-ttu-id="f0f08-135">コントロールには、次の変更<xref:System.Windows.Forms.PropertyGrid>が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0f08-135">The following changes apply to the <xref:System.Windows.Forms.PropertyGrid> control:</span></span>

- <span data-ttu-id="f0f08-136">グリッド`PropertyGrid.Bounds`エントリのアクセシビリティ プロパティによって提供される修正により、外接する四角形の計算のパフォーマンスが向上しました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-136">Corrected `PropertyGrid.Bounds` provided by accessibility properties for grid entries, improved performance of bounding rectangle calculation.</span></span> <span data-ttu-id="f0f08-137">ここでは、コントロール全体の境界とビューポートを考慮して、すべてのアクセシビリティ境界が正しく表現されています。</span><span class="sxs-lookup"><span data-stu-id="f0f08-137">For now all accessibility bounds are represented correctly taking into account the bounds of entire control, along with its viewport.</span></span>
- <span data-ttu-id="f0f08-138">コントロール型名を含めず、コントロールの型名に対する二重アナウンスを回避するために、サブコントロールのアクセシビリティ対応名と説明を修正しました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-138">Corrected accessible names and descriptions of subcontrols to not include control type names and to avoid double announcement for control type names.</span></span>

## <a name="toolstrip-accessibility-support"></a><span data-ttu-id="f0f08-139">ツールストリップ アクセシビリティサポート</span><span class="sxs-lookup"><span data-stu-id="f0f08-139">ToolStrip Accessibility support</span></span>

<span data-ttu-id="f0f08-140">コントロールには、次の変更<xref:System.Windows.Forms.ToolStrip>が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0f08-140">The following changes apply to the <xref:System.Windows.Forms.ToolStrip> control:</span></span>

- <span data-ttu-id="f0f08-141">、 、`ToolStrip``MenuStrip`および`StatusStrip`項目のナビゲーションが改善されました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-141">Improved navigation through `ToolStrip`, `MenuStrip`, and `StatusStrip` items.</span></span> <span data-ttu-id="f0f08-142">修正され`ToolStrip``MenuStrip`、シフトタブナビゲーション,Shiftタブ上矢印が押されたときにメニュー項目をバックループし、下部のメニュー要素に移動します。</span><span class="sxs-lookup"><span data-stu-id="f0f08-142">Corrected `ToolStrip` and `MenuStrip` shift-tab navigation, back-looping the menu items when shift-tab up-arrow is pressed, which navigates to the bottom menu element.</span></span>
- <span data-ttu-id="f0f08-143">アクセシビリティ`MenuStrip`対応ナビゲーションの改善、サブメニューの修正されたメニューアクセス可能なコントロールの種類を 'MenuItem' ではなく 、型 'Menu' のサブメニューにします。</span><span class="sxs-lookup"><span data-stu-id="f0f08-143">Improved `MenuStrip` accessible navigation, corrected menu accessible control types for submenus to make submenus of type 'Menu' instead of 'MenuItem'.</span></span>

## <a name="printpreviewcontrol-and-printpreviewdialog-accessibility-support"></a><span data-ttu-id="f0f08-144">印刷プレビュー コントロールと印刷プレビューダイアログ アクセシビリティ サポート</span><span class="sxs-lookup"><span data-stu-id="f0f08-144">PrintPreviewControl and PrintPreviewDialog Accessibility support</span></span>

<span data-ttu-id="f0f08-145">印刷コントロールには、次の変更が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0f08-145">The following changes apply to the print controls:</span></span>

- <span data-ttu-id="f0f08-146">メニュー項目を介したアクセシビリティ対応ナビゲーション (ナレーター ナビゲーションを含む) が改善されました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-146">Improved accessible navigation (including Narrator navigation) through menu items.</span></span>
- <span data-ttu-id="f0f08-147">ハイ コントラスト テーマのサポートが改善され、コントロール要素のコントラストが向上しました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-147">Improved High Contrast themes support and made the control element more contrasted.</span></span>

## <a name="stringcollectioneditor-accessibility-support"></a><span data-ttu-id="f0f08-148">アクセシビリティサポート</span><span class="sxs-lookup"><span data-stu-id="f0f08-148">StringCollectionEditor Accessibility support</span></span>

<span data-ttu-id="f0f08-149">Windows フォーム デザイナーでは、アクセシビリティ サポートを強化した文字列コレクション エディターが使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-149">Windows Forms designer now uses the string collection editor with improved accessibility support.</span></span>

## <a name="monthcalendar-accessibility-support-available-in-net-core-31"></a><span data-ttu-id="f0f08-150">月間予定表のアクセシビリティサポート (.NET Core 3.1 で利用可能)</span><span class="sxs-lookup"><span data-stu-id="f0f08-150">MonthCalendar Accessibility support (available in .NET Core 3.1)</span></span>

<span data-ttu-id="f0f08-151">コントロールには、次の変更<xref:System.Windows.Forms.MonthCalendar>が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0f08-151">The following changes apply to the <xref:System.Windows.Forms.MonthCalendar> control:</span></span>

- <span data-ttu-id="f0f08-152">コントロールする UI オートメーション`MonthCalendar`サーバー プロバイダーが追加され、UI オートメーション グリッド パターンとテーブル パターン プロバイダーが追加されました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-152">Added UI Automation server providers to `MonthCalendar` control, added UI Automation Grid pattern and Table pattern providers.</span></span>
- <span data-ttu-id="f0f08-153">コントロールにコントロールのアクセシビリティ名を`MonthCalendar`定義するラベル`MonthCalendar`コントロールがある場合を除いて、_テーブル_アクセス可能なコントロール型を_カレンダー_アクセス可能なコントロール型に_変更します。_</span><span class="sxs-lookup"><span data-stu-id="f0f08-153">Changed _table_ accessible control type to _calendar_ accessible control type for `MonthCalendar` except the case when the control has a preceding label control that defines `MonthCalendar` control accessible name, in this specific case accessible control type becomes _table_.</span></span>
- <span data-ttu-id="f0f08-154">選択した制御日の発表`MonthCalendar`が改善されました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-154">Improved announcement of selected date for `MonthCalendar` control.</span></span>
- <span data-ttu-id="f0f08-155">スクリーン`MonthCalendar`リーダーおよびその他のユーザー補助ツールのコントロール のサポートが強化されました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-155">Improved `MonthCalendar` control support for screen readers and other accessibility tools.</span></span> <span data-ttu-id="f0f08-156">現時点では、ユーザーはコントロール要素を移動し、キーボードのみの入力を使用してこれらの要素と対話できます。</span><span class="sxs-lookup"><span data-stu-id="f0f08-156">At this moment, users can navigate the control elements and interact with these elements using keyboard-only input.</span></span> <span data-ttu-id="f0f08-157">ナレーターでは、CAPS + 矢印キーを使用してコントロール要素をナビゲーションし、CAPS + Enter キーを使用して要素の既定のアクションを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f0f08-157">With Narrator, use CAPS + arrow keys to navigation through the control elements and CAPS + Enter to invoke element default action.</span></span>
- <span data-ttu-id="f0f08-158">子要素間の`MonthCalendar`矢印キーナビゲーションを改善し、フォーカスを四角形にします: ナレーターの青フォーカス四角形。</span><span class="sxs-lookup"><span data-stu-id="f0f08-158">Improved arrow key navigation across `MonthCalendar` child elements with a focusing rectangle: blue focus rectangle for Narrator.</span></span>
- <span data-ttu-id="f0f08-159">指定された座標で子のアクセス`MonthCalendar`可能な要素を取得`MonthCalendar`できるように、コントロール要素のヒット テスト アクションのアクセシビリティが向上しました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-159">Improved accessibility for hit test action for `MonthCalendar` control elements to allow getting `MonthCalendar` child accessible element by provided coordinates.</span></span>

## <a name="tooltips-accessibility-available-in-net-core-31"></a><span data-ttu-id="f0f08-160">ツールヒントのアクセシビリティ (.NET Core 3.1 で利用可能)</span><span class="sxs-lookup"><span data-stu-id="f0f08-160">ToolTips accessibility (available in .NET Core 3.1)</span></span>

- <span data-ttu-id="f0f08-161">NVDA やナレーターなどのスクリーン リーダー アプリケーションによってツールヒント テキストを発表する機能を追加しました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-161">Added ability to announce a tooltip text by screen reader applications such as NVDA and Narrator.</span></span> <span data-ttu-id="f0f08-162">スクリーン リーダー アプリケーションは、ツールヒントを表示するように構成された Windows フォーム コントロールのキーボードまたはマウスのツールヒントのテキストを発表できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f0f08-162">Screen reader application can now announce the text of keyboard or mouse tooltip of any Windows Forms control that configured to show tooltips.</span></span>

## <a name="ui-automation-support-for-datagridview-propertygrid-listbox-combobox-toolstrip-and-other-controls"></a><span data-ttu-id="f0f08-163">データ グリッド ビュー、プロパティ グリッド、リスト ボックス、コンボ ボックス、ツール ストリップ、およびその他のコントロールの UI オートメーションのサポート</span><span class="sxs-lookup"><span data-stu-id="f0f08-163">UI automation support for DataGridView, PropertyGrid, ListBox, ComboBox, ToolStrip, and other controls</span></span>

<span data-ttu-id="f0f08-164">UI オートメーションのサポートは、実行時にコントロールに対して有効にされますが、デザイン時には使用されません。</span><span class="sxs-lookup"><span data-stu-id="f0f08-164">UI Automation support is enabled for controls at runtime but isn't used during design time.</span></span> <span data-ttu-id="f0f08-165">UI オートメーションの概要については、「[UI オートメーションの概要](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0f08-165">For an overview of UI automation, see the [UI Automation Overview](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0f08-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0f08-166">See also</span></span>

- <span data-ttu-id="f0f08-167">[アクセシビリティのベストプラクティス](../ui-automation/accessibility-best-practices.md)」</span><span class="sxs-lookup"><span data-stu-id="f0f08-167">[Accessibility Best Practices](../ui-automation/accessibility-best-practices.md).</span></span>
