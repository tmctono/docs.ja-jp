---
ms.openlocfilehash: 5c949b79eefa68ea6f8d4ad27c716c438e24f170
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620215"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="67452-101">アプリ ドメイン全体でのオブジェクトの逆シリアル化に失敗する可能性がある</span><span class="sxs-lookup"><span data-stu-id="67452-101">Deserialization of objects across appdomains can fail</span></span>

#### <a name="details"></a><span data-ttu-id="67452-102">説明</span><span class="sxs-lookup"><span data-stu-id="67452-102">Details</span></span>

<span data-ttu-id="67452-103">場合によっては、アプリが異なるアプリケーション ベースを持つ複数のアプリ ドメインを使用すると、アプリ ドメイン間で論理呼び出しコンテキストのオブジェクトを逆シリアル化しようとして、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="67452-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="67452-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="67452-104">Suggestion</span></span>

<span data-ttu-id="67452-105">「[軽減策:アプリ ドメイン全体でのオブジェクトの逆シリアル化](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67452-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>

| <span data-ttu-id="67452-106">名前</span><span class="sxs-lookup"><span data-stu-id="67452-106">Name</span></span>    | <span data-ttu-id="67452-107">[値]</span><span class="sxs-lookup"><span data-stu-id="67452-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="67452-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="67452-108">Scope</span></span>   |<span data-ttu-id="67452-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="67452-109">Edge</span></span>|
|<span data-ttu-id="67452-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="67452-110">Version</span></span>|<span data-ttu-id="67452-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="67452-111">4.5.1</span></span>|
|<span data-ttu-id="67452-112">種類</span><span class="sxs-lookup"><span data-stu-id="67452-112">Type</span></span>|<span data-ttu-id="67452-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="67452-113">Runtime</span></span>|
