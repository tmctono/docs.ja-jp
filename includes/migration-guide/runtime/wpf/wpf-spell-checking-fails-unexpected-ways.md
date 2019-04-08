---
ms.openlocfilehash: 8049bf01bc10c5913fa11b25e49afd1b1317eecc
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761402"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a><span data-ttu-id="c447d-101">WPF スペル チェックが予期しない方法で失敗する</span><span class="sxs-lookup"><span data-stu-id="c447d-101">WPF Spell Checking fails in unexpected ways</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c447d-102">説明</span><span class="sxs-lookup"><span data-stu-id="c447d-102">Details</span></span>|<span data-ttu-id="c447d-103">これには、次の WPF スペル チェックのいくつかの問題が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c447d-103">This includes a number of WPF Spell Checker issues:</span></span><ul><li><span data-ttu-id="c447d-104">WPF スペル チェックで <xref:System.Runtime.InteropServices.COMException?displayProperty=name> がスローされる場合がある。</span><span class="sxs-lookup"><span data-stu-id="c447d-104">WPF Spell Checker sometimes throws <xref:System.Runtime.InteropServices.COMException?displayProperty=name></span></span></li><li><span data-ttu-id="c447d-105">"別のユーザーとして実行" を使用してアプリケーションが起動された場合、WPF スペル チェックが <xref:System.UnauthorizedAccessException> で失敗する。</span><span class="sxs-lookup"><span data-stu-id="c447d-105">WPF Spell Checker fails with <xref:System.UnauthorizedAccessException> when applications are launched using 'run as different user'</span></span></li><li><span data-ttu-id="c447d-106">WPF スペル チェックで、ドイツ語の "Hausnummer" などの複合語のスペル ミスが正しく識別されない。</span><span class="sxs-lookup"><span data-stu-id="c447d-106">WPF Spell Checker incorrectly identifies spelling errors in compound words like 'Hausnummer' in German.</span></span></li></ul>|
|<span data-ttu-id="c447d-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="c447d-107">Suggestion</span></span>|<span data-ttu-id="c447d-108">問題 1 - これは .NET Framework 4.6.2 で修正されました。問題 2 - "別のユーザーとして実行" を使用してアプリケーションが起動された場合、WPF スペル チェックがサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c447d-108">Issue #1 - This has been fixed in .NET Framework 4.6.2 Issue #2 - WPF Spell Checker is no longer supported when applications are launched using 'run as different user'.</span></span> <span data-ttu-id="c447d-109">.NET Framework 4.6.2 以降では、このように起動されたアプリケーションが予期せずクラッシュしなくなります。代わりに、スペル チェックが自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="c447d-109">Starting .NET Framework 4.6.2, applications launched in this manner will no longer crash unexpectedly - instead the Spell Checker will be silently disabled.</span></span> <span data-ttu-id="c447d-110">問題 3 - これは .NET Framework 4.6.2 で修正されました。</span><span class="sxs-lookup"><span data-stu-id="c447d-110">Issue #3 - This has been fixed in .NET Framework 4.6.2.</span></span>|
|<span data-ttu-id="c447d-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="c447d-111">Scope</span></span>|<span data-ttu-id="c447d-112">エッジ</span><span class="sxs-lookup"><span data-stu-id="c447d-112">Edge</span></span>|
|<span data-ttu-id="c447d-113">Version</span><span class="sxs-lookup"><span data-stu-id="c447d-113">Version</span></span>|<span data-ttu-id="c447d-114">4.6.1</span><span class="sxs-lookup"><span data-stu-id="c447d-114">4.6.1</span></span>|
|<span data-ttu-id="c447d-115">型</span><span class="sxs-lookup"><span data-stu-id="c447d-115">Type</span></span>|<span data-ttu-id="c447d-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="c447d-116">Runtime</span></span>|

