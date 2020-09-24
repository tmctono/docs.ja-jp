---
ms.openlocfilehash: 54bee14f6de409550357194e905b6ee5d8ef8f18
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679001"
---
### <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a>WPF アプリと WinForms アプリで OutputType が WinExe に設定されている

`OutputType` は、Windows Presentation Foundation (WPF) アプリと Windows フォーム アプリでは、自動的に `WinExe` に設定されます。 `OutputType` が `WinExe` に設定されている場合、アプリの実行時にコンソール ウィンドウは開きません。

#### <a name="change-description"></a>変更内容

以前のバージョンの .NET では、プロジェクト ファイルで `OutputType` に指定されている値が使用されます。 次に例を示します。

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

.NET 5.0 以降では、WPF アプリと Windows フォーム アプリで `OutputType` が `WinExe` に自動的に設定されます。 次に例を示します。

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

#### <a name="reason-for-change"></a>変更理由

WPF アプリまたは Windows フォーム アプリの実行時に、ほとんどのユーザーがコンソール ウィンドウを開かないことを前提としています。 さらに、[これらの種類のアプリケーションでは .NET SDK が使用され](../../../../docs/core/compatibility/wpf.md#winforms-and-wpf-apps-use-microsoftnetsdk) (Windows Desktop SDK が使用されるのではなく)、正しい既定値が設定されるようになります。 さらに、iOS と Android を対象としたサポートが追加されると、これらすべてで同じ出力の種類が使用される場合に、複数のプラットフォーム間で複数のターゲットを指定することが容易になります。

#### <a name="version-introduced"></a>導入されたバージョン

.NET 5.0 Preview 8

#### <a name="recommended-action"></a>推奨アクション

ユーザー側の対応は必要ありません。 ただし、以前の動作に戻す場合は、プロジェクト ファイルの `DisableWinExeOutputInference` プロパティを `true` に設定します。

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

#### <a name="category"></a>カテゴリ

- Windows フォーム
- Windows Presentation Foundation (WPF)

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
