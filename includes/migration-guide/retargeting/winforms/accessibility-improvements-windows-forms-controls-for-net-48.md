---
ms.openlocfilehash: 882c4c0455b7df538079ffe1b7d1d7ca8af1904a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606787"
---
### <a name="accessibility-improvements-in-windows-forms-controls-for-net-48"></a><span data-ttu-id="a916f-101">.NET 4.8 の Windows フォーム コントロールでのアクセシビリティの改善</span><span class="sxs-lookup"><span data-stu-id="a916f-101">Accessibility improvements in Windows Forms controls for .NET 4.8</span></span>

#### <a name="details"></a><span data-ttu-id="a916f-102">説明</span><span class="sxs-lookup"><span data-stu-id="a916f-102">Details</span></span>

<span data-ttu-id="a916f-103">Windows フォーム フレームワークでは引き続き、アクセシビリティ テクノロジでの動作が改善されており、Windows フォームのお客様のサポートが向上しています。</span><span class="sxs-lookup"><span data-stu-id="a916f-103">The Windows Forms Framework is continuing to improve how it works with accessibility technologies to better support Windows Forms customers.</span></span> <span data-ttu-id="a916f-104">次のような点が変更されます。</span><span class="sxs-lookup"><span data-stu-id="a916f-104">These include the following changes:</span></span>

- <span data-ttu-id="a916f-105">ハイ コントラスト モード中の表示が向上する変更。</span><span class="sxs-lookup"><span data-stu-id="a916f-105">Changes to improve display during High Contrast mode.</span></span>
- <span data-ttu-id="a916f-106">ナレーターとのやり取りの変更。</span><span class="sxs-lookup"><span data-stu-id="a916f-106">Changes to interaction with Narrator.</span></span>
- <span data-ttu-id="a916f-107">アクセス可能な階層の変更 (UI オートメーション ツリー間の移動の改善)。</span><span class="sxs-lookup"><span data-stu-id="a916f-107">Changes in the Accessible hierarchy (improving navigation through the UI Automation tree).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a916f-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="a916f-108">Suggestion</span></span>

<span data-ttu-id="a916f-109">**これらの変更を選択する方法と選択しない方法** アプリケーションでこれらの変更を利用するには、.NET Framework 4.8 で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a916f-109">**How to opt in or out of these changes** In order for the application to benefit from these changes, it must run on the .NET Framework 4.8.</span></span> <span data-ttu-id="a916f-110">アプリケーションでは、次のいずれかの方法でこれらの変更を選択できます。</span><span class="sxs-lookup"><span data-stu-id="a916f-110">The application can opt in into these changes in either of the following ways:</span></span>

- <span data-ttu-id="a916f-111">.NET Framework 4.8 をターゲットとして再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="a916f-111">It is recompiled to target the .NET Framework 4.8.</span></span> <span data-ttu-id="a916f-112">.NET Framework 4.8 をターゲットとする Windows フォーム アプリケーションでは、これらのアクセシビリティの変更が既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="a916f-112">These accessibility changes are enabled by default on Windows Forms applications that target the .NET Framework 4.8.</span></span>
- <span data-ttu-id="a916f-113">.NET Framework 4.7.2 以前のバージョンをターゲットとし、下の例のように、アプリ構成ファイルの `<runtime>` セクションに次の [AppContext スイッチ](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)を追加し、それを `false` に設定することで、以前のアクセシビリティ動作を選択しないようにします。</span><span class="sxs-lookup"><span data-stu-id="a916f-113">It targets the .NET Framework 4.7.2 or earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the `<runtime>` section of the app config file and setting it to `false`, as the following example shows.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
  </runtime>
</configuration>
```

<span data-ttu-id="a916f-114">.NET Framework 4.8 で追加されたアクセシビリティ機能を選択するには、.NET Framework 4.7.1 と 4.7.2 のアクセシビリティ機能も選択する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a916f-114">Note that to opt in to the accessibility features added in .NET Framework 4.8, you must also opt in to accessibility features of .NET Framework 4.7.1 and 4.7.2 as well.</span></span> <span data-ttu-id="a916f-115">.NET Framework 4.8 をターゲットとするアプリケーションで以前のアクセシビリティ動作を残す場合、この AppContext スイッチを明示的に `true` に設定することで、以前のアクセシビリティ機能の使用を選択できます。キーボード ツールヒントの呼び出しサポートを有効にするには、`Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false` 行を AppContextSwitchOverrides 値に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a916f-115">Applications that target the .NET Framework 4.8 and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to `true`.Enabling the keyboard ToolTip invocation support requires adding the `Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false` line to the AppContextSwitchOverrides value:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false" />
```

