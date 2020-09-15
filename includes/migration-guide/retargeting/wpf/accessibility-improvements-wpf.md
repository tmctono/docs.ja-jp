---
ms.openlocfilehash: 895d09e4ec39bd4a92ed1f4910da80474334d99b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496831"
---
### <a name="accessibility-improvements-in-wpf"></a><span data-ttu-id="7ae90-101">WPF でのアクセシビリティの向上</span><span class="sxs-lookup"><span data-stu-id="7ae90-101">Accessibility improvements in WPF</span></span>

#### <a name="details"></a><span data-ttu-id="7ae90-102">説明</span><span class="sxs-lookup"><span data-stu-id="7ae90-102">Details</span></span>

<span data-ttu-id="7ae90-103">**ハイ コントラストの改善**</span><span class="sxs-lookup"><span data-stu-id="7ae90-103">**High Contrast improvements**</span></span>

- <span data-ttu-id="7ae90-104"><xref:System.Windows.Controls.Expander> コントロールにフォーカスを合わせると、表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7ae90-104">The focus for the <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="7ae90-105">.NET Framework の以前のバージョンでは、そうではありませんでした。</span><span class="sxs-lookup"><span data-stu-id="7ae90-105">In previous versions of .NET Framework, it was not.</span></span>
- <span data-ttu-id="7ae90-106"><xref:System.Windows.Controls.CheckBox> および <xref:System.Windows.Controls.RadioButton> コントロールを選択したとき、コントロールのテキストが .NET Framework の以前のバージョンより見やすくなりました。</span><span class="sxs-lookup"><span data-stu-id="7ae90-106">The text in <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls when they are selected is now easier to see than in previous .NET Framework versions.</span></span>
- <span data-ttu-id="7ae90-107">無効になっている <xref:System.Windows.Controls.ComboBox> の境界が、無効なテキストと同じ色になりました。</span><span class="sxs-lookup"><span data-stu-id="7ae90-107">The border of a disabled <xref:System.Windows.Controls.ComboBox> is now the same color as the disabled text.</span></span> <span data-ttu-id="7ae90-108">.NET Framework の以前のバージョンでは、そうではありませんでした。</span><span class="sxs-lookup"><span data-stu-id="7ae90-108">In previous versions of .NET Framework, it was not.</span></span>
- <span data-ttu-id="7ae90-109">無効になっているボタンにフォーカスを合わせたとき、正しいテーマ色が使われるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7ae90-109">Disabled and focused buttons now use the correct theme color.</span></span> <span data-ttu-id="7ae90-110">.NET Framework の以前のバージョンでは、そうではありませんでした。</span><span class="sxs-lookup"><span data-stu-id="7ae90-110">In previous versions of .NET Framework, they did not.</span></span>
- <span data-ttu-id="7ae90-111">ドロップダウン ボタンが、<xref:System.Windows.Controls.ComboBox> コントロールのスタイルが <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey?displayProperty=nameWithType> に設定されている場合、表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7ae90-111">The dropdown button is now visible when a <xref:System.Windows.Controls.ComboBox> control's style is set to <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7ae90-112">.NET Framework の以前のバージョンでは、そうではありませんでした。</span><span class="sxs-lookup"><span data-stu-id="7ae90-112">In previous versions of .NET Framework, it was not.</span></span>
- <span data-ttu-id="7ae90-113"><xref:System.Windows.Controls.DataGrid> コントロールの並べ替えインジケーターの矢印で、テーマの色が使われるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7ae90-113">The sort indicator arrow in a <xref:System.Windows.Controls.DataGrid> control now uses theme colors.</span></span> <span data-ttu-id="7ae90-114">.NET Framework の以前のバージョンでは、そうではありませんでした。</span><span class="sxs-lookup"><span data-stu-id="7ae90-114">In previous versions of .NET Framework, it did not.</span></span>
- <span data-ttu-id="7ae90-115">ハイパーリンクの既定のスタイルが、マウスでポイントされると正しいテーマの色に変わるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7ae90-115">The default hyperlink style now changes to the correct theme color on mouse over.</span></span> <span data-ttu-id="7ae90-116">.NET Framework の以前のバージョンでは、そうではありませんでした。</span><span class="sxs-lookup"><span data-stu-id="7ae90-116">In previous versions of .NET Framework, it did not.</span></span>
- <span data-ttu-id="7ae90-117">ラジオ ボタンに対するキーボード フォーカスが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7ae90-117">The Keyboard focus on radio buttons is now visible.</span></span> <span data-ttu-id="7ae90-118">.NET Framework の以前のバージョンでは、そうではありませんでした。</span><span class="sxs-lookup"><span data-stu-id="7ae90-118">In previous versions of .NET Framework, it was not.</span></span>
- <span data-ttu-id="7ae90-119"><xref:System.Windows.Controls.DataGrid> コントロールのチェック ボックス列で、キーボード フォーカスのフィードバックに予期される色が使われるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7ae90-119">The <xref:System.Windows.Controls.DataGrid> control's checkbox column now uses the expected colors for keyboard focus feedback.</span></span> <span data-ttu-id="7ae90-120">.NET Framework の以前のバージョンでは、そうではありませんでした。</span><span class="sxs-lookup"><span data-stu-id="7ae90-120">In previous versions of .NET Framework, it did not.</span></span>
- <span data-ttu-id="7ae90-121"><xref:System.Windows.Controls.ComboBox> および <xref:System.Windows.Controls.ListBox> コントロールで、キーボード フォーカスのビジュアルが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7ae90-121">the Keyboard focus visuals are now visible on <xref:System.Windows.Controls.ComboBox> and <xref:System.Windows.Controls.ListBox> controls.</span></span> <span data-ttu-id="7ae90-122">.NET Framework の以前のバージョンでは、そうではありませんでした。</span><span class="sxs-lookup"><span data-stu-id="7ae90-122">In previous versions of .NET Framework, it was not.</span></span>

