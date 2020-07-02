---
ms.openlocfilehash: 7d3568fef933758c40e47cefa86c24d31d4119fc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620132"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="15866-101">HttpRequest.ContentEncoding プロパティで UTF7 が禁止される</span><span class="sxs-lookup"><span data-stu-id="15866-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

#### <a name="details"></a><span data-ttu-id="15866-102">説明</span><span class="sxs-lookup"><span data-stu-id="15866-102">Details</span></span>

<span data-ttu-id="15866-103">.NET Framework 4.5 以降では、<xref:System.Web.HttpRequest?displayProperty=fullName> の本文では UTF-7 エンコードが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="15866-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=fullName>s' bodies.</span></span> <span data-ttu-id="15866-104">UTF-7 データの受信を必要とするアプリケーションのデータが、正しくデコードされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="15866-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="15866-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="15866-105">Suggestion</span></span>

<span data-ttu-id="15866-106">理想的には、<xref:System.Web.HttpRequest?displayProperty=fullName> で UTF-7 エンコードを使用しないようにアプリケーションを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15866-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=fullName>s.</span></span> <span data-ttu-id="15866-107">または、 [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) 要素の <code>aspnet:AllowUtf7RequestContentEncoding</code> 属性を使用して、レガシ動作に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="15866-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>

| <span data-ttu-id="15866-108">名前</span><span class="sxs-lookup"><span data-stu-id="15866-108">Name</span></span>    | <span data-ttu-id="15866-109">[値]</span><span class="sxs-lookup"><span data-stu-id="15866-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="15866-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="15866-110">Scope</span></span>   |<span data-ttu-id="15866-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="15866-111">Edge</span></span>|
|<span data-ttu-id="15866-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="15866-112">Version</span></span>|<span data-ttu-id="15866-113">4.5</span><span class="sxs-lookup"><span data-stu-id="15866-113">4.5</span></span>|
|<span data-ttu-id="15866-114">種類</span><span class="sxs-lookup"><span data-stu-id="15866-114">Type</span></span>|<span data-ttu-id="15866-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="15866-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="15866-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="15866-116">Affected APIs</span></span>

-<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