<span data-ttu-id="a916f-116">この機能を有効にするには、.NET Framework 4.7.1 から 4.8 の前述のアクセシビリティ機能を選択する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a916f-116">Note that enabling this feature requires opting in to the aforementioned accessibility features of .NET Framework 4.7.1 - 4.8.</span></span> <span data-ttu-id="a916f-117">また、どのアクセシビリティ機能も選択されていないが、ツールヒントに機能が選択されていることが示される場合は、これらの機能への初回アクセス時に、ランタイムの <xref:System.NotSupportedException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="a916f-117">Also, if any of the accessibility features are not opted in but the tooltip display feature is opted in, a runtime <xref:System.NotSupportedException> will be thrown on the first access to these features.</span></span> <span data-ttu-id="a916f-118">例外メッセージには、キーボードのツールヒントではレベル 3 のアクセシビリティ機能の強化を有効にする必要があることが示されます。</span><span class="sxs-lookup"><span data-stu-id="a916f-118">The exception message indicates that keyboard ToolTips require accessibility improvements of level 3 to be enabled.</span></span>

<span data-ttu-id="a916f-119">**ハイ コントラスト テーマでの OS で定義された色の使用**</span><span class="sxs-lookup"><span data-stu-id="a916f-119">**Use of OS-defined colors in High Contrast themes**</span></span>

- <span data-ttu-id="a916f-120">ハイ コントラストのテーマが改善されました。</span><span class="sxs-lookup"><span data-stu-id="a916f-120">Improved high-contrast themes.</span></span>

<span data-ttu-id="a916f-121">**ナレーター サポートが改善されました**</span><span class="sxs-lookup"><span data-stu-id="a916f-121">**Improved Narrator support**</span></span>

- <span data-ttu-id="a916f-122">ナレーターで、<xref:System.Windows.Forms.DataGridViewCell> のアクセス可能な名前を読み上げるときに、<xref:System.Windows.Forms.DataGridViewColumn> の並べ替えの方向を読み上げるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a916f-122">Narrator now announces the sort direction of the <xref:System.Windows.Forms.DataGridViewColumn> when announcing an accessible name of a <xref:System.Windows.Forms.DataGridViewCell>.</span></span>

<span data-ttu-id="a916f-123">**CheckedListBox アクセシビリティ サポートの改善**</span><span class="sxs-lookup"><span data-stu-id="a916f-123">**Improved CheckedListBox Accessibility support**</span></span>

- <span data-ttu-id="a916f-124"><xref:System.Windows.Forms.CheckedListBox> コントロールのナレーター サポートが改善されました。</span><span class="sxs-lookup"><span data-stu-id="a916f-124">Improved Narrator support for the <xref:System.Windows.Forms.CheckedListBox> control.</span></span> <span data-ttu-id="a916f-125">キーボードを使用して <xref:System.Windows.Forms.CheckedListBox> コントロールに移動するときに、ナレーターでは <xref:System.Windows.Forms.CheckedListBox> 項目にフォーカスし、それを読み上げます。</span><span class="sxs-lookup"><span data-stu-id="a916f-125">When navigating to the <xref:System.Windows.Forms.CheckedListBox> control using the keyboard, Narrator focuses the <xref:System.Windows.Forms.CheckedListBox> item and announces it.</span></span>
- <span data-ttu-id="a916f-126">空の CheckedListBox コントロールでは、コントロールがフォーカスされたときに、仮想の最初の項目に対してフォーカスを示す四角形が描画されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a916f-126">An empty CheckedListBox control now has a focus rectangle drawn for a virtual first item when the control becomes focused.</span></span>

<span data-ttu-id="a916f-127">**ComboBox アクセシビリティ サポートの改善**</span><span class="sxs-lookup"><span data-stu-id="a916f-127">**Improved ComboBox Accessibility support**</span></span>

- <span data-ttu-id="a916f-128">UI オートメーション通知やその他の UI オートメーション機能を使用できる、<xref:System.Windows.Forms.ComboBox> コントロールの UI オートメーション サポートが有効になりました。</span><span class="sxs-lookup"><span data-stu-id="a916f-128">Enabled UI Automation support for the <xref:System.Windows.Forms.ComboBox> control, with the ability to use UI Automation notifications and other UI Automation features.</span></span>
<span data-ttu-id="a916f-129">**DataGridView のアクセシビリティ サポートの向上**</span><span class="sxs-lookup"><span data-stu-id="a916f-129">**Improved DataGridView Accessibility support**</span></span>

