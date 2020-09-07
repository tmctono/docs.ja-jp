---
ms.openlocfilehash: af8de731ee93d0bfb01042d894f5730570dcdd78
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496385"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="d4322-101">デバッガーですぐに null コアレッサー値が表示されない</span><span class="sxs-lookup"><span data-stu-id="d4322-101">Null coalescer values are not visible in debugger until one step later</span></span>

#### <a name="details"></a><span data-ttu-id="d4322-102">説明</span><span class="sxs-lookup"><span data-stu-id="d4322-102">Details</span></span>

<span data-ttu-id="d4322-103">.NET Framework 4.5 のバグにより、64 ビット版の Framework で実行中に代入演算が実行された直後に、デバッガーで null 合体演算で設定された値が表示されません。</span><span class="sxs-lookup"><span data-stu-id="d4322-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d4322-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d4322-104">Suggestion</span></span>

<span data-ttu-id="d4322-105">デバッガーでの操作に時間がかかると、ローカル/フィールドの値が正しく更新されなくなります。</span><span class="sxs-lookup"><span data-stu-id="d4322-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="d4322-106">この問題は .NET Framework 4.6 で修正されました。このバージョンの .NET Framework にアップグレードすれば、問題は解決します。</span><span class="sxs-lookup"><span data-stu-id="d4322-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>

| <span data-ttu-id="d4322-107">名前</span><span class="sxs-lookup"><span data-stu-id="d4322-107">Name</span></span>    | <span data-ttu-id="d4322-108">[値]</span><span class="sxs-lookup"><span data-stu-id="d4322-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d4322-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="d4322-109">Scope</span></span>   |<span data-ttu-id="d4322-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="d4322-110">Edge</span></span>|
|<span data-ttu-id="d4322-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="d4322-111">Version</span></span>|<span data-ttu-id="d4322-112">4.5</span><span class="sxs-lookup"><span data-stu-id="d4322-112">4.5</span></span>|
|<span data-ttu-id="d4322-113">種類</span><span class="sxs-lookup"><span data-stu-id="d4322-113">Type</span></span>|<span data-ttu-id="d4322-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="d4322-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d4322-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d4322-115">Affected APIs</span></span>

<span data-ttu-id="d4322-116">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="d4322-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
