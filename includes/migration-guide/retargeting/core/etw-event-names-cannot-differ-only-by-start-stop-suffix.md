---
ms.openlocfilehash: 0e25d5d9b545e5cb400cbf701fb13da572fadf10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614673"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a><span data-ttu-id="cc7d2-101">サフィックスの "Start" または "Stop" のみで ETW イベント名を使い分けることができない</span><span class="sxs-lookup"><span data-stu-id="cc7d2-101">ETW event names cannot differ only by a "Start" or "Stop" suffix</span></span>

#### <a name="details"></a><span data-ttu-id="cc7d2-102">説明</span><span class="sxs-lookup"><span data-stu-id="cc7d2-102">Details</span></span>

<span data-ttu-id="cc7d2-103">.NET Framework 4.6 と4.6.1 では、2 つの Windows イベント トレーシング (ETW) のイベント名の違いが、"Start" または "Stop" のサフィックスのみである場合 (あるイベントの名前が `LogUser` で、別のイベントの名前が `LogUserStart` の場合など)、ランタイムにより <xref:System.ArgumentException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-103">In the .NET Framework 4.6 and 4.6.1, the runtime throws an <xref:System.ArgumentException> when two Event Tracing for Windows (ETW) event names differ only by a "Start" or "Stop" suffix (as when one event is named `LogUser` and another is named `LogUserStart`).</span></span> <span data-ttu-id="cc7d2-104">この場合、ランタイムはイベント ソースを作成できないため、ログ記録は生成できません。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-104">In this case, the runtime cannot construct the event source, which cannot emit any logging.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cc7d2-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="cc7d2-105">Suggestion</span></span>

<span data-ttu-id="cc7d2-106">この例外を回避するには、"Start" または "Stop" のサフィックスだけが異なる 2 つのイベント名が存在しないようにします。この要件は、.NET Framework 4.6.2 以降では削除されています。ランタイムは、"Start" と "Stop" のサフィックスだけが異なるイベント名を明確に区別できます。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-106">To prevent the exception, ensure that no two event names differ only by a "Start" or "Stop" suffix.This requirement is removed starting with the .NET Framework 4.6.2; the runtime can disambiguate event names that differ only by the "Start" and "Stop" suffix.</span></span>

| <span data-ttu-id="cc7d2-107">名前</span><span class="sxs-lookup"><span data-stu-id="cc7d2-107">Name</span></span>    | <span data-ttu-id="cc7d2-108">[値]</span><span class="sxs-lookup"><span data-stu-id="cc7d2-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cc7d2-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="cc7d2-109">Scope</span></span>   | <span data-ttu-id="cc7d2-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="cc7d2-110">Edge</span></span>        |
| <span data-ttu-id="cc7d2-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="cc7d2-111">Version</span></span> | <span data-ttu-id="cc7d2-112">4.6</span><span class="sxs-lookup"><span data-stu-id="cc7d2-112">4.6</span></span>         |
| <span data-ttu-id="cc7d2-113">種類</span><span class="sxs-lookup"><span data-stu-id="cc7d2-113">Type</span></span>    | <span data-ttu-id="cc7d2-114">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="cc7d2-114">Retargeting</span></span> |