- <span data-ttu-id="a916f-130">UI オートメーション通知やその他の UI オートメーション機能を使用できる、<xref:System.Windows.Forms.DataGridView> コントロールの UI オートメーション サポートが有効になりました。</span><span class="sxs-lookup"><span data-stu-id="a916f-130">Enabled UI Automation support for <xref:System.Windows.Forms.DataGridView> control with ability to use UI Automation notifications and other UI Automation features.</span></span>
- <span data-ttu-id="a916f-131"><xref:System.Windows.Forms.DataGridViewComboBoxEditingControl> または <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl> に対応する UI オートメーション要素が、対応する編集セルの子になりました。</span><span class="sxs-lookup"><span data-stu-id="a916f-131">The UI Automation element which corresponds to the <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl> or <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl> is now a child of corresponding editing cell.</span></span>

<span data-ttu-id="a916f-132">**LinkLabel アクセシビリティ サポートの改善**</span><span class="sxs-lookup"><span data-stu-id="a916f-132">**Improved LinkLabel Accessibility support**</span></span>

- <span data-ttu-id="a916f-133"><xref:System.Windows.Forms.LinkLabel> コントロールのアクセシビリティが改善されました。対応する <xref:System.Windows.Forms.LinkLabel> コントロールが無効になっている場合、ナレーターではリンクの無効状態が読み上げられます。</span><span class="sxs-lookup"><span data-stu-id="a916f-133">Improved <xref:System.Windows.Forms.LinkLabel> control accessibility: Narrator announces the disabled state for the link if the corresponding <xref:System.Windows.Forms.LinkLabel> control is disabled.</span></span>

<span data-ttu-id="a916f-134">**ProgressBar アクセシビリティ サポートの改善**</span><span class="sxs-lookup"><span data-stu-id="a916f-134">**Improved ProgressBar Accessibility support**</span></span>

