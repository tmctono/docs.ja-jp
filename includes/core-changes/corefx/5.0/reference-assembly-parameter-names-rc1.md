---
ms.openlocfilehash: 760c9ce2427bc1f5e9276e66ecb6d2cf2ed83c16
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738822"
---
### <a name="parameter-names-changed-in-rc1"></a><span data-ttu-id="90e20-101">RC1 でパラメーター名が変更されている</span><span class="sxs-lookup"><span data-stu-id="90e20-101">Parameter names changed in RC1</span></span>

<span data-ttu-id="90e20-102">一部の参照アセンブリ パラメーター名が、実装アセンブリ内のパラメーター名と一致するように変更されました。</span><span class="sxs-lookup"><span data-stu-id="90e20-102">Some reference assembly parameter names have changed to match parameter names in the implementation assemblies.</span></span>

#### <a name="change-description"></a><span data-ttu-id="90e20-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="90e20-103">Change description</span></span>

<span data-ttu-id="90e20-104">以前の .NET 5.0 Preview および RC バージョンでは、一部の[参照アセンブリ](../../../../docs/standard/assembly/reference-assemblies.md)のパラメーター名が、実装アセンブリ内にある対応するパラメーターのものとは異なっています。</span><span class="sxs-lookup"><span data-stu-id="90e20-104">In previous .NET 5.0 preview and RC versions, some [reference assembly](../../../../docs/standard/assembly/reference-assemblies.md) parameter names are different to their corresponding parameters in the implementation assembly.</span></span> <span data-ttu-id="90e20-105">これにより、名前付き引数とリフレクションの使用中に問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90e20-105">This can cause problems while using named arguments and reflection.</span></span>

<span data-ttu-id="90e20-106">.NET 5.0 RC2 では、参照アセンブリ内でこのような不一致のパラメーター名が更新され、実装アセンブリ内の対応するパラメーター名と完全に一致するようになりました。</span><span class="sxs-lookup"><span data-stu-id="90e20-106">In .NET 5.0 RC2, these mismatched parameter names were updated in the reference assemblies to exactly match the corresponding parameter names in the implementation assemblies.</span></span>

<span data-ttu-id="90e20-107">次の表に API と変更されたパラメーター名を示します。</span><span class="sxs-lookup"><span data-stu-id="90e20-107">The following table shows the APIs and parameter names that changed.</span></span>

| <span data-ttu-id="90e20-108">API</span><span class="sxs-lookup"><span data-stu-id="90e20-108">API</span></span> | <span data-ttu-id="90e20-109">古いパラメーター名</span><span class="sxs-lookup"><span data-stu-id="90e20-109">Old parameter name</span></span> | <span data-ttu-id="90e20-110">新しいパラメーター名</span><span class="sxs-lookup"><span data-stu-id="90e20-110">New parameter name</span></span> |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

#### <a name="reason-for-change"></a><span data-ttu-id="90e20-111">変更理由</span><span class="sxs-lookup"><span data-stu-id="90e20-111">Reason for change</span></span>

<span data-ttu-id="90e20-112">一貫性を保つため、および名前付き引数とリフレクションを使用するときにエラーが発生するのを回避するために、パラメーター名が変更されました。</span><span class="sxs-lookup"><span data-stu-id="90e20-112">The parameter names were changed for consistency and to avoid failures when using named arguments and reflection.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="90e20-113">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="90e20-113">Version introduced</span></span>

<span data-ttu-id="90e20-114">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="90e20-114">5.0 RC2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="90e20-115">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="90e20-115">Recommended action</span></span>

<span data-ttu-id="90e20-116">パラメーター名の変更が原因で、コンパイラ エラーが発生する場合は、適宜パラメーター名を更新してください。</span><span class="sxs-lookup"><span data-stu-id="90e20-116">If you encounter a compiler error due to a parameter name change, update the parameter name accordingly.</span></span>

#### <a name="category"></a><span data-ttu-id="90e20-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="90e20-117">Category</span></span>

<span data-ttu-id="90e20-118">Core .NET ライブラリ</span><span class="sxs-lookup"><span data-stu-id="90e20-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="90e20-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="90e20-119">Affected APIs</span></span>

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
