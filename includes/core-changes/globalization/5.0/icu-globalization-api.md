---
ms.openlocfilehash: 18718ebc934e0175c20411055b8c0a90ef6b175f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539490"
---
### <a name="globalization-apis-use-icu-libraries-on-windows"></a>グローバリゼーション API では Windows 上の ICU ライブラリが使用される

.NET 5.0 以降のバージョンでは、Windows 10 May 2019 Update 以降で実行されると、グローバリゼーション機能用に [International Components for Unicode (ICU)](http://site.icu-project.org/home) ライブラリが使用されます。

#### <a name="change-description"></a>変更の説明

それより前の .NET ライブラリでは、グローバリゼーション機能用に [National Language Support (NLS)](/windows/win32/intl/national-language-support) API が使用されていました。 たとえば、日付と時刻の形式のパターンなどのカルチャ データの取得、文字列の比較、適切なカルチャでの文字列の大文字と小文字の使い分けの実行には、NLS 関数が使用されていました。

.NET 5.0 以降では、アプリが Windows 10 May 2019 Update 以降で実行されている場合、[ICU](http://site.icu-project.org/home) グローバリゼーション API が .NET ライブラリで使用されます。 Windows 10 May 2019 Update 以降のバージョンには、ICU ネイティブ ライブラリが付属しています。 .NET ランタイムで ICU を読み込むことができない場合は、代わりに NLS が使用されます。

この変更は、次の 2 つの理由で導入されました。

- アプリのグローバリゼーション動作は、Linux、macOS、Windows など、プラットフォームが異なっても同じです。
- アプリでは、カスタム ICU ライブラリを使用して、グローバリゼーションの動作を制御できます。

#### <a name="version-introduced"></a>導入されたバージョン

.NET 5.0 Preview 4

#### <a name="recommended-action"></a>推奨アクション

開発者側では、何も行う必要はありません。 ただし、NLS グローバリゼーション API を引き続き使いたい場合は、[ランタイム スイッチ](../../../../docs/core/run-time-config/globalization.md#nls)を設定して、その動作に戻すことができます。 使用可能なスイッチの詳細については、「[.NET グローバリゼーションと ICU](../../../../docs/standard/globalization-localization/globalization-icu.md)」の記事をご覧ください。

#### <a name="category"></a>カテゴリ

グローバリゼーション

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- <xref:System.Globalization?displayProperty=fullName> 名前空間のほとんどの型

<!--

#### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`

-->
