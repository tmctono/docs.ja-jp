---
ms.openlocfilehash: 46f6f77a543dfcf2073063d8ec200ef7d71e6b1f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077593"
---
### <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a>Blazor: JSObjectReference および JSInProcessObjectReference 型を internal に変更

ASP.NET Core 5.0 RC1 で導入された新しい `Microsoft.JSInterop.JSObjectReference` および `Microsoft.JSInterop.JSInProcessObjectReference` 型は `internal` としてマークされています。

#### <a name="version-introduced"></a>導入されたバージョン

5.0 RC2

#### <a name="old-behavior"></a>以前の動作

`JSObjectReference` は、`IJSRuntime` 経由で JavaScript の相互運用呼び出しから取得できます。 次に例を示します。

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

#### <a name="new-behavior"></a>新しい動作

`JSObjectReference` では [internal](../../../../docs/csharp/language-reference/keywords/internal.md) アクセス修飾子が使用されます。 代わりに `public` `IJSObjectReference` インターフェイスを使用する必要があります。 次に例を示します。

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

`JSInProcessObjectReference` も `internal` としてマークされ、`IJSInProcessObjectReference` によって置き換えられました。

#### <a name="reason-for-change"></a>変更理由

この変更により、JavaScript の相互運用機能が Blazor 内の他のパターンとより一貫したものになります。 `IJSObjectReference` は、同様の目的で機能し、同様のメソッドと拡張機能を備えているという点で `IJSRuntime` に似ています。

#### <a name="recommended-action"></a>推奨アクション

`JSObjectReference` と `JSInProcessObjectReference` の使用を、それぞれ `IJSObjectReference` と `IJSInProcessObjectReference` に置換します。

#### <a name="category"></a>カテゴリ

ASP.NET Core

#### <a name="affected-apis"></a>影響を受ける API

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

#### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
