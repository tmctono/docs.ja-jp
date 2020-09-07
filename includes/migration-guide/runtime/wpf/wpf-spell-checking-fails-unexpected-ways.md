---
ms.openlocfilehash: d4e60f2a59980263916718ebcc71cc359952c031
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496367"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a><span data-ttu-id="a45ce-101">WPF スペル チェックが予期しない方法で失敗する</span><span class="sxs-lookup"><span data-stu-id="a45ce-101">WPF Spell Checking fails in unexpected ways</span></span>

#### <a name="details"></a><span data-ttu-id="a45ce-102">説明</span><span class="sxs-lookup"><span data-stu-id="a45ce-102">Details</span></span>

<span data-ttu-id="a45ce-103">これには、次の WPF スペル チェックのいくつかの問題が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a45ce-103">This includes a number of WPF Spell Checker issues:</span></span><ul><li><span data-ttu-id="a45ce-104">WPF スペル チェックで <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName> がスローされる場合がある。</span><span class="sxs-lookup"><span data-stu-id="a45ce-104">WPF Spell Checker sometimes throws <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName></span></span></li><li><span data-ttu-id="a45ce-105">"別のユーザーとして実行" を使用してアプリケーションが起動された場合、WPF スペル チェックが <xref:System.UnauthorizedAccessException> で失敗する。</span><span class="sxs-lookup"><span data-stu-id="a45ce-105">WPF Spell Checker fails with <xref:System.UnauthorizedAccessException> when applications are launched using 'run as different user'</span></span></li><li><span data-ttu-id="a45ce-106">WPF スペル チェックで、ドイツ語の "Hausnummer" などの複合語のスペル ミスが正しく識別されない。</span><span class="sxs-lookup"><span data-stu-id="a45ce-106">WPF Spell Checker incorrectly identifies spelling errors in compound words like 'Hausnummer' in German.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="a45ce-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="a45ce-107">Suggestion</span></span>

<span data-ttu-id="a45ce-108">問題 1 - これは .NET Framework 4.6.2 で修正されました。問題 2 - "別のユーザーとして実行" を使用してアプリケーションが起動された場合、WPF スペル チェックがサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a45ce-108">Issue #1 - This has been fixed in .NET Framework 4.6.2 Issue #2 - WPF Spell Checker is no longer supported when applications are launched using 'run as different user'.</span></span> <span data-ttu-id="a45ce-109">.NET Framework 4.6.2 以降では、このように起動されたアプリケーションが予期せずクラッシュしなくなります。代わりに、スペル チェックが自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="a45ce-109">Starting .NET Framework 4.6.2, applications launched in this manner will no longer crash unexpectedly - instead the Spell Checker will be silently disabled.</span></span> <span data-ttu-id="a45ce-110">問題 3 - これは .NET Framework 4.6.2 で修正されました。</span><span class="sxs-lookup"><span data-stu-id="a45ce-110">Issue #3 - This has been fixed in .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="a45ce-111">名前</span><span class="sxs-lookup"><span data-stu-id="a45ce-111">Name</span></span>    | <span data-ttu-id="a45ce-112">[値]</span><span class="sxs-lookup"><span data-stu-id="a45ce-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a45ce-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="a45ce-113">Scope</span></span>   |<span data-ttu-id="a45ce-114">エッジ</span><span class="sxs-lookup"><span data-stu-id="a45ce-114">Edge</span></span>|
|<span data-ttu-id="a45ce-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="a45ce-115">Version</span></span>|<span data-ttu-id="a45ce-116">4.6.1</span><span class="sxs-lookup"><span data-stu-id="a45ce-116">4.6.1</span></span>|
|<span data-ttu-id="a45ce-117">種類</span><span class="sxs-lookup"><span data-stu-id="a45ce-117">Type</span></span>|<span data-ttu-id="a45ce-118">ランタイム</span><span class="sxs-lookup"><span data-stu-id="a45ce-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a45ce-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="a45ce-119">Affected APIs</span></span>

<span data-ttu-id="a45ce-120">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="a45ce-120">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
