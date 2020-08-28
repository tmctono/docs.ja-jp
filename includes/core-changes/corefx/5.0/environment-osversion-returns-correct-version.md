---
ms.openlocfilehash: ccd056f23d26e6cce4cc691542784792bffe9fc6
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558182"
---
### <a name="environmentosversion-returns-the-correct-operating-system-version"></a>Environment.OSVersion で正しいオペレーティング システム バージョンが返される

<xref:System.Environment.OSVersion?displayProperty=nameWithType> で、アプリケーションの互換性のために選択される OS などではなく、オペレーティング システム (OS) の実際のバージョンが返されます。

#### <a name="change-description"></a>変更の説明

以前のバージョンの .NET では、アプリケーションが Windows 互換モードで実行されている場合、<xref:System.Environment.OSVersion?displayProperty=nameWithType> によって、正しくない可能性がある OS バージョンが返されます。 詳細については、[GetVersionExA 関数の解説](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks)に関する記述を参照してください。

.NET 5.0 以降では、<xref:System.Environment.OSVersion?displayProperty=nameWithType> によってオペレーティング システムの実際のバージョンが返されます。

#### <a name="reason-for-change"></a>変更理由

このプロパティのユーザーは、オペレーティング システムの実際のバージョンが返されることを期待しています。 ほとんどの .NET アプリにより、アプリケーション マニフェストでサポートされているバージョンが指定されないため、dotnet ホストから既定でサポートされているバージョンが取得されます。 その結果、実行されているアプリでは互換性 shim はほとんど意味がなくなります。 Windows で新しいバージョンがリリースされており、古い dotnet ホストがまだ使用されている場合は、これらのアプリの OS バージョンが正しくない可能性があります。 実際のバージョンを返すことが、この API に対する開発者の期待により沿うことになります。

#### <a name="version-introduced"></a>導入されたバージョン

5.0

#### <a name="recommended-action"></a>推奨アクション

<xref:System.Environment.OSVersion?displayProperty=nameWithType> を使用するコードを確認してテストし、確実に期待どおりに動作するようにします。

#### <a name="category"></a>カテゴリ

Core .NET ライブラリ

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Environment.OSVersion`

-->
