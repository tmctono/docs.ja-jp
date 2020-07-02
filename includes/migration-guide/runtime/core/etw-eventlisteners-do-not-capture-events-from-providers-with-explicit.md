---
ms.openlocfilehash: 7d50962b518c15875a5f1a82f5b89ab87a1db02e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620235"
---
### <a name="etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a><span data-ttu-id="94c54-101">ETW EventListeners は、明示的なキーワードを持つプロバイダーからのイベント (TPL プロバイダーなど) をキャプチャしません</span><span class="sxs-lookup"><span data-stu-id="94c54-101">ETW EventListeners do not capture events from providers with explicit keywords (like the TPL provider)</span></span>

#### <a name="details"></a><span data-ttu-id="94c54-102">説明</span><span class="sxs-lookup"><span data-stu-id="94c54-102">Details</span></span>

<span data-ttu-id="94c54-103">空白のキーワード マスクを持つ ETW EventListeners は、明示的なキーワードを持つプロバイダーからのイベントを正しくキャプチャしません。</span><span class="sxs-lookup"><span data-stu-id="94c54-103">ETW EventListeners with a blank keyword mask do not properly capture events from providers with explicit keywords.</span></span> <span data-ttu-id="94c54-104">.NET Framework 4.5 では、TPL プロバイダーは、明示的なキーワードを提供するようになり、この問題が発生しました。</span><span class="sxs-lookup"><span data-stu-id="94c54-104">In the .NET Framework 4.5, the TPL provider began providing explicit keywords and triggered this issue.</span></span> <span data-ttu-id="94c54-105">.NET Framework 4.6 では、EventListeners が更新され、この問題は修正されました。</span><span class="sxs-lookup"><span data-stu-id="94c54-105">In the .NET Framework 4.6, EventListeners have been updated to no longer have this issue.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="94c54-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="94c54-106">Suggestion</span></span>

<span data-ttu-id="94c54-107">この問題を回避するには、<xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> の呼び出しを、使用する &quot;任意のキーワード&quot; マスクを明示的に指定する EnableEvents オーバーロード (<code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>) の呼び出しに置換します。または、この問題は .NET Framework 4.6 で修正されたため、このバージョンの .NET Framework にアップグレードすることによって対処できます。</span><span class="sxs-lookup"><span data-stu-id="94c54-107">To work around this problem, replace calls to <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> with calls to the EnableEvents overload that explicitly specifies the &quot;any keywords&quot; mask to use: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>.Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="94c54-108">名前</span><span class="sxs-lookup"><span data-stu-id="94c54-108">Name</span></span>    | <span data-ttu-id="94c54-109">[値]</span><span class="sxs-lookup"><span data-stu-id="94c54-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="94c54-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="94c54-110">Scope</span></span>   |<span data-ttu-id="94c54-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="94c54-111">Edge</span></span>|
|<span data-ttu-id="94c54-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="94c54-112">Version</span></span>|<span data-ttu-id="94c54-113">4.5</span><span class="sxs-lookup"><span data-stu-id="94c54-113">4.5</span></span>|
|<span data-ttu-id="94c54-114">種類</span><span class="sxs-lookup"><span data-stu-id="94c54-114">Type</span></span>|<span data-ttu-id="94c54-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="94c54-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="94c54-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="94c54-116">Affected APIs</span></span>

-<xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li></ul>|