<span data-ttu-id="7ae90-123">**スクリーン リーダーの操作性の向上**</span><span class="sxs-lookup"><span data-stu-id="7ae90-123">**Screen reader interaction improvements**</span></span>

- <span data-ttu-id="7ae90-124"><xref:System.Windows.Controls.Expander> コントロールが、スクリーン リーダーによってグループ (展開/折りたたみ) として正しく読み上げられるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7ae90-124"><xref:System.Windows.Controls.Expander> controls are now correctly announced as groups (expand/collapse) by screen readers.</span></span>
- <span data-ttu-id="7ae90-125"><xref:System.Windows.Controls.DataGridCell> コントロールが、スクリーン リーダーによってデータ グリッド セル (ローカライズ済み) として正しく読み上げられるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7ae90-125"><xref:System.Windows.Controls.DataGridCell> controls are now correctly announced as data grid cell (localized) by screen readers.</span></span>
- <span data-ttu-id="7ae90-126">スクリーン リーダーが、編集可能な <xref:System.Windows.Controls.ComboBox> の名前を読み上げるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7ae90-126">Screen readers will now announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>
- <span data-ttu-id="7ae90-127">スクリーン リーダーが、<xref:System.Windows.Controls.PasswordBox> コントロールを "ビューに項目がありません" と読み上げなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7ae90-127"><xref:System.Windows.Controls.PasswordBox> controls are no longer announced as "no item in view" by screen readers.</span></span>

<span data-ttu-id="7ae90-128">**LiveRegion のサポート**</span><span class="sxs-lookup"><span data-stu-id="7ae90-128">**LiveRegion support**</span></span>

<span data-ttu-id="7ae90-129">ナレーターなどのスクリーン リーダーでは、通常は現在フォーカスがあるユーザー インターフェイス要素を説明して、ユーザーがアプリケーションの UI を理解するのを助けます。</span><span class="sxs-lookup"><span data-stu-id="7ae90-129">Screen readers, such as Narrator, help people understand the user interface (UI) of an application, usually by describing the UI element that currently has focus.</span></span> <span data-ttu-id="7ae90-130">しかし、画面内のどこかの UI 要素が変わり、フォーカスがなくなった場合、ユーザーに通知されず、重要な情報を逃すことがあります。</span><span class="sxs-lookup"><span data-stu-id="7ae90-130">However, if a UI element changes somewhere in the screen and it does not have the focus, the user may not be informed and miss important information.</span></span> <span data-ttu-id="7ae90-131">LiveRegions は、この問題を解決するためのものです。</span><span class="sxs-lookup"><span data-stu-id="7ae90-131">LiveRegions are meant to solve this problem.</span></span> <span data-ttu-id="7ae90-132">開発者はこれを利用して、UI 要素が大幅に変更されたことをスクリーン リーダーやその他の [UI オートメーション](~/docs/framework/ui-automation/ui-automation-overview.md) クライアントに伝えることができます。</span><span class="sxs-lookup"><span data-stu-id="7ae90-132">A developer can use them to inform the screen reader or any other [UI Automation](~/docs/framework/ui-automation/ui-automation-overview.md) client that an important change has been made to a UI element.</span></span> <span data-ttu-id="7ae90-133">指示後、スクリーン リーダーでは、その変更をユーザーに通知する方法とタイミングが決定されます。</span><span class="sxs-lookup"><span data-stu-id="7ae90-133">The screen reader can then decide how and when to inform the user of this change.</span></span> <span data-ttu-id="7ae90-134">LiveSetting プロパティを使うと、UI に行われた変更をユーザーに通知するのがどの程度重要かをスクリーン リーダーに知らせることもできます。</span><span class="sxs-lookup"><span data-stu-id="7ae90-134">The LiveSetting property also lets the screen reader know how important it is to inform the user of the change made to the UI.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7ae90-135">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="7ae90-135">Suggestion</span></span>

