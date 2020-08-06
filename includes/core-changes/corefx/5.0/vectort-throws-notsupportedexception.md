---
ms.openlocfilehash: 43ebb37124b8efe077b9f81fe5351bd7db2c72f7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302715"
---
### <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a>Vector\<T> で、サポートされていない型に対して常に NotSupportedException がスローされる

<xref:System.Numerics.Vector%601?displayProperty=nameWithType> では、サポートされていない型パラメーターに対して常に <xref:System.NotSupportedException> がスローされるようになりました。

#### <a name="change-description"></a>変更の説明

以前の <xref:System.Numerics.Vector%601> のメンバーでは、`T` が [サポートされていない型](#unsupported-types)だった場合に、常に <xref:System.NotSupportedException> がスローされるとは限りませんでした。 例外が常にスローされなかったのは、ハードウェアの高速化をサポートしていたコード パスが原因でした。 たとえば、ハードウェアの高速化がないプラットフォーム (ARM32 など) で `Vector<bool> + Vector<bool>` を使用すると、例外をスローするのではなく `default` が返されました。 サポートされていない型について、<xref:System.Numerics.Vector%601> のメンバーが示す動作には、異なるプラットフォームやハードウェア構成にわたる一貫性がありませんでした。

.NET 5.0 以降、<xref:System.Numerics.Vector%601> のメンバーでは、`T` がサポートされていない型である場合に、すべてのハードウェア構成で常に <xref:System.NotSupportedException> がスローされます。

##### <a name="unsupported-types"></a>サポートされていない型

<xref:System.Numerics.Vector%601> の型パラメーターでサポートされている型は次のとおりです。

- `byte`
- `sbyte`
- `short`
- `ushort`
- `int`
- `uint`
- `long`
- `ulong`
- `float`
- `double`

サポートされている型は変更されていませんが、将来変更される可能性があります。

#### <a name="version-introduced"></a>導入されたバージョン

5.0 Preview 8

#### <a name="recommended-action"></a>推奨アクション

<xref:System.Numerics.Vector%601> の型パラメーターにサポートされていない型を使用しないでください。

#### <a name="category"></a>カテゴリ

Core .NET ライブラリ

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Numerics.Vector%601?displayProperty=fullName> およびそのすべてのメンバー

<!--

#### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
