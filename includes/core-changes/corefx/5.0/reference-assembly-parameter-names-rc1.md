---
ms.openlocfilehash: 760c9ce2427bc1f5e9276e66ecb6d2cf2ed83c16
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738822"
---
### <a name="parameter-names-changed-in-rc1"></a>RC1 でパラメーター名が変更されている

一部の参照アセンブリ パラメーター名が、実装アセンブリ内のパラメーター名と一致するように変更されました。

#### <a name="change-description"></a>変更の説明

以前の .NET 5.0 Preview および RC バージョンでは、一部の[参照アセンブリ](../../../../docs/standard/assembly/reference-assemblies.md)のパラメーター名が、実装アセンブリ内にある対応するパラメーターのものとは異なっています。 これにより、名前付き引数とリフレクションの使用中に問題が発生する可能性があります。

.NET 5.0 RC2 では、参照アセンブリ内でこのような不一致のパラメーター名が更新され、実装アセンブリ内の対応するパラメーター名と完全に一致するようになりました。

次の表に API と変更されたパラメーター名を示します。

| API | 古いパラメーター名 | 新しいパラメーター名 |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

#### <a name="reason-for-change"></a>変更理由

一貫性を保つため、および名前付き引数とリフレクションを使用するときにエラーが発生するのを回避するために、パラメーター名が変更されました。

#### <a name="version-introduced"></a>導入されたバージョン

5.0 RC2

#### <a name="recommended-action"></a>推奨アクション

パラメーター名の変更が原因で、コンパイラ エラーが発生する場合は、適宜パラメーター名を更新してください。

#### <a name="category"></a>カテゴリ

Core .NET ライブラリ

#### <a name="affected-apis"></a>影響を受ける API

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
