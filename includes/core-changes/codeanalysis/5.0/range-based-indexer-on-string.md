---
ms.openlocfilehash: 87f9cc03f334233ef286abd11e6f5ff82d7988c2
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811349"
---
### <a name="ca1831-use-asspan-or-asmemory-instead-of-range-based-indexer"></a>CA1831 範囲ベースのインデクサーの代わりに AsSpan か AsMemory を使用する

.NET コード アナライザー ルール [CA1831](/visualstudio/code-quality/ca1831) は .NET 5.0 以降では既定で有効になっています。 <xref:System.Range> ベースのインデクサーが文字列で使用されているが、コピーが意図されていないコードでは、ビルド警告が生成されます。

#### <a name="change-description"></a>変更内容

.NET 5.0 以降、.NET SDK には [.NET ソース コード アナライザー](../../../../docs/fundamentals/productivity/code-analysis.md)が含まれています。 これらのルールのいくつかは、既定では [CA1831](/visualstudio/code-quality/ca1831) を含めて有効になっています。 このルールに違反し、警告をエラーとして扱うように構成されているコードがプロジェクトに含まれている場合、この変更によってビルドが破損する可能性があります。

ルール CA1831 は、文字列で <xref:System.Range> ベースのインデクサーが使用されているが、コピーが意図されていないインスタンスを検索します。 <xref:System.Range> ベースのインデクサーを文字列で直接使用して暗黙的なキャストを生成する場合は、文字列の要求された部分の不要なコピーが作成されます。 次に例を示します。

```csharp
ReadOnlySpan<char> slice = str[1..3];
```

CA1831 では、代わりに文字列の "*スパン*" で <xref:System.Range> ベースのインデクサーを使用することが提案されます。 次に例を示します。

```csharp
ReadOnlySpan<char> slice = str.AsSpan()[1..3];
```

#### <a name="version-introduced"></a>導入されたバージョン

5.0 Preview 8

#### <a name="recommended-action"></a>推奨アクション

- コードを修正し、不要な割り当てを回避するには、<xref:System.Range> ベースのインデクサーを使用する前に <xref:System.MemoryExtensions.AsSpan(System.String)> または <xref:System.MemoryExtensions.AsMemory(System.String)> を呼び出します。 次に例を示します。

  ```csharp
  ReadOnlySpan<char> slice = str.AsSpan()[1..3];
  ```

- コードを変更しない場合は、その重要度を `suggestion` または `none` に設定して、ルールを無効にすることができます。 詳細については、「[コード分析ルールを構成する](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md)」を参照してください。

- コード分析を完全に無効にするには、プロジェクト ファイルで `EnableNETAnalyzers` を `false` に設定します。 詳細については、「[EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)」を参照してください。

#### <a name="category"></a>カテゴリ

コード分析

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Range?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Range`

-->
