---
ms.openlocfilehash: cc3c2c2be179842f87be8892d057a6c4138086cb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614877"
---
### <a name="accessibility-improvements-in-windows-forms-controls-for-net-472"></a><span data-ttu-id="97c66-101">.NET 4.7.2 の Windows フォーム コントロールでのアクセシビリティの向上</span><span class="sxs-lookup"><span data-stu-id="97c66-101">Accessibility improvements in Windows Forms controls for .NET 4.7.2</span></span>

#### <a name="details"></a><span data-ttu-id="97c66-102">説明</span><span class="sxs-lookup"><span data-stu-id="97c66-102">Details</span></span>

<span data-ttu-id="97c66-103">Windows フォーム フレームワークは、アクセシビリティ テクノロジでの動作の向上により、Windows フォームのお客様のサポートが向上しています。</span><span class="sxs-lookup"><span data-stu-id="97c66-103">Windows Forms Framework is improving how it works with accessibility technologies to better support Windows Forms customers.</span></span> <span data-ttu-id="97c66-104">次のような点が変更されます。</span><span class="sxs-lookup"><span data-stu-id="97c66-104">These include the following changes:</span></span>

- <span data-ttu-id="97c66-105">ハイ コントラスト モード中の表示が向上する変更。</span><span class="sxs-lookup"><span data-stu-id="97c66-105">Changes to improve display during High Contrast mode.</span></span>
- <span data-ttu-id="97c66-106">DataGridView コントロールと MenuStrip コントロールでのキーボード ナビゲーションが向上する変更。</span><span class="sxs-lookup"><span data-stu-id="97c66-106">Changes to improve the keyboard navigation in the DataGridView and MenuStrip controls.</span></span>
- <span data-ttu-id="97c66-107">ナレーターとのやり取りの変更。</span><span class="sxs-lookup"><span data-stu-id="97c66-107">Changes to interaction with Narrator.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="97c66-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="97c66-108">Suggestion</span></span>

<span data-ttu-id="97c66-109">**これらの変更を選択する方法と選択しない方法** アプリケーションでこれらの変更を利用するには、.NET Framework 4.7.2 以降で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97c66-109">**How to opt in or out of these changes** In order for the application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="97c66-110">アプリケーションは、次のいずれかの方法でこれらの変更を利用できます。</span><span class="sxs-lookup"><span data-stu-id="97c66-110">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="97c66-111">.NET Framework 4.7.2 を対象にして再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="97c66-111">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="97c66-112">.NET Framework 4.7.2 以降を対象とする Windows フォーム アプリケーションでは、これらのアクセシビリティの変更が既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="97c66-112">These accessibility changes are enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="97c66-113">.NET Framework 4.7.1 以前を対象にして、下の例のように、app.config ファイルの `<runtime>` セクションに次の [AppContext スイッチ](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element)を追加し、それを `false` に設定することで、以前のアクセシビリティ動作を無効にします。</span><span class="sxs-lookup"><span data-stu-id="97c66-113">It targets the .NET Framework 4.7.1 or earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the `<runtime>` section of the app config file and setting it to `false`, as the following example shows.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
  </runtime>
