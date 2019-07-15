---
ms.openlocfilehash: 9ad283af76085c228bedceb6db723a1d18b10210
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804417"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a><span data-ttu-id="0ea1a-101">サフィックスの "Start" または "Stop" のみで ETW イベント名を使い分けることができない</span><span class="sxs-lookup"><span data-stu-id="0ea1a-101">ETW event names cannot differ only by a "Start" or "Stop" suffix</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0ea1a-102">説明</span><span class="sxs-lookup"><span data-stu-id="0ea1a-102">Details</span></span>|<span data-ttu-id="0ea1a-103">.NET Framework 4.6 と 4.6.1 では、2 つの ETW (Windows イベント トレーシング) イベント名の違いがサフィックスの &quot;Start&quot; または &quot;Stop&quot; のみのとき (たとえば、あるイベントの名前が <code>LogUser</code> で、別のイベントの名前が <code>LogUserStart</code> のとき)、ランタイムによって <xref:System.ArgumentException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="0ea1a-103">In the .NET Framework 4.6 and 4.6.1, the runtime throws an <xref:System.ArgumentException> when two Event Tracing for Windows (ETW) event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix (as when one event is named <code>LogUser</code> and another is named <code>LogUserStart</code>).</span></span> <span data-ttu-id="0ea1a-104">この場合、ランタイムはイベント ソースを作成できないため、ログ記録は生成できません。</span><span class="sxs-lookup"><span data-stu-id="0ea1a-104">In this case, the runtime cannot construct the event source, which cannot emit any logging.</span></span>|
|<span data-ttu-id="0ea1a-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="0ea1a-105">Suggestion</span></span>|<span data-ttu-id="0ea1a-106">この例外を回避するには、サフィックスの &quot;Start&quot; または &quot;Stop&quot; でしか違いのないイベント名が存在しないようにします。この要件は .NET Framework 4.6.2 以降で削除されています。サフィックスの &quot;Start&quot; と &quot;Stop&quot; のみが異なるイベント名がランタイムによって区別されます。</span><span class="sxs-lookup"><span data-stu-id="0ea1a-106">To prevent the exception, ensure that no two event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix.This requirement is removed starting with the .NET Framework 4.6.2; the runtime can disambiguate event names that differ only by the &quot;Start&quot; and &quot;Stop&quot; suffix.</span></span>|
|<span data-ttu-id="0ea1a-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="0ea1a-107">Scope</span></span>|<span data-ttu-id="0ea1a-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="0ea1a-108">Edge</span></span>|
|<span data-ttu-id="0ea1a-109">Version</span><span class="sxs-lookup"><span data-stu-id="0ea1a-109">Version</span></span>|<span data-ttu-id="0ea1a-110">4.6</span><span class="sxs-lookup"><span data-stu-id="0ea1a-110">4.6</span></span>|
|<span data-ttu-id="0ea1a-111">型</span><span class="sxs-lookup"><span data-stu-id="0ea1a-111">Type</span></span>|<span data-ttu-id="0ea1a-112">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="0ea1a-112">Retargeting</span></span>|

