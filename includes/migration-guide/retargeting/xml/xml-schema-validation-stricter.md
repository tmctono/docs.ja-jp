---
ms.openlocfilehash: ef0381dc2ce4373b2a62e8ebefa44152059ca332
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234697"
---
### <a name="xml-schema-validation-is-stricter"></a><span data-ttu-id="ae742-101">XML スキーマ検証がより厳格になりました</span><span class="sxs-lookup"><span data-stu-id="ae742-101">XML schema validation is stricter</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ae742-102">説明</span><span class="sxs-lookup"><span data-stu-id="ae742-102">Details</span></span>|<span data-ttu-id="ae742-103">.NET Framework 4.5 では、XML スキーマ検証が厳格化されました。</span><span class="sxs-lookup"><span data-stu-id="ae742-103">In the .NET Framework 4.5, XML schema validation is more strict.</span></span> <span data-ttu-id="ae742-104">xsd:anyURI を使用して mailto プロトコルなどの URI を検証したときに、URI にスペースが入っていると検証は失敗します。</span><span class="sxs-lookup"><span data-stu-id="ae742-104">If you use xsd:anyURI to validate a URI such as a mailto protocol, validation fails if there are spaces in the URI.</span></span> <span data-ttu-id="ae742-105">.NET Framework の以前のバージョンでは、検証は成功していました。</span><span class="sxs-lookup"><span data-stu-id="ae742-105">In previous versions of the .NET Framework, validation succeeded.</span></span> <span data-ttu-id="ae742-106">この変更は、.NET Framework 4.5 を対象とするアプリケーションにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="ae742-106">The change affects only applications that target the .NET Framework 4.5.</span></span>|
|<span data-ttu-id="ae742-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="ae742-107">Suggestion</span></span>|<span data-ttu-id="ae742-108">より緩やかな .NET Framework 4.0 の検証が必要な場合、検証アプリケーションはバージョン 4.0 の .NET Framework をターゲットにできます。</span><span class="sxs-lookup"><span data-stu-id="ae742-108">If looser .NET Framework 4.0 validation is needed, the validating application can target version 4.0 of the .NET Framework.</span></span> <span data-ttu-id="ae742-109">もう一度 .NET Framework 4.5 をターゲットにする場合は、無効な URI (およびスペース) が anyURI データ型の属性値として予期されないように、コード レビューを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae742-109">When retargeting to .NET Framework 4.5, however, code review should be done to be sure that invalid URIs (with spaces) are not expected as attribute values with the anyURI data type.</span></span>|
|<span data-ttu-id="ae742-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="ae742-110">Scope</span></span>|<span data-ttu-id="ae742-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="ae742-111">Minor</span></span>|
|<span data-ttu-id="ae742-112">Version</span><span class="sxs-lookup"><span data-stu-id="ae742-112">Version</span></span>|<span data-ttu-id="ae742-113">4.5</span><span class="sxs-lookup"><span data-stu-id="ae742-113">4.5</span></span>|
|<span data-ttu-id="ae742-114">型</span><span class="sxs-lookup"><span data-stu-id="ae742-114">Type</span></span>|<span data-ttu-id="ae742-115">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="ae742-115">Retargeting</span></span>|
