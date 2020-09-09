---
ms.openlocfilehash: 895d09e4ec39bd4a92ed1f4910da80474334d99b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496831"
---
### <a name="accessibility-improvements-in-wpf"></a>WPF でのアクセシビリティの向上

#### <a name="details"></a>説明

**ハイ コントラストの改善**

- <xref:System.Windows.Controls.Expander> コントロールにフォーカスを合わせると、表示されるようになりました。 .NET Framework の以前のバージョンでは、そうではありませんでした。
- <xref:System.Windows.Controls.CheckBox> および <xref:System.Windows.Controls.RadioButton> コントロールを選択したとき、コントロールのテキストが .NET Framework の以前のバージョンより見やすくなりました。
- 無効になっている <xref:System.Windows.Controls.ComboBox> の境界が、無効なテキストと同じ色になりました。 .NET Framework の以前のバージョンでは、そうではありませんでした。
- 無効になっているボタンにフォーカスを合わせたとき、正しいテーマ色が使われるようになりました。 .NET Framework の以前のバージョンでは、そうではありませんでした。
- ドロップダウン ボタンが、<xref:System.Windows.Controls.ComboBox> コントロールのスタイルが <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey?displayProperty=nameWithType> に設定されている場合、表示されるようになりました。 .NET Framework の以前のバージョンでは、そうではありませんでした。
- <xref:System.Windows.Controls.DataGrid> コントロールの並べ替えインジケーターの矢印で、テーマの色が使われるようになりました。 .NET Framework の以前のバージョンでは、そうではありませんでした。
- ハイパーリンクの既定のスタイルが、マウスでポイントされると正しいテーマの色に変わるようになりました。 .NET Framework の以前のバージョンでは、そうではありませんでした。
- ラジオ ボタンに対するキーボード フォーカスが表示されるようになりました。 .NET Framework の以前のバージョンでは、そうではありませんでした。
- <xref:System.Windows.Controls.DataGrid> コントロールのチェック ボックス列で、キーボード フォーカスのフィードバックに予期される色が使われるようになりました。 .NET Framework の以前のバージョンでは、そうではありませんでした。
- <xref:System.Windows.Controls.ComboBox> および <xref:System.Windows.Controls.ListBox> コントロールで、キーボード フォーカスのビジュアルが表示されるようになりました。 .NET Framework の以前のバージョンでは、そうではありませんでした。

**スクリーン リーダーの操作性の向上**

- <xref:System.Windows.Controls.Expander> コントロールが、スクリーン リーダーによってグループ (展開/折りたたみ) として正しく読み上げられるようになりました。
- <xref:System.Windows.Controls.DataGridCell> コントロールが、スクリーン リーダーによってデータ グリッド セル (ローカライズ済み) として正しく読み上げられるようになりました。
- スクリーン リーダーが、編集可能な <xref:System.Windows.Controls.ComboBox> の名前を読み上げるようになりました。
- スクリーン リーダーが、<xref:System.Windows.Controls.PasswordBox> コントロールを "ビューに項目がありません" と読み上げなくなりました。

**LiveRegion のサポート**

ナレーターなどのスクリーン リーダーでは、通常は現在フォーカスがあるユーザー インターフェイス要素を説明して、ユーザーがアプリケーションの UI を理解するのを助けます。 しかし、画面内のどこかの UI 要素が変わり、フォーカスがなくなった場合、ユーザーに通知されず、重要な情報を逃すことがあります。 LiveRegions は、この問題を解決するためのものです。 開発者はこれを利用して、UI 要素が大幅に変更されたことをスクリーン リーダーやその他の [UI オートメーション](~/docs/framework/ui-automation/ui-automation-overview.md) クライアントに伝えることができます。 指示後、スクリーン リーダーでは、その変更をユーザーに通知する方法とタイミングが決定されます。 LiveSetting プロパティを使うと、UI に行われた変更をユーザーに通知するのがどの程度重要かをスクリーン リーダーに知らせることもできます。

#### <a name="suggestion"></a>提案される解決策

**これらの変更を選択する方法と選択しない方法**

アプリケーションでこれらの変更を利用するには、.NET Framework 4.7.1 以降で実行する必要があります。 アプリケーションは、次のいずれかの方法でこれらの変更を利用できます。

- .NET Framework 4.7.1 を対象にします。 この方法をお勧めします。 .NET Framework 4.7.1 以降を対象とする WPF アプリケーションでは、これらのアクセシビリティの変更が既定で有効になっています。
- 下の例のように、アプリ構成ファイルの `<runtime>` セクションで次の [AppContext スイッチ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)を追加し、それを `false` に設定することで、以前のアクセシビリティ動作を無効にします。

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

.NET Framework 4.7.1 以降を対象とするアプリケーションで以前のアクセシビリティ動作を残す場合、この AppContext スイッチを明示的に `true` に設定することで以前のアクセシビリティ機能を選択できます。
UI オートメーションの概要については、「[UI オートメーションの概要](~/docs/framework/ui-automation/ui-automation-overview.md)」を参照してください。

| 名前    | [値]       |
|:--------|:------------|
| スコープ   | Major       |
| バージョン | 4.7.1       |
| 種類    | 再ターゲット中 |

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting(System.Windows.DependencyObject,System.Windows.Automation.AutomationLiveSetting)?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting(System.Windows.DependencyObject)?displayProperty=nameWithType>
- <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore?displayProperty=nameWithType>
