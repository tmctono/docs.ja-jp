---
ms.openlocfilehash: 71c81cf188fa4c2300661f10eb87e7ae00e031f6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804417"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a><span data-ttu-id="1dcdf-101">サフィックスの "Start" または "Stop" のみで ETW イベント名を使い分けることができない</span><span class="sxs-lookup"><span data-stu-id="1dcdf-101">ETW event names cannot differ only by a "Start" or "Stop" suffix</span></span>

|   |   |
|---|---|
|<span data-ttu-id="1dcdf-102">説明</span><span class="sxs-lookup"><span data-stu-id="1dcdf-102">Details</span></span>|<span data-ttu-id="1dcdf-103">.NET Framework 4.6 と 4.6.1 では、2 つの ETW (Windows イベント トレーシング) イベント名の違いがサフィックスの <xref:System.ArgumentException>Start&quot; または &quot;Stop&quot; のみのとき (たとえば、あるイベントの名前が &quot; で、別のイベントの名前が <code>LogUser</code> のとき)、ランタイムによって <code>LogUserStart</code> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="1dcdf-103">In the .NET Framework 4.6 and 4.6.1, the runtime throws an <xref:System.ArgumentException> when two Event Tracing for Windows (ETW) event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix (as when one event is named <code>LogUser</code> and another is named <code>LogUserStart</code>).</span></span> <span data-ttu-id="1dcdf-104">この場合、ランタイムはイベント ソースを作成できないため、ログ記録は生成できません。</span><span class="sxs-lookup"><span data-stu-id="1dcdf-104">In this case, the runtime cannot construct the event source, which cannot emit any logging.</span></span>|
|<span data-ttu-id="1dcdf-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="1dcdf-105">Suggestion</span></span>|<span data-ttu-id="1dcdf-106">この例外を回避するには、サフィックスの &quot;Start&quot; または &quot;Stop&quot; でしか違いのないイベント名が存在しないようにします。この要件は .NET Framework 4.6.2 以降で削除されています。サフィックスの &quot;Start&quot; と &quot;Stop&quot; のみが異なるイベント名がランタイムによって区別されます。</span><span class="sxs-lookup"><span data-stu-id="1dcdf-106">To prevent the exception, ensure that no two event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix.This requirement is removed starting with the .NET Framework 4.6.2; the runtime can disambiguate event names that differ only by the &quot;Start&quot; and &quot;Stop&quot; suffix.</span></span>|
|<span data-ttu-id="1dcdf-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="1dcdf-107">Scope</span></span>|<span data-ttu-id="1dcdf-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="1dcdf-108">Edge</span></span>|
|<span data-ttu-id="1dcdf-109">バージョン</span><span class="sxs-lookup"><span data-stu-id="1dcdf-109">Version</span></span>|<span data-ttu-id="1dcdf-110">4.6</span><span class="sxs-lookup"><span data-stu-id="1dcdf-110">4.6</span></span>|
|<span data-ttu-id="1dcdf-111">[種類]</span><span class="sxs-lookup"><span data-stu-id="1dcdf-111">Type</span></span>|<span data-ttu-id="1dcdf-112">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="1dcdf-112">Retargeting</span></span>|
