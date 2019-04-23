---
ms.openlocfilehash: 891c29b731214fb0028e960256b79cfc267d86b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804373"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="b13d7-101">アプリ ドメイン全体でのオブジェクトの逆シリアル化に失敗する可能性がある</span><span class="sxs-lookup"><span data-stu-id="b13d7-101">Deserialization of objects across appdomains can fail</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b13d7-102">説明</span><span class="sxs-lookup"><span data-stu-id="b13d7-102">Details</span></span>|<span data-ttu-id="b13d7-103">場合によっては、アプリが異なるアプリケーション ベースを持つ複数のアプリ ドメインを使用すると、アプリ ドメイン間で論理呼び出しコンテキストのオブジェクトを逆シリアル化しようとして、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="b13d7-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>|
|<span data-ttu-id="b13d7-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="b13d7-104">Suggestion</span></span>|<span data-ttu-id="b13d7-105">「[軽減策:アプリ ドメイン全体でのオブジェクトの逆シリアル化](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b13d7-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>|
|<span data-ttu-id="b13d7-106">スコープ</span><span class="sxs-lookup"><span data-stu-id="b13d7-106">Scope</span></span>|<span data-ttu-id="b13d7-107">エッジ</span><span class="sxs-lookup"><span data-stu-id="b13d7-107">Edge</span></span>|
|<span data-ttu-id="b13d7-108">Version</span><span class="sxs-lookup"><span data-stu-id="b13d7-108">Version</span></span>|<span data-ttu-id="b13d7-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="b13d7-109">4.5.1</span></span>|
|<span data-ttu-id="b13d7-110">型</span><span class="sxs-lookup"><span data-stu-id="b13d7-110">Type</span></span>|<span data-ttu-id="b13d7-111">ランタイム</span><span class="sxs-lookup"><span data-stu-id="b13d7-111">Runtime</span></span>|