</configuration>
```

<span data-ttu-id="97c66-114">.NET Framework 4.7.2 で追加されたアクセシビリティ機能にオプトインするには、.NET Framework 4.7.1 のアクセシビリティ機能にもオプトインする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="97c66-114">Note that to opt in to the accessibility features added in .NET Framework 4.7.2, you must also opt in to accessibility features of .NET Framework 4.7.1 as well.</span></span> <span data-ttu-id="97c66-115">.NET Framework 4.7.2 以降を対象とするアプリケーションで以前のアクセシビリティ動作を残す場合、この AppContext スイッチを明示的に `true` に設定することで以前のアクセシビリティ機能を選択できます。</span><span class="sxs-lookup"><span data-stu-id="97c66-115">Applications that target the .NET Framework 4.7.2 or later and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to `true`.</span></span>

<span data-ttu-id="97c66-116">**ハイ コントラスト テーマでの OS で定義された色の使用**</span><span class="sxs-lookup"><span data-stu-id="97c66-116">**Use of OS-defined colors in High Contrast themes**</span></span>

- <span data-ttu-id="97c66-117"><xref:System.Windows.Forms.ToolStripDropDownButton> のドロップダウン矢印が、OS で定義されているハイ コントラスト テーマの色を使うようになりました。</span><span class="sxs-lookup"><span data-stu-id="97c66-117">The drop down arrow of the <xref:System.Windows.Forms.ToolStripDropDownButton> now uses OS-defined colors in High Contrast theme.</span></span>
- <span data-ttu-id="97c66-118"><xref:System.Windows.Forms.ButtonBase.FlatStyle> が <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> または <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType> に設定された <xref:System.Windows.Forms.Button>、<xref:System.Windows.Forms.RadioButton>、<xref:System.Windows.Forms.CheckBox> コントロールは、ハイ コントラスト テーマが選択されているときは OS で定義された色を使用するようになります。</span><span class="sxs-lookup"><span data-stu-id="97c66-118"><xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with <xref:System.Windows.Forms.ButtonBase.FlatStyle> set to <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> or <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType> now use OS-defined colors in High Contrast theme when selected.</span></span> <span data-ttu-id="97c66-119">以前は、テキストと背景の色はコントラストが同じで、見分けるのが困難でした。</span><span class="sxs-lookup"><span data-stu-id="97c66-119">Previously, text and background colors were not contrasting and were hard to read.</span></span>
- <span data-ttu-id="97c66-120"><xref:System.Windows.Forms.Control.Enabled> プロパティが `false` に設定された <xref:System.Windows.Forms.GroupBox> に含まれるコントロールは、OS で定義されているハイ コントラスト テーマの色を使うようになります。</span><span class="sxs-lookup"><span data-stu-id="97c66-120">Controls contained within a <xref:System.Windows.Forms.GroupBox> that has its <xref:System.Windows.Forms.Control.Enabled> property set to `false` will now use OS-defined colors in High Contrast theme.</span></span>
- <span data-ttu-id="97c66-121"><xref:System.Windows.Forms.ToolStripButton>、<xref:System.Windows.Forms.ToolStripComboBox>、<xref:System.Windows.Forms.ToolStripDropDownButton> コントロールは、ハイ コントラスト モードでの明度コントラストの比率が高くなりました。</span><span class="sxs-lookup"><span data-stu-id="97c66-121">The <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox>, and <xref:System.Windows.Forms.ToolStripDropDownButton> controls have an increased luminosity contrast ratio in High Contrast Mode.</span></span>
- <span data-ttu-id="97c66-122"><xref:System.Windows.Forms.DataGridViewLinkCell> は <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor?displayProperty=nameWithType> プロパティに対し OS で定義されているハイ コントラスト テーマの色を既定で使うようになります。</span><span class="sxs-lookup"><span data-stu-id="97c66-122"><xref:System.Windows.Forms.DataGridViewLinkCell> will by default use OS-defined colors in High Contrast mode for the <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor?displayProperty=nameWithType> property.</span></span>
<span data-ttu-id="97c66-123">注:Windows 10 では、一部のハイ コントラストのシステム カラーの値が変更されています。</span><span class="sxs-lookup"><span data-stu-id="97c66-123">NOTE: Windows 10 has changed values for some high contrast system colors.</span></span> <span data-ttu-id="97c66-124">Windows フォームのフレームワークは、Win32 フレームワークに基づいています。</span><span class="sxs-lookup"><span data-stu-id="97c66-124">Windows Forms Framework is based on the Win32 framework.</span></span> <span data-ttu-id="97c66-125">最も快適に利用するためには、最新版の Windows で実行し、テスト アプリケーションに app.manifest ファイルを追加して最新の OS 変更を選択し、次のコードのコメントを解除します。</span><span class="sxs-lookup"><span data-stu-id="97c66-125">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-commenting the following code:</span></span>

```xml
<!-- Windows 10 -->
<supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
```

<span data-ttu-id="97c66-126">**ナレーター サポートが改善されました**</span><span class="sxs-lookup"><span data-stu-id="97c66-126">**Improved Narrator support**</span></span>

- <span data-ttu-id="97c66-127">ナレーターは、<xref:System.Windows.Forms.ToolStripMenuItem> のテキストを読み上げるときに、<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> プロパティの値を読み上げるようになります。</span><span class="sxs-lookup"><span data-stu-id="97c66-127">Narrator now announces the value of the <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> property when announcing the text of a <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>
- <span data-ttu-id="97c66-128"><xref:System.Windows.Forms.ToolStripMenuItem> の <xref:System.Windows.Forms.Control.Enabled> プロパティが `false` に設定されている場合、ナレーターはそれを示すようになります。</span><span class="sxs-lookup"><span data-stu-id="97c66-128">Narrator now indicates when a <xref:System.Windows.Forms.ToolStripMenuItem> has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>
- <span data-ttu-id="97c66-129">ナレーターは、<xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> プロパティが `true` に設定されているとき、チェック ボックスの状態に関するフィードバックを提供するようになります。</span><span class="sxs-lookup"><span data-stu-id="97c66-129">Narrator now gives feedback on the state of a check box when the <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> property is set to `true`.</span></span>
- <span data-ttu-id="97c66-130">ナレーター スキャン モードのフォーカス順序が、ClickOnce ダウンロード ダイアログ ウィンドウでのコントロールの視覚的な順序と一致するようになります。</span><span class="sxs-lookup"><span data-stu-id="97c66-130">Narrator Scan Mode focus order is now consistent with the visual order of the controls on the ClickOnce download dialog window.</span></span>

<span data-ttu-id="97c66-131">**DataGridView のアクセシビリティ サポートの向上**</span><span class="sxs-lookup"><span data-stu-id="97c66-131">**Improved DataGridView Accessibility support**</span></span>

- <span data-ttu-id="97c66-132"><xref:System.Windows.Forms.DataGridView> の行をキーボードを使って並べ替えられるようになります。</span><span class="sxs-lookup"><span data-stu-id="97c66-132">Rows in a <xref:System.Windows.Forms.DataGridView> can now be sorted using the keyboard.</span></span> <span data-ttu-id="97c66-133">ユーザーは、F3 キーを使って現在の列で並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="97c66-133">Now a user can use the F3 key in order to sort by the current column.</span></span>
- <span data-ttu-id="97c66-134"><xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> が <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> に設定されていると、ユーザーが現在の行のセルを Tab で移動するとき、列ヘッダーの色が変わって現在の列を示します。</span><span class="sxs-lookup"><span data-stu-id="97c66-134">When the <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> is set to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, the column header will change color to indicate the current column as the user tabs through the cells in the current row.</span></span>
- <span data-ttu-id="97c66-135"><xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Parent?displayProperty=nameWithType> プロパティは、正しい親コントロールを返します。</span><span class="sxs-lookup"><span data-stu-id="97c66-135">The <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Parent?displayProperty=nameWithType> property now returns the correct parent control.</span></span>

<span data-ttu-id="97c66-136">**視覚的な手掛かりの向上**</span><span class="sxs-lookup"><span data-stu-id="97c66-136">**Improved Visual cues**</span></span>

- <span data-ttu-id="97c66-137"><xref:System.Windows.Forms.ButtonBase.Text> プロパティが空の <xref:System.Windows.Forms.RadioButton> および <xref:System.Windows.Forms.CheckBox> コントロールは、フォーカスを受け取るとフォーカス インジケーターを表示するようになりました。</span><span class="sxs-lookup"><span data-stu-id="97c66-137">The <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with an empty <xref:System.Windows.Forms.ButtonBase.Text> property will now display a focus indicator when they receive focus.</span></span>

<span data-ttu-id="97c66-138">**強化されたプロパティ グリッドのサポート**</span><span class="sxs-lookup"><span data-stu-id="97c66-138">**Improved Property Grid Support**</span></span>

- <span data-ttu-id="97c66-139"><xref:System.Windows.Forms.PropertyGrid> コントロールの子要素は、PropertyGrid 要素が有効になっている場合にのみ、<xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> プロパティに対して `true` を返すようになりました。</span><span class="sxs-lookup"><span data-stu-id="97c66-139">The <xref:System.Windows.Forms.PropertyGrid> control child elements now return a `true` for the  <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> property only when a PropertyGrid element is enabled.</span></span>
- <span data-ttu-id="97c66-140"><xref:System.Windows.Forms.PropertyGrid> コントロールの子要素は、PropertyGrid 要素をユーザーが変更できる場合にのみ、<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> プロパティに対して `false` を返すようになりました。</span><span class="sxs-lookup"><span data-stu-id="97c66-140">The <xref:System.Windows.Forms.PropertyGrid> control child elements now return a `false` for the <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> property only when a PropertyGrid element can be changed by the user.</span></span>
<span data-ttu-id="97c66-141">UI オートメーションの概要については、「[UI オートメーションの概要](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97c66-141">For an overview of UI automation, see the [UI Automation Overview](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview).</span></span></p><span data-ttu-id="97c66-142">**キーボード ナビゲーションの向上**</span><span class="sxs-lookup"><span data-stu-id="97c66-142">**Improved keyboard navigation**</span></span>

- <span data-ttu-id="97c66-143"><xref:System.Windows.Forms.ToolStripButton> は、<xref:System.Windows.Forms.ToolStripPanel.TabStop> プロパティが `true` に設定された <xref:System.Windows.Forms.ToolStripPanel> 内に含まれているときに、フォーカスできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="97c66-143"><xref:System.Windows.Forms.ToolStripButton> now allows focus when contained within a <xref:System.Windows.Forms.ToolStripPanel> that has the <xref:System.Windows.Forms.ToolStripPanel.TabStop> property set to `true`.</span></span>

| <span data-ttu-id="97c66-144">名前</span><span class="sxs-lookup"><span data-stu-id="97c66-144">Name</span></span>    | <span data-ttu-id="97c66-145">[値]</span><span class="sxs-lookup"><span data-stu-id="97c66-145">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="97c66-146">スコープ</span><span class="sxs-lookup"><span data-stu-id="97c66-146">Scope</span></span>   | <span data-ttu-id="97c66-147">Major</span><span class="sxs-lookup"><span data-stu-id="97c66-147">Major</span></span>       |
| <span data-ttu-id="97c66-148">バージョン</span><span class="sxs-lookup"><span data-stu-id="97c66-148">Version</span></span> | <span data-ttu-id="97c66-149">4.7.2</span><span class="sxs-lookup"><span data-stu-id="97c66-149">4.7.2</span></span>       |
| <span data-ttu-id="97c66-150">種類</span><span class="sxs-lookup"><span data-stu-id="97c66-150">Type</span></span>    | <span data-ttu-id="97c66-151">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="97c66-151">Retargeting</span></span> |
