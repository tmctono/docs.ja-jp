---
ms.openlocfilehash: 4a22d78f2308aab544d7a7d2e4d05ddc1ad5457d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617237"
---
### <a name="xml-schema-validation-is-stricter"></a><span data-ttu-id="aeb0f-101">XML スキーマ検証がより厳格になりました</span><span class="sxs-lookup"><span data-stu-id="aeb0f-101">XML schema validation is stricter</span></span>

#### <a name="details"></a><span data-ttu-id="aeb0f-102">説明</span><span class="sxs-lookup"><span data-stu-id="aeb0f-102">Details</span></span>

<span data-ttu-id="aeb0f-103">.NET Framework 4.5 では、XML スキーマ検証が厳格化されました。</span><span class="sxs-lookup"><span data-stu-id="aeb0f-103">In the .NET Framework 4.5, XML schema validation is more strict.</span></span> <span data-ttu-id="aeb0f-104">xsd:anyURI を使用して mailto プロトコルなどの URI を検証したときに、URI にスペースが入っていると検証は失敗します。</span><span class="sxs-lookup"><span data-stu-id="aeb0f-104">If you use xsd:anyURI to validate a URI such as a mailto protocol, validation fails if there are spaces in the URI.</span></span> <span data-ttu-id="aeb0f-105">.NET Framework の以前のバージョンでは、検証は成功していました。</span><span class="sxs-lookup"><span data-stu-id="aeb0f-105">In previous versions of the .NET Framework, validation succeeded.</span></span> <span data-ttu-id="aeb0f-106">この変更は、.NET Framework 4.5 を対象とするアプリケーションにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="aeb0f-106">The change affects only applications that target the .NET Framework 4.5.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="aeb0f-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="aeb0f-107">Suggestion</span></span>

<span data-ttu-id="aeb0f-108">より緩やかな .NET Framework 4.0 の検証が必要な場合、検証アプリケーションはバージョン 4.0 の .NET Framework をターゲットにできます。</span><span class="sxs-lookup"><span data-stu-id="aeb0f-108">If looser .NET Framework 4.0 validation is needed, the validating application can target version 4.0 of the .NET Framework.</span></span> <span data-ttu-id="aeb0f-109">もう一度 .NET Framework 4.5 をターゲットにする場合は、無効な URI (およびスペース) が anyURI データ型の属性値として予期されないように、コード レビューを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeb0f-109">When retargeting to .NET Framework 4.5, however, code review should be done to be sure that invalid URIs (with spaces) are not expected as attribute values with the anyURI data type.</span></span>

| <span data-ttu-id="aeb0f-110">名前</span><span class="sxs-lookup"><span data-stu-id="aeb0f-110">Name</span></span>    | <span data-ttu-id="aeb0f-111">[値]</span><span class="sxs-lookup"><span data-stu-id="aeb0f-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="aeb0f-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="aeb0f-112">Scope</span></span>   | <span data-ttu-id="aeb0f-113">マイナー</span><span class="sxs-lookup"><span data-stu-id="aeb0f-113">Minor</span></span>       |
| <span data-ttu-id="aeb0f-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="aeb0f-114">Version</span></span> | <span data-ttu-id="aeb0f-115">4.5</span><span class="sxs-lookup"><span data-stu-id="aeb0f-115">4.5</span></span>         |
| <span data-ttu-id="aeb0f-116">種類</span><span class="sxs-lookup"><span data-stu-id="aeb0f-116">Type</span></span>    | <span data-ttu-id="aeb0f-117">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="aeb0f-117">Retargeting</span></span> |
