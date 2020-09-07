---
ms.openlocfilehash: 018c99d60dc8926cae2682dc9c035e25fba711e5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497093"
---
### <a name="incorrect-code-generation-when-passing-and-comparing-uint16-values"></a>UInt16 値を渡して比較する場合にコード生成が正しく行われません

#### <a name="details"></a>説明

.NET Framework 4.7 で変更が導入されたため、.NET Framework 4.7 で実行されているアプリケーションの JIT コンパイラによって生成されたコードが 2 つの <code>T:System.UInt16</code> 値を正しく比較しない場合があります。 詳細については、GitHub.com の「[Issue #11508: Silent bad codegen when passing and comparing ushort args](https://github.com/dotnet/coreclr/issues/11508)」 (問題 #11508: ushort の引数を渡して比較する場合のサイレントかつ不適切な codegen ) を参照してください。

#### <a name="suggestion"></a>提案される解決策

.NET Framework 4.7 で 16 ビットの符号なし値を比較したときに問題が検出された場合は、.NET Framework 4.7.1 にアップグレードしてください。

| 名前    | 値       |
|:--------|:------------|
| スコープ   |エッジ|
|バージョン|4.7|
|種類|ランタイム|

#### <a name="affected-apis"></a>影響を受ける API

API 分析では検出できません。

<!--

#### Affected APIs

Not detectable via API analysis.

-->
