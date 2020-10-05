---
ms.openlocfilehash: a9545c66d3873b5114fe66e13c77ddc28e20020e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077606"
---
### <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a>Blazor: ProtectedBrowserStorage 機能を共有フレームワークに移行

ASP.NET Core 5.0 RC2 リリースの一部として、`ProtectedBrowserStorage` 機能は ASP.NET Core 共有フレームワークに移行されました。

#### <a name="version-introduced"></a>導入されたバージョン

5.0 RC2

#### <a name="old-behavior"></a>以前の動作

ASP.NET Core 5.0 Preview 8 では、この機能は [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) パッケージの一部として利用できますが、Blazor WebAssembly でのみ使用可能でした。

ASP.NET Core 5.0 RC1 では、この機能は `Microsoft.AspNetCore.App` 共有フレームワークが参照される [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) パッケージの一部として利用できます。

#### <a name="new-behavior"></a>新しい動作

ASP.NET Core 5.0 RC2 では、機能を参照して使用するために NuGet パッケージ参照が不要になりました。

#### <a name="reason-for-change"></a>変更理由

共有フレームワークへの移行は、お客様が期待するユーザー エクスペリエンスにより適っています。

#### <a name="recommended-action"></a>推奨アクション

ASP.NET Core 5.0 RC1 からアップグレードする場合は、次の手順を実行してください。

1. プロジェクトから `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` パッケージ参照を削除します。
1. `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` を `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;` で置き換え
1. `Startup` クラスから `AddProtectedBrowserStorage` への呼び出しを削除します。

ASP.NET Core 5.0 Preview 8 からアップグレードする場合は、次の手順を実行してください。

1. プロジェクトから `Microsoft.AspNetCore.Components.Web.Extensions` パッケージ参照を削除します。
1. `using Microsoft.AspNetCore.Components.Web.Extensions;` を `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;` で置き換え
1. `Startup` クラスから `AddProtectedBrowserStorage` への呼び出しを削除します。

#### <a name="category"></a>カテゴリ

ASP.NET Core

#### <a name="affected-apis"></a>影響を受ける API

なし

<!--

#### Affected APIs

Not detectable via API analysis

-->
