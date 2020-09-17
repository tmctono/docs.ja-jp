---
ms.openlocfilehash: 975e331ad3e7bd7e0e8f49b62795c6acc7031ca9
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656343"
---
### <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a>WinForms と WPF アプリで Microsoft.NET.Sdk が使用される

Windows フォームと Windows Presentation Framework (WPF) アプリで、.NET Core WinForms および WPF SDK (`Microsoft.NET.Sdk.WindowsDesktop`) ではなく、.NET SDK (`Microsoft.NET.Sdk`) が使用されるようになりました。

#### <a name="change-description"></a>変更内容

以前のバージョンの .NET Core では、WinForms および WPF アプリで別の[プロジェクト SDK](../../../../docs/core/project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`) が使用されていました。 .NET 5.0 以降、WinForms および WPF SDK の両方で .NET SDK (`Microsoft.NET.Sdk`) が統合されました。 また、.NET 5 では、`netcoreapp` と `netstandard` が新しい[ターゲット フレーム ワークモニカー (TFM)](../../../../docs/standard/frameworks.md) に置き換えられています。 次の例では、WPF プロジェクト ファイルを .NET 5.0 以降に変更する場合に、行う必要がある変更を示しています。

以前の .NET Core バージョンの場合:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

.NET 5.0 以降のバージョンの場合:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

#### <a name="version-introduced"></a>導入されたバージョン

.NET 5.0 Preview 8

#### <a name="recommended-action"></a>推奨アクション

お使いの WPF または Windows フォーム プロジェクト ファイル:

- `Sdk` 属性を `Microsoft.NET.Sdk` に更新します。
- `TargetFramework` プロパティを `net5.0-windows` に更新します。

#### <a name="category"></a>カテゴリ

- Windows フォーム
- Windows Presentation Foundation (WPF)

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
