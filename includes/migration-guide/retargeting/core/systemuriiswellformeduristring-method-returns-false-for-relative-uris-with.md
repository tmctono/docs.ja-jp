---
ms.openlocfilehash: f7dcf9c4c3dc7ea536ddc847769a1a30f1298bb2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617213"
---
### <a name="systemuriiswellformeduristring-method-returns-false-for-relative-uris-with-a-colon-char-in-first-segment"></a><span data-ttu-id="85eec-101">最初のセグメントにコロン文字を含む相対 URI に対して System.Uri.IsWellFormedUriString メソッドが false を返す</span><span class="sxs-lookup"><span data-stu-id="85eec-101">System.Uri.IsWellFormedUriString method returns false for relative URIs with a colon char in first segment</span></span>

#### <a name="details"></a><span data-ttu-id="85eec-102">説明</span><span class="sxs-lookup"><span data-stu-id="85eec-102">Details</span></span>

<span data-ttu-id="85eec-103">.NET Framework 4.5 より、<xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> では、最初のセグメントに `:` を含む相対 URI が形式が正しくないとして処理されます。</span><span class="sxs-lookup"><span data-stu-id="85eec-103">Beginning with the .NET Framework 4.5, <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> will treat relative URIs with a `:` in their first segment as not well formed.</span></span> <span data-ttu-id="85eec-104">これは .NET Framework 4.0 の <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> 動作からの変更であり、RFC3986 に準拠する目的で行われました。</span><span class="sxs-lookup"><span data-stu-id="85eec-104">This is a change from <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> behavior in the .NET Framework 4.0 that was made to conform to RFC3986.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="85eec-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="85eec-105">Suggestion</span></span>

<span data-ttu-id="85eec-106">この変更は (他の多くの URI 変更と同様に) .NET Framework 4.5 (以降) を対象とするアプリケーションにのみ影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="85eec-106">This change (like many other URI changes) will only affect applications targeting the .NET Framework 4.5 (or later).</span></span> <span data-ttu-id="85eec-107">以前の動作を維持するには、アプリの対象を .NET Framework 4.0 にします。</span><span class="sxs-lookup"><span data-stu-id="85eec-107">To keep using the old behavior, target the app against the .NET Framework 4.0.</span></span> <span data-ttu-id="85eec-108">あるいは、<xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> を呼び出す前に URI を調べて `:` 文字を探し、以前の動作が望ましければそれを削除し、正しい形式として処理させます。</span><span class="sxs-lookup"><span data-stu-id="85eec-108">Alternatively, scan URI's prior to calling <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> looking for `:` characters that you may want to remove for validation purposes, if the old behavior is desirable.</span></span>

| <span data-ttu-id="85eec-109">名前</span><span class="sxs-lookup"><span data-stu-id="85eec-109">Name</span></span>    | <span data-ttu-id="85eec-110">[値]</span><span class="sxs-lookup"><span data-stu-id="85eec-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="85eec-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="85eec-111">Scope</span></span>   | <span data-ttu-id="85eec-112">マイナー</span><span class="sxs-lookup"><span data-stu-id="85eec-112">Minor</span></span>       |
| <span data-ttu-id="85eec-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="85eec-113">Version</span></span> | <span data-ttu-id="85eec-114">4.5</span><span class="sxs-lookup"><span data-stu-id="85eec-114">4.5</span></span>         |
| <span data-ttu-id="85eec-115">種類</span><span class="sxs-lookup"><span data-stu-id="85eec-115">Type</span></span>    | <span data-ttu-id="85eec-116">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="85eec-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="85eec-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="85eec-117">Affected APIs</span></span>

- <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=nameWithType>
