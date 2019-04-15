---
ms.openlocfilehash: 6dc3669433804a4524c18d5a932f9879343ab508
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235457"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a><span data-ttu-id="ba897-101">OData URL の Replace メソッドが既定で無効になる</span><span class="sxs-lookup"><span data-stu-id="ba897-101">The Replace method in OData URLs is disabled by default</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ba897-102">説明</span><span class="sxs-lookup"><span data-stu-id="ba897-102">Details</span></span>|<span data-ttu-id="ba897-103">.NET Framework 4.5 以降では、OData URL の Replace メソッドは既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="ba897-103">Beginning in the .NET Framework 4.5, the Replace method in OData URLs is disabled by default.</span></span> <span data-ttu-id="ba897-104">OData Replace が無効のとき (既定)、replace 関数を含むユーザー要求 (一般的ではない) は失敗します。</span><span class="sxs-lookup"><span data-stu-id="ba897-104">When OData Replace is disabled (now by default), any user requests including replace functions (which are uncommon) will fail.</span></span>|
|<span data-ttu-id="ba897-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="ba897-105">Suggestion</span></span>|<span data-ttu-id="ba897-106">Replace メソッドが必要な場合 (一般的ではない)、構成設定 (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>) によって再び有効にできます。</span><span class="sxs-lookup"><span data-stu-id="ba897-106">If the replace method is required (which is uncommon), it can be re-enabled through a config settings (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>).</span></span> <span data-ttu-id="ba897-107">ただし、有効になった replace メソッドはセキュリティの脆弱性を開くことがあり、慎重にレビューしてから使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba897-107">However, an enabled replace method can open security vulnerabilities and should only be used after careful review.</span></span>|
|<span data-ttu-id="ba897-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="ba897-108">Scope</span></span>|<span data-ttu-id="ba897-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="ba897-109">Edge</span></span>|
|<span data-ttu-id="ba897-110">Version</span><span class="sxs-lookup"><span data-stu-id="ba897-110">Version</span></span>|<span data-ttu-id="ba897-111">4.5</span><span class="sxs-lookup"><span data-stu-id="ba897-111">4.5</span></span>|
|<span data-ttu-id="ba897-112">型</span><span class="sxs-lookup"><span data-stu-id="ba897-112">Type</span></span>|<span data-ttu-id="ba897-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="ba897-113">Runtime</span></span>|
|<span data-ttu-id="ba897-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="ba897-114">Affected APIs</span></span>|<ul><li><xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
