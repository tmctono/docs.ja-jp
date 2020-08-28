---
ms.openlocfilehash: 115cd6be935ae12a1293f948a0f899c6c3ff0d78
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608479"
---
### <a name="winhttphandler-removed-from-net-runtime"></a>.NET ランタイムからの WinHttpHandler の削除

`WinHttpHandler` クラスが *System.Net.Http.dll* アセンブリから削除されました。 現在、これは帯域外 (OOB) [NuGet パッケージ](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)としてのみ使用できます。

#### <a name="version-introduced"></a>導入されたバージョン

5.0

#### <a name="change-description"></a>変更の説明

以前のバージョンの .NET では、<xref:System.Net.Http.WinHttpHandler> クラスは .NET のコア ライブラリの一部として使用できました。 .NET 5.0 以降、<xref:System.Net.Http.WinHttpHandler> クラスは、別にインストールする [NuGet パッケージ](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)のみとして用意されています。

#### <a name="recommended-action"></a>推奨アクション

[System.Net.Http.WinHttpHandler NuGet パッケージ](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)をインストールします。 または、WinHTTP 固有の機能を必要としない場合は、代わりに <xref:System.Net.Http.SocketsHttpHandler> を使用します。

#### <a name="category"></a>カテゴリ

ネットワーキング

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

-->
