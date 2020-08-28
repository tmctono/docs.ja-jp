---
ms.openlocfilehash: faf9459ab9002e6149560e2a3452265fa246bf6b
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720200"
---
### <a name="uri-paths-with-non-ascii-characters-parse-correctly-on-unix"></a>Unix 上で ASCII 以外の文字を含む URI パスが正しく解析される

<xref:System.Uri?displayProperty=fullName> クラス内のバグが修正され、Unix プラットフォーム上で ASCII 以外の文字を含む絶対 URI パスが正しく解析されるようになりました。

#### <a name="change-description"></a>変更の説明

以前のバージョンの .NET では、Unix プラットフォーム上で ASCII 以外の文字を含む絶対 URI パスが正しく解析されず、パスのセグメントに重複が生じます。 (絶対パスとは、"/" で始まるものです)。 .NET 5.0 ではこの解析の問題が修正されました。 以前のバージョンの .NET から .NET 5.0 以降に移行すると、<xref:System.Uri.AbsoluteUri?displayProperty=nameWithType>、<xref:System.Uri.ToString?displayProperty=nameWithType>、およびその他の <xref:System.Uri> メンバーによって生成され出力される値は異なるものとなります。

Unix 上で実行する場合は、次のコードの出力を検討してください。

```csharp
var myUri = new Uri("/üri");

Console.WriteLine($"AbsoluteUri: {myUri.AbsoluteUri}");
Console.WriteLine($"ToString: {myUri.ToString()}");
```

以前のバージョンの .NET での出力:

```text
AbsoluteUri: /%C3%BCri/%C3%BCri
ToString: /üri/üri
```

.NET 5.0 以降のバージョンでの出力:

```text
AbsoluteUri: /%C3%BCri
ToString: /üri
```

#### <a name="version-introduced"></a>導入されたバージョン

5.0

#### <a name="recommended-action"></a>推奨アクション

重複したパス セグメントの発生が予期される、および明らかであるコードがある場合は、そのコードを削除できます。

#### <a name="category"></a>カテゴリ

Core .NET ライブラリ

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->
