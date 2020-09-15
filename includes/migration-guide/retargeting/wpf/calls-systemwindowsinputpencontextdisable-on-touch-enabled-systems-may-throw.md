---
ms.openlocfilehash: a44458484ea09c566defeabc9b604bd55d994e93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617539"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="af431-101">タッチ対応システムで System.Windows.Input.PenContext.Disable を呼び出すと ArgumentException がスローされることがある</span><span class="sxs-lookup"><span data-stu-id="af431-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

#### <a name="details"></a><span data-ttu-id="af431-102">説明</span><span class="sxs-lookup"><span data-stu-id="af431-102">Details</span></span>

<span data-ttu-id="af431-103">一部の状況では、タッチ対応システムで内部 **System.Windows.Intput.PenContext.Disable** メソッドを呼び出すと、再入に起因して未処理の `T:System.ArgumentException` がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="af431-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled `T:System.ArgumentException` because of reentrancy.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="af431-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="af431-104">Suggestion</span></span>

<span data-ttu-id="af431-105">この問題は、.NET Framework 4.7 では対処済みです。</span><span class="sxs-lookup"><span data-stu-id="af431-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="af431-106">例外を防ぐには、.NET Framework 4.7 以降のバージョンの .NET Framework にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="af431-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>

| <span data-ttu-id="af431-107">名前</span><span class="sxs-lookup"><span data-stu-id="af431-107">Name</span></span>    | <span data-ttu-id="af431-108">[値]</span><span class="sxs-lookup"><span data-stu-id="af431-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="af431-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="af431-109">Scope</span></span>   | <span data-ttu-id="af431-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="af431-110">Edge</span></span>        |
| <span data-ttu-id="af431-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="af431-111">Version</span></span> | <span data-ttu-id="af431-112">4.6.1</span><span class="sxs-lookup"><span data-stu-id="af431-112">4.6.1</span></span>       |
| <span data-ttu-id="af431-113">種類</span><span class="sxs-lookup"><span data-stu-id="af431-113">Type</span></span>    | <span data-ttu-id="af431-114">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="af431-114">Retargeting</span></span> |
