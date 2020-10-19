---
ms.openlocfilehash: 24b88b3ba1b6cfe9fb9fb1f6398a6daeb57596a9
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756112"
---
### <a name="order-of-tags-in-activitytags-is-reversed"></a>Activity.Tags 内のタグの順序が逆になっている

<xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> では、追加された順に項目がリストに格納されるようになりました。つまり、最初に追加された項目がリストの先頭になります。 この変更は、[OpenTelemetry Attributes 仕様](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes)と一致させるために行われました。

#### <a name="change-description"></a>変更内容

以前のバージョンの .NET では、<xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> により追加されたのと逆の順序で項目が格納されます。 つまり、最初に追加された項目がリストの末尾になります。 .NET 5.0 以降では、項目の順序は逆になり、最初に追加された項目が常にリストの先頭になります。

#### <a name="version-introduced"></a>導入されたバージョン

5.0

#### <a name="recommended-action"></a>推奨アクション

ご使用のアプリが <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> リストの順序に依存していて、.NET 5.0 以降にアップグレードする場合は、コードのこの部分を変更する必要があります。

#### <a name="category"></a>カテゴリ

Core .NET ライブラリ

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
