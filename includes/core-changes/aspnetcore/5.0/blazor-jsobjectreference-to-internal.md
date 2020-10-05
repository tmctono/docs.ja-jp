---
ms.openlocfilehash: 46f6f77a543dfcf2073063d8ec200ef7d71e6b1f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077593"
---
### <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a><span data-ttu-id="85d05-101">Blazor: JSObjectReference および JSInProcessObjectReference 型を internal に変更</span><span class="sxs-lookup"><span data-stu-id="85d05-101">Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal</span></span>

<span data-ttu-id="85d05-102">ASP.NET Core 5.0 RC1 で導入された新しい `Microsoft.JSInterop.JSObjectReference` および `Microsoft.JSInterop.JSInProcessObjectReference` 型は `internal` としてマークされています。</span><span class="sxs-lookup"><span data-stu-id="85d05-102">The new `Microsoft.JSInterop.JSObjectReference` and `Microsoft.JSInterop.JSInProcessObjectReference` types introduced in ASP.NET Core 5.0 RC1 have been marked as `internal`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="85d05-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="85d05-103">Version introduced</span></span>

<span data-ttu-id="85d05-104">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="85d05-104">5.0 RC2</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="85d05-105">以前の動作</span><span class="sxs-lookup"><span data-stu-id="85d05-105">Old behavior</span></span>

<span data-ttu-id="85d05-106">`JSObjectReference` は、`IJSRuntime` 経由で JavaScript の相互運用呼び出しから取得できます。</span><span class="sxs-lookup"><span data-stu-id="85d05-106">A `JSObjectReference` can be obtained from a JavaScript interop call via `IJSRuntime`.</span></span> <span data-ttu-id="85d05-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="85d05-107">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

#### <a name="new-behavior"></a><span data-ttu-id="85d05-108">新しい動作</span><span class="sxs-lookup"><span data-stu-id="85d05-108">New behavior</span></span>

<span data-ttu-id="85d05-109">`JSObjectReference` では [internal](../../../../docs/csharp/language-reference/keywords/internal.md) アクセス修飾子が使用されます。</span><span class="sxs-lookup"><span data-stu-id="85d05-109">`JSObjectReference` uses the [internal](../../../../docs/csharp/language-reference/keywords/internal.md) access modifier.</span></span> <span data-ttu-id="85d05-110">代わりに `public` `IJSObjectReference` インターフェイスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85d05-110">The `public` `IJSObjectReference` interface must be used instead.</span></span> <span data-ttu-id="85d05-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="85d05-111">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

<span data-ttu-id="85d05-112">`JSInProcessObjectReference` も `internal` としてマークされ、`IJSInProcessObjectReference` によって置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="85d05-112">`JSInProcessObjectReference` was also marked as `internal` and was replaced by `IJSInProcessObjectReference`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="85d05-113">変更理由</span><span class="sxs-lookup"><span data-stu-id="85d05-113">Reason for change</span></span>

<span data-ttu-id="85d05-114">この変更により、JavaScript の相互運用機能が Blazor 内の他のパターンとより一貫したものになります。</span><span class="sxs-lookup"><span data-stu-id="85d05-114">The change makes the JavaScript interop feature more consistent with other patterns within Blazor.</span></span> <span data-ttu-id="85d05-115">`IJSObjectReference` は、同様の目的で機能し、同様のメソッドと拡張機能を備えているという点で `IJSRuntime` に似ています。</span><span class="sxs-lookup"><span data-stu-id="85d05-115">`IJSObjectReference` is analogous to `IJSRuntime` in that it serves a similar purpose and has similar methods and extensions.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="85d05-116">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="85d05-116">Recommended action</span></span>

<span data-ttu-id="85d05-117">`JSObjectReference` と `JSInProcessObjectReference` の使用を、それぞれ `IJSObjectReference` と `IJSInProcessObjectReference` に置換します。</span><span class="sxs-lookup"><span data-stu-id="85d05-117">Replace occurrences of `JSObjectReference` and `JSInProcessObjectReference` with `IJSObjectReference` and `IJSInProcessObjectReference`, respectively.</span></span>

#### <a name="category"></a><span data-ttu-id="85d05-118">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="85d05-118">Category</span></span>

<span data-ttu-id="85d05-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="85d05-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="85d05-120">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="85d05-120">Affected APIs</span></span>

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

#### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
