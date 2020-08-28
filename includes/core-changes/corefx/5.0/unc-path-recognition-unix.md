---
ms.openlocfilehash: 0246f325a6274082b7fb0d5590cec7c80687ae85
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720198"
---
### <a name="uri-recognition-of-unc-paths-on-unix"></a>Unix での UNC パスの URI 認識

Unix オペレーティング システム上で、2 つのスラッシュ (`//`) で始まる文字列が <xref:System.Uri> クラスによって UNC (汎用名前付け規則) パスとして認識されるようになりました。 この変更により、すべてのプラットフォームでそのような文字列の動作の一貫性が確保されるようになります。

#### <a name="change-description"></a>変更の説明

以前のバージョンの .NET では、Unix オペレーティング システム上で、2 つのスラッシュで始まる文字列 (`//contoso`など) が <xref:System.Uri> クラスによって絶対ファイル パスとして認識されます。 ただし、Windows では、そのような文字列は UNC パスとして認識されます。

.NET 5.0 以降、Unix を含むすべてのプラットフォーム上で、2 つのスラッシュで始まる文字列は <xref:System.Uri> クラスによって UNC パスとして認識されます。 さらに、プロパティは UNC セマンティクスに従って動作します。

- <xref:System.Uri.IsUnc?displayProperty=nameWithType> は、`true` を返します。
- パス内の円記号は、スラッシュに置き換えられます。 たとえば、`//first\second` を `//first/second` にします。
- <xref:System.Uri.LocalPath?displayProperty=nameWithType> によって文字のパーセントエンコードは行われません。 たとえば、`//first/\uFFF0` は `//first/%EF%BF%B0` に変換 "*されません*"。

#### <a name="version-introduced"></a>導入されたバージョン

5.0

#### <a name="recommended-action"></a>推奨アクション

開発者側では、何も行う必要はありません。

#### <a name="category"></a>カテゴリ

Core .NET ライブラリ

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->
