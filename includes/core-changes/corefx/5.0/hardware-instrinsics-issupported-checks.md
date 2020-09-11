---
ms.openlocfilehash: bba9659b92e5aabc276c585929c99898316036c5
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359137"
---
### <a name="hardware-intrinsic-issupported-checks-may-differ-for-nested-types"></a>ハードウェアに組み込みの IsSupported チェックは、入れ子にされた型によって異なる場合があります

`<Isa>.X64.IsSupported` (`<Isa>` は <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> 名前空間のクラスを指す) をチェックすると、場合によっては、前のバージョンの .NET とは異なる結果が生成されるようになりました。

> [!TIP]
> *ISA* は業界標準アーキテクチャの略です。

#### <a name="version-introduced"></a>導入されたバージョン

5.0 Preview 8

#### <a name="change-description"></a>変更内容

.NET の前のバージョンでは、ハードウェアに組み込まれている型 <xref:System.Runtime.Intrinsics.X86> (たとえば、<xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType>) で、入れ子にされた `X64` クラスが公開されませんでした。 このような型の場合、`<Isa>.X64.IsSupported` を呼び出すと、`<Isa>` の親クラスの入れ子 `X64` クラスで `IsSupported` プロパティに解決されました。 これは、`<Isa>.IsSupported` で `false` が返されるときでも、このプロパティで `true` が返される可能性を意味しました。

.NET 5.0 以降のバージョンでは、すべての <xref:System.Runtime.Intrinsics.X86> 型で、サポートを適宜報告する入れ子 `X64` クラスが公開されます。 これにより、一般階層が正しく維持され、`<Isa>.X64.IsSupported` が `true` の場合、`<Isa>.IsSupported` も `true` になると想定できます。

#### <a name="reason-for-change"></a>変更理由

`<Isa>.X64.IsSupported` が `true` の場合、`<Isa>.IsSupported` も暗黙的に `true` になることが意図されていました。 しかしながら、C# におけるメンバー解決のしくみに起因し、入れ子 `X64` クラスが与えられていないクラスでは意図どおりになるとは限らず、ユーザー コードでバグが見つかる状況が発生しました。

#### <a name="recommended-action"></a>推奨アクション

必要に応じて、該当する ISA がないか確認するよう、`IsSupported` をチェックするコードを調整します。

#### <a name="category"></a>カテゴリ

Core .NET ライブラリ

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported`

-->
