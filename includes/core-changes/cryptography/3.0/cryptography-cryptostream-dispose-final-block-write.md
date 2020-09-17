---
ms.openlocfilehash: 7766a59131fffe2b436c15a5ff58e67001be7941
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065105"
---
### <a name="cryptostreamdispose-transforms-final-block-only-when-writing"></a>CryptoStream.Dispose は書き込み時にのみ最後のブロックを変換する

`CryptoStream` 操作を完了するために使用される <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType> メソッドは、読み取り時に最後のブロックの変換を試行しなくなりました。

#### <a name="change-description"></a>変更内容

以前のバージョンの .NET では、ユーザーが <xref:System.Security.Cryptography.CryptoStreamMode.Read> モードで <xref:System.Security.Cryptography.CryptoStream> を使用するときに不完全な読み取りを実行した場合、<xref:System.Security.Cryptography.CryptoStream.Dispose%2A> メソッドから例外がスローされる可能性がありました (たとえば、パディングで AES を使用する場合)。 例外がスローされた理由は、最後のブロックの変換が試みられたがデータが不完全だったことにありました。

.NET Core 3.0 以降のバージョンでは、<xref:System.Security.Cryptography.CryptoStream.Dispose%2A> が読み取り時に最後のブロックの変換を試行しなくなりました。これにより、不完全な読み取りが許容されます。

#### <a name="reason-for-change"></a>変更理由

この変更により、ネットワーク操作がキャンセルされたときに、例外をキャッチする必要なく、暗号化ストリームからの不完全な読み取りが可能になります。

#### <a name="version-introduced"></a>導入されたバージョン

3.0

#### <a name="recommended-action"></a>推奨アクション

ほとんどのアプリは、この変更の影響を受けることはありません。

不完全な読み取りが発生した場合にアプリケーションが例外をキャッチしても、その `catch` ブロックを削除できます。
ご利用のアプリがハッシュ シナリオで最後のブロックの変換を使用した場合、ストリーム全体が破棄される前にそれを確実に読み取るようにする必要がある可能性があります。

#### <a name="category"></a>カテゴリ

暗号

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.CryptoStream.Dispose`

-->
