---
ms.openlocfilehash: 3f82a4daac3b5d8981532f0c82e9a76f13c68b6e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496441"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="b89fa-101">アプリ ドメイン全体でのオブジェクトの逆シリアル化に失敗する可能性がある</span><span class="sxs-lookup"><span data-stu-id="b89fa-101">Deserialization of objects across appdomains can fail</span></span>

#### <a name="details"></a><span data-ttu-id="b89fa-102">説明</span><span class="sxs-lookup"><span data-stu-id="b89fa-102">Details</span></span>

<span data-ttu-id="b89fa-103">場合によっては、アプリが異なるアプリケーション ベースを持つ複数のアプリ ドメインを使用すると、アプリ ドメイン間で論理呼び出しコンテキストのオブジェクトを逆シリアル化しようとして、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="b89fa-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b89fa-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="b89fa-104">Suggestion</span></span>

<span data-ttu-id="b89fa-105">「[軽減策:アプリ ドメイン全体でのオブジェクトの逆シリアル化](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b89fa-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>

| <span data-ttu-id="b89fa-106">名前</span><span class="sxs-lookup"><span data-stu-id="b89fa-106">Name</span></span>    | <span data-ttu-id="b89fa-107">[値]</span><span class="sxs-lookup"><span data-stu-id="b89fa-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b89fa-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="b89fa-108">Scope</span></span>   |<span data-ttu-id="b89fa-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="b89fa-109">Edge</span></span>|
|<span data-ttu-id="b89fa-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="b89fa-110">Version</span></span>|<span data-ttu-id="b89fa-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="b89fa-111">4.5.1</span></span>|
|<span data-ttu-id="b89fa-112">種類</span><span class="sxs-lookup"><span data-stu-id="b89fa-112">Type</span></span>|<span data-ttu-id="b89fa-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="b89fa-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b89fa-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="b89fa-114">Affected APIs</span></span>

<span data-ttu-id="b89fa-115">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="b89fa-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
