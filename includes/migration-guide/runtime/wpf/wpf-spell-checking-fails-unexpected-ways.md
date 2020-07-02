---
ms.openlocfilehash: d4f0095bc9fde98087dce528c8154d9c9ac6ddb7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621810"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a><span data-ttu-id="69f18-101">WPF スペル チェックが予期しない方法で失敗する</span><span class="sxs-lookup"><span data-stu-id="69f18-101">WPF Spell Checking fails in unexpected ways</span></span>

#### <a name="details"></a><span data-ttu-id="69f18-102">説明</span><span class="sxs-lookup"><span data-stu-id="69f18-102">Details</span></span>

<span data-ttu-id="69f18-103">これには、次の WPF スペル チェックのいくつかの問題が含まれます。</span><span class="sxs-lookup"><span data-stu-id="69f18-103">This includes a number of WPF Spell Checker issues:</span></span><ul><li><span data-ttu-id="69f18-104">WPF スペル チェックで <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName> がスローされる場合がある。</span><span class="sxs-lookup"><span data-stu-id="69f18-104">WPF Spell Checker sometimes throws <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName></span></span></li><li><span data-ttu-id="69f18-105">"別のユーザーとして実行" を使用してアプリケーションが起動された場合、WPF スペル チェックが <xref:System.UnauthorizedAccessException> で失敗する。</span><span class="sxs-lookup"><span data-stu-id="69f18-105">WPF Spell Checker fails with <xref:System.UnauthorizedAccessException> when applications are launched using 'run as different user'</span></span></li><li><span data-ttu-id="69f18-106">WPF スペル チェックで、ドイツ語の "Hausnummer" などの複合語のスペル ミスが正しく識別されない。</span><span class="sxs-lookup"><span data-stu-id="69f18-106">WPF Spell Checker incorrectly identifies spelling errors in compound words like 'Hausnummer' in German.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="69f18-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="69f18-107">Suggestion</span></span>

<span data-ttu-id="69f18-108">問題 1 - これは .NET Framework 4.6.2 で修正されました。問題 2 - "別のユーザーとして実行" を使用してアプリケーションが起動された場合、WPF スペル チェックがサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="69f18-108">Issue #1 - This has been fixed in .NET Framework 4.6.2 Issue #2 - WPF Spell Checker is no longer supported when applications are launched using 'run as different user'.</span></span> <span data-ttu-id="69f18-109">.NET Framework 4.6.2 以降では、このように起動されたアプリケーションが予期せずクラッシュしなくなります。代わりに、スペル チェックが自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="69f18-109">Starting .NET Framework 4.6.2, applications launched in this manner will no longer crash unexpectedly - instead the Spell Checker will be silently disabled.</span></span> <span data-ttu-id="69f18-110">問題 3 - これは .NET Framework 4.6.2 で修正されました。</span><span class="sxs-lookup"><span data-stu-id="69f18-110">Issue #3 - This has been fixed in .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="69f18-111">名前</span><span class="sxs-lookup"><span data-stu-id="69f18-111">Name</span></span>    | <span data-ttu-id="69f18-112">[値]</span><span class="sxs-lookup"><span data-stu-id="69f18-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="69f18-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="69f18-113">Scope</span></span>   |<span data-ttu-id="69f18-114">エッジ</span><span class="sxs-lookup"><span data-stu-id="69f18-114">Edge</span></span>|
|<span data-ttu-id="69f18-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="69f18-115">Version</span></span>|<span data-ttu-id="69f18-116">4.6.1</span><span class="sxs-lookup"><span data-stu-id="69f18-116">4.6.1</span></span>|
|<span data-ttu-id="69f18-117">種類</span><span class="sxs-lookup"><span data-stu-id="69f18-117">Type</span></span>|<span data-ttu-id="69f18-118">ランタイム</span><span class="sxs-lookup"><span data-stu-id="69f18-118">Runtime</span></span>|
