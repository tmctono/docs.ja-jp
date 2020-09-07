---
ms.openlocfilehash: 151f88f1214e3abedf491761144ffc1a89d29e43
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496753"
---
### <a name="compiler-support-for-type-forwarding-when-multi-targeting-mscorlib"></a><span data-ttu-id="2dcde-101">mscorlib の複数バージョン対応時の型転送のコンパイラ サポート</span><span class="sxs-lookup"><span data-stu-id="2dcde-101">Compiler support for type forwarding when multi-targeting mscorlib</span></span>

#### <a name="details"></a><span data-ttu-id="2dcde-102">説明</span><span class="sxs-lookup"><span data-stu-id="2dcde-102">Details</span></span>

<span data-ttu-id="2dcde-103">新しい CodeDOM の機能を使用すると、mscorlib.dll の .NET Framework 4.5 バージョンではなく、mscorlib.dll の対象バージョンに対してコンパイルできるようになります。</span><span class="sxs-lookup"><span data-stu-id="2dcde-103">A new CodeDOM feature allows a compiler to compile against the targeted version of mscorlib.dll instead of the .NET Framework 4.5 version of mscorlib.dll.</span></span>

| <span data-ttu-id="2dcde-104">名前</span><span class="sxs-lookup"><span data-stu-id="2dcde-104">Name</span></span>    | <span data-ttu-id="2dcde-105">[値]</span><span class="sxs-lookup"><span data-stu-id="2dcde-105">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2dcde-106">スコープ</span><span class="sxs-lookup"><span data-stu-id="2dcde-106">Scope</span></span>   |<span data-ttu-id="2dcde-107">エッジ</span><span class="sxs-lookup"><span data-stu-id="2dcde-107">Edge</span></span>|
|<span data-ttu-id="2dcde-108">バージョン</span><span class="sxs-lookup"><span data-stu-id="2dcde-108">Version</span></span>|<span data-ttu-id="2dcde-109">4.5</span><span class="sxs-lookup"><span data-stu-id="2dcde-109">4.5</span></span>|
|<span data-ttu-id="2dcde-110">種類</span><span class="sxs-lookup"><span data-stu-id="2dcde-110">Type</span></span>|<span data-ttu-id="2dcde-111">ランタイム</span><span class="sxs-lookup"><span data-stu-id="2dcde-111">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2dcde-112">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="2dcde-112">Affected APIs</span></span>

<span data-ttu-id="2dcde-113">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="2dcde-113">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