- <span data-ttu-id="a916f-135">UI オートメーション通知やその他の UI オートメーション機能を使用できる、<xref:System.Windows.Forms.ProgressBar> コントロールの UI オートメーション サポートが有効になりました。</span><span class="sxs-lookup"><span data-stu-id="a916f-135">Enabled UI Automation support for the <xref:System.Windows.Forms.ProgressBar> control with the ability to use UI Automation notifications and other UI Automation features.</span></span> <span data-ttu-id="a916f-136">開発者は、進行状況を示すためにナレーターで読み上げることができる、UI オートメーション通知を使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a916f-136">Developers are now able to use UI Automation notifications which Narrator can announce to indicate progress.</span></span>
<span data-ttu-id="a916f-137">UI オートメーション通知イベントを含む、UI オートメーション イベントの概要については、「[UI オートメーション イベントの概要](/windows/desktop/WinAuto/uiauto-eventsoverview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a916f-137">For an overview of UI automation events overview, including UI automation notification events, see the [UI Automation Events Overview](/windows/desktop/WinAuto/uiauto-eventsoverview).</span></span>

<span data-ttu-id="a916f-138">**PropertyGrid アクセシビリティ サポートの改善**</span><span class="sxs-lookup"><span data-stu-id="a916f-138">**Improved PropertyGrid Accessibility support**</span></span>

- <span data-ttu-id="a916f-139">UI オートメーション通知やその他の UI オートメーション機能を使用できる、<xref:System.Windows.Forms.PropertyGrid> コントロールの UI オートメーション サポートが有効になりました。</span><span class="sxs-lookup"><span data-stu-id="a916f-139">Enabled UI Automation support for the <xref:System.Windows.Forms.PropertyGrid> control, with the ability to use UI Automation notifications and other UI Automation features.</span></span>
- <span data-ttu-id="a916f-140">現在編集されているプロパティに対応する UI オートメーション要素が、対応するプロパティ項目の UI オートメーション要素の子になりました。</span><span class="sxs-lookup"><span data-stu-id="a916f-140">The UI Automation element which corresponds to the currently edited property is now a child of the corresponding property item UI Automation element.</span></span>
- <span data-ttu-id="a916f-141">親の <xref:System.Windows.Forms.PropertyGrid> コントロールがカテゴリ ビューに設定されている場合、UI オートメーション プロパティ項目の要素は、対応するカテゴリ要素の子になります。</span><span class="sxs-lookup"><span data-stu-id="a916f-141">The UI Automation property item element is now a child of the corresponding category element if the parent <xref:System.Windows.Forms.PropertyGrid> control is set to category view.</span></span>

<span data-ttu-id="a916f-142">**ToolStrip サポートの改善**</span><span class="sxs-lookup"><span data-stu-id="a916f-142">**Improved ToolStrip support**</span></span>

- <span data-ttu-id="a916f-143">UI オートメーション通知やその他の UI オートメーション機能を使用できる、<xref:System.Windows.Forms.ToolStrip> コントロールの UI オートメーション サポートが有効になりました。</span><span class="sxs-lookup"><span data-stu-id="a916f-143">Enabled UI Automation support for the <xref:System.Windows.Forms.ToolStrip> control, with the ability to use UI Automation notifications and other UI Automation features.</span></span>
- <span data-ttu-id="a916f-144"><xref:System.Windows.Forms.ToolStrip> 項目間の移動が改善されました。</span><span class="sxs-lookup"><span data-stu-id="a916f-144">Improved navigation through <xref:System.Windows.Forms.ToolStrip> items.</span></span>
- <span data-ttu-id="a916f-145">項目モードでは、ナレーターのフォーカスは非表示にならず、非表示項目には移動しません。</span><span class="sxs-lookup"><span data-stu-id="a916f-145">In items mode, Narrator focus does not disappear and does not go to hidden items.</span></span>

<span data-ttu-id="a916f-146">**視覚的な手掛かりの向上**</span><span class="sxs-lookup"><span data-stu-id="a916f-146">**Improved Visual cues**</span></span>

- <span data-ttu-id="a916f-147">空の <xref:System.Windows.Forms.CheckedListBox> コントロールでは、フォーカスを受け取ったときに、フォーカス インジケーターが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a916f-147">An empty <xref:System.Windows.Forms.CheckedListBox> control now displays a focus indicator when it receives focus.</span></span>
<span data-ttu-id="a916f-148">メモ:UI オートメーション サポートは、実行時のコントロールでは有効になりますが、設計時には使用されません。</span><span class="sxs-lookup"><span data-stu-id="a916f-148">Note: UI automation support is enabled for controls in runtime but is not used in design time.</span></span> <span data-ttu-id="a916f-149">UI オートメーションの概要については、「[UI オートメーションの概要](../../../../docs/framework/ui-automation/ui-automation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a916f-149">For an overview of UI automation, see the [UI Automation Overview](../../../../docs/framework/ui-automation/ui-automation-overview.md).</span></span>

<span data-ttu-id="a916f-150">**キーボードでのコントロールのツールヒントの呼び出し**</span><span class="sxs-lookup"><span data-stu-id="a916f-150">**Invoking controls' ToolTips with a keyboard**</span></span>

- <span data-ttu-id="a916f-151">キーボードを使用してコントロールにフォーカスすることで、コントロール ツールヒントを呼び出せるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a916f-151">Control tooltip can now be invoked by focusing the control with keyboard.</span></span> <span data-ttu-id="a916f-152">この機能は、アプリケーションに対して明示的に有効にする必要があります (「 **&quot;これらの変更を選択する方法と選択しない方法&quot;** 」セクションを参照)</span><span class="sxs-lookup"><span data-stu-id="a916f-152">This feature needs to be enabled explicitly for the application (see section **&quot;How to opt in or out of these changes&quot;**)</span></span>

| <span data-ttu-id="a916f-153">名前</span><span class="sxs-lookup"><span data-stu-id="a916f-153">Name</span></span>    | <span data-ttu-id="a916f-154">[値]</span><span class="sxs-lookup"><span data-stu-id="a916f-154">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a916f-155">スコープ</span><span class="sxs-lookup"><span data-stu-id="a916f-155">Scope</span></span>   | <span data-ttu-id="a916f-156">Major</span><span class="sxs-lookup"><span data-stu-id="a916f-156">Major</span></span>       |
| <span data-ttu-id="a916f-157">バージョン</span><span class="sxs-lookup"><span data-stu-id="a916f-157">Version</span></span> | <span data-ttu-id="a916f-158">4.8</span><span class="sxs-lookup"><span data-stu-id="a916f-158">4.8</span></span>         |
| <span data-ttu-id="a916f-159">種類</span><span class="sxs-lookup"><span data-stu-id="a916f-159">Type</span></span>    | <span data-ttu-id="a916f-160">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="a916f-160">Retargeting</span></span> |