<span data-ttu-id="7ae90-136">**これらの変更を選択する方法と選択しない方法**</span><span class="sxs-lookup"><span data-stu-id="7ae90-136">**How to opt in or out of these changes**</span></span>

<span data-ttu-id="7ae90-137">アプリケーションでこれらの変更を利用するには、.NET Framework 4.7.1 以降で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ae90-137">In order for the application to benefit from these changes, it must run on .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="7ae90-138">アプリケーションは、次のいずれかの方法でこれらの変更を利用できます。</span><span class="sxs-lookup"><span data-stu-id="7ae90-138">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="7ae90-139">.NET Framework 4.7.1 を対象にします。</span><span class="sxs-lookup"><span data-stu-id="7ae90-139">Target .NET Framework 4.7.1.</span></span> <span data-ttu-id="7ae90-140">この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7ae90-140">This is the recommended approach.</span></span> <span data-ttu-id="7ae90-141">.NET Framework 4.7.1 以降を対象とする WPF アプリケーションでは、これらのアクセシビリティの変更が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="7ae90-141">These accessibility changes are enabled by default on WPF applications that target .NET Framework 4.7.1 or later.</span></span>
- <span data-ttu-id="7ae90-142">下の例のように、アプリ構成ファイルの `<runtime>` セクションで次の [AppContext スイッチ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)を追加し、それを `false` に設定することで、以前のアクセシビリティ動作を無効にします。</span><span class="sxs-lookup"><span data-stu-id="7ae90-142">It opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) in the `<runtime>` section of the app config file and setting it to `false`, as the following example shows.</span></span>

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
    </startup>
    <runtime>
      <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false'  -->
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
    </runtime>
  </configuration>
  ```

<span data-ttu-id="7ae90-143">.NET Framework 4.7.1 以降を対象とするアプリケーションで以前のアクセシビリティ動作を残す場合、この AppContext スイッチを明示的に `true` に設定することで以前のアクセシビリティ機能を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7ae90-143">Applications that target .NET Framework 4.7.1 or later and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to `true`.</span></span>
<span data-ttu-id="7ae90-144">UI オートメーションの概要については、「[UI オートメーションの概要](~/docs/framework/ui-automation/ui-automation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ae90-144">For an overview of UI automation, see [UI Automation Overview](~/docs/framework/ui-automation/ui-automation-overview.md).</span></span>

| <span data-ttu-id="7ae90-145">名前</span><span class="sxs-lookup"><span data-stu-id="7ae90-145">Name</span></span>    | <span data-ttu-id="7ae90-146">[値]</span><span class="sxs-lookup"><span data-stu-id="7ae90-146">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7ae90-147">スコープ</span><span class="sxs-lookup"><span data-stu-id="7ae90-147">Scope</span></span>   | <span data-ttu-id="7ae90-148">Major</span><span class="sxs-lookup"><span data-stu-id="7ae90-148">Major</span></span>       |
| <span data-ttu-id="7ae90-149">バージョン</span><span class="sxs-lookup"><span data-stu-id="7ae90-149">Version</span></span> | <span data-ttu-id="7ae90-150">4.7.1</span><span class="sxs-lookup"><span data-stu-id="7ae90-150">4.7.1</span></span>       |
| <span data-ttu-id="7ae90-151">種類</span><span class="sxs-lookup"><span data-stu-id="7ae90-151">Type</span></span>    | <span data-ttu-id="7ae90-152">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="7ae90-152">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="7ae90-153">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="7ae90-153">Affected APIs</span></span>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting(System.Windows.DependencyObject,System.Windows.Automation.AutomationLiveSetting)?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting(System.Windows.DependencyObject)?displayProperty=nameWithType>
- <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore?displayProperty=nameWithType>
