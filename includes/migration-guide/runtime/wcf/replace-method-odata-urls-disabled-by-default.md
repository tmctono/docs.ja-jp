---
ms.openlocfilehash: b2fcacdb02c411c4dcb12051bf0c6759faccdea2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620390"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a><span data-ttu-id="17c3c-101">OData URL の Replace メソッドが既定で無効になる</span><span class="sxs-lookup"><span data-stu-id="17c3c-101">The Replace method in OData URLs is disabled by default</span></span>

#### <a name="details"></a><span data-ttu-id="17c3c-102">説明</span><span class="sxs-lookup"><span data-stu-id="17c3c-102">Details</span></span>

<span data-ttu-id="17c3c-103">.NET Framework 4.5 以降では、OData URL の Replace メソッドは既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="17c3c-103">Beginning in the .NET Framework 4.5, the Replace method in OData URLs is disabled by default.</span></span> <span data-ttu-id="17c3c-104">OData Replace が無効のとき (既定)、replace 関数を含むユーザー要求 (一般的ではない) は失敗します。</span><span class="sxs-lookup"><span data-stu-id="17c3c-104">When OData Replace is disabled (now by default), any user requests including replace functions (which are uncommon) will fail.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="17c3c-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="17c3c-105">Suggestion</span></span>

<span data-ttu-id="17c3c-106">Replace メソッドが必要な場合 (一般的ではない)、構成設定 (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>) によって再び有効にできます。</span><span class="sxs-lookup"><span data-stu-id="17c3c-106">If the replace method is required (which is uncommon), it can be re-enabled through a config settings (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>).</span></span> <span data-ttu-id="17c3c-107">ただし、有効になった replace メソッドはセキュリティの脆弱性を開くことがあり、慎重にレビューしてから使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17c3c-107">However, an enabled replace method can open security vulnerabilities and should only be used after careful review.</span></span>

| <span data-ttu-id="17c3c-108">名前</span><span class="sxs-lookup"><span data-stu-id="17c3c-108">Name</span></span>    | <span data-ttu-id="17c3c-109">[値]</span><span class="sxs-lookup"><span data-stu-id="17c3c-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="17c3c-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="17c3c-110">Scope</span></span>   |<span data-ttu-id="17c3c-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="17c3c-111">Edge</span></span>|
|<span data-ttu-id="17c3c-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="17c3c-112">Version</span></span>|<span data-ttu-id="17c3c-113">4.5</span><span class="sxs-lookup"><span data-stu-id="17c3c-113">4.5</span></span>|
|<span data-ttu-id="17c3c-114">種類</span><span class="sxs-lookup"><span data-stu-id="17c3c-114">Type</span></span>|<span data-ttu-id="17c3c-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="17c3c-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="17c3c-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="17c3c-116">Affected APIs</span></span>

-<xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
