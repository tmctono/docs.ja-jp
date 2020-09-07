---
ms.openlocfilehash: fccf349517133245ec85ae3c25cedbfb27a7dd8b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497386"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a><span data-ttu-id="5d8dd-101">OData URL の Replace メソッドが既定で無効になる</span><span class="sxs-lookup"><span data-stu-id="5d8dd-101">The Replace method in OData URLs is disabled by default</span></span>

#### <a name="details"></a><span data-ttu-id="5d8dd-102">説明</span><span class="sxs-lookup"><span data-stu-id="5d8dd-102">Details</span></span>

<span data-ttu-id="5d8dd-103">.NET Framework 4.5 以降では、OData URL の Replace メソッドは既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="5d8dd-103">Beginning in the .NET Framework 4.5, the Replace method in OData URLs is disabled by default.</span></span> <span data-ttu-id="5d8dd-104">OData Replace が無効のとき (既定)、replace 関数を含むユーザー要求 (一般的ではない) は失敗します。</span><span class="sxs-lookup"><span data-stu-id="5d8dd-104">When OData Replace is disabled (now by default), any user requests including replace functions (which are uncommon) will fail.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5d8dd-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="5d8dd-105">Suggestion</span></span>

<span data-ttu-id="5d8dd-106">Replace メソッドが必要な場合 (一般的ではない)、構成設定 (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>) によって再び有効にできます。</span><span class="sxs-lookup"><span data-stu-id="5d8dd-106">If the replace method is required (which is uncommon), it can be re-enabled through a config settings (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>).</span></span> <span data-ttu-id="5d8dd-107">ただし、有効になった replace メソッドはセキュリティの脆弱性を開くことがあり、慎重にレビューしてから使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d8dd-107">However, an enabled replace method can open security vulnerabilities and should only be used after careful review.</span></span>

| <span data-ttu-id="5d8dd-108">名前</span><span class="sxs-lookup"><span data-stu-id="5d8dd-108">Name</span></span>    | <span data-ttu-id="5d8dd-109">[値]</span><span class="sxs-lookup"><span data-stu-id="5d8dd-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5d8dd-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="5d8dd-110">Scope</span></span>   |<span data-ttu-id="5d8dd-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="5d8dd-111">Edge</span></span>|
|<span data-ttu-id="5d8dd-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="5d8dd-112">Version</span></span>|<span data-ttu-id="5d8dd-113">4.5</span><span class="sxs-lookup"><span data-stu-id="5d8dd-113">4.5</span></span>|
|<span data-ttu-id="5d8dd-114">種類</span><span class="sxs-lookup"><span data-stu-id="5d8dd-114">Type</span></span>|<span data-ttu-id="5d8dd-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="5d8dd-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="5d8dd-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="5d8dd-116">Affected APIs</span></span>

- <xref:System.Data.Services.DataService%601?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``T:System.Data.Services.DataService`1``

-->
