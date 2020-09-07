---
ms.openlocfilehash: 30d12db888c3ac612b0717f903cea64e572e9725
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497271"
---
### <a name="entityframework-60-loads-very-slowly-in-apps-launched-from-visual-studio"></a><span data-ttu-id="d63c2-101">EntityFramework 6.0 は、Visual Studio から起動されたアプリを読み込むとき、非常に遅くなる</span><span class="sxs-lookup"><span data-stu-id="d63c2-101">EntityFramework 6.0 loads very slowly in apps launched from Visual Studio</span></span>

#### <a name="details"></a><span data-ttu-id="d63c2-102">説明</span><span class="sxs-lookup"><span data-stu-id="d63c2-102">Details</span></span>

<span data-ttu-id="d63c2-103">Entity Framework 6.0 を使用するアプリを Visual Studio 2013 から起動すると、非常に遅くなることがあります。</span><span class="sxs-lookup"><span data-stu-id="d63c2-103">Launching an app from Visual Studio 2013 that uses EntityFramework 6.0 can be very slow.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d63c2-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d63c2-104">Suggestion</span></span>

<span data-ttu-id="d63c2-105">この問題は、EntityFramework 6.0.2 で修正されます。</span><span class="sxs-lookup"><span data-stu-id="d63c2-105">This issue is fixed in EntityFramework 6.0.2.</span></span> <span data-ttu-id="d63c2-106">パフォーマンス問題を回避するには、EntityFramework を更新します。</span><span class="sxs-lookup"><span data-stu-id="d63c2-106">Update EntityFramework to avoid the performance issue.</span></span>

| <span data-ttu-id="d63c2-107">名前</span><span class="sxs-lookup"><span data-stu-id="d63c2-107">Name</span></span>    | <span data-ttu-id="d63c2-108">[値]</span><span class="sxs-lookup"><span data-stu-id="d63c2-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d63c2-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="d63c2-109">Scope</span></span>   |<span data-ttu-id="d63c2-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="d63c2-110">Edge</span></span>|
|<span data-ttu-id="d63c2-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="d63c2-111">Version</span></span>|<span data-ttu-id="d63c2-112">4.5</span><span class="sxs-lookup"><span data-stu-id="d63c2-112">4.5</span></span>|
|<span data-ttu-id="d63c2-113">種類</span><span class="sxs-lookup"><span data-stu-id="d63c2-113">Type</span></span>|<span data-ttu-id="d63c2-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="d63c2-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d63c2-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d63c2-115">Affected APIs</span></span>

<span data-ttu-id="d63c2-116">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="d63c2-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
