---
ms.openlocfilehash: cf34c5df1badcfd86d8a07bafdf1b759234712e0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496569"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="e1d16-101">HttpRequest.ContentEncoding プロパティで UTF7 が禁止される</span><span class="sxs-lookup"><span data-stu-id="e1d16-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

#### <a name="details"></a><span data-ttu-id="e1d16-102">説明</span><span class="sxs-lookup"><span data-stu-id="e1d16-102">Details</span></span>

<span data-ttu-id="e1d16-103">.NET Framework 4.5 以降では、<xref:System.Web.HttpRequest?displayProperty=fullName> の本文では UTF-7 エンコードが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="e1d16-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=fullName>s' bodies.</span></span> <span data-ttu-id="e1d16-104">UTF-7 データの受信を必要とするアプリケーションのデータが、正しくデコードされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e1d16-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e1d16-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="e1d16-105">Suggestion</span></span>

<span data-ttu-id="e1d16-106">理想的には、<xref:System.Web.HttpRequest?displayProperty=fullName> で UTF-7 エンコードを使用しないようにアプリケーションを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1d16-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=fullName>s.</span></span> <span data-ttu-id="e1d16-107">または、 [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) 要素の <code>aspnet:AllowUtf7RequestContentEncoding</code> 属性を使用して、レガシ動作に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="e1d16-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>

| <span data-ttu-id="e1d16-108">名前</span><span class="sxs-lookup"><span data-stu-id="e1d16-108">Name</span></span>    | <span data-ttu-id="e1d16-109">[値]</span><span class="sxs-lookup"><span data-stu-id="e1d16-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e1d16-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="e1d16-110">Scope</span></span>   |<span data-ttu-id="e1d16-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="e1d16-111">Edge</span></span>|
|<span data-ttu-id="e1d16-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="e1d16-112">Version</span></span>|<span data-ttu-id="e1d16-113">4.5</span><span class="sxs-lookup"><span data-stu-id="e1d16-113">4.5</span></span>|
|<span data-ttu-id="e1d16-114">種類</span><span class="sxs-lookup"><span data-stu-id="e1d16-114">Type</span></span>|<span data-ttu-id="e1d16-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="e1d16-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="e1d16-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e1d16-116">Affected APIs</span></span>

- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.ContentEncoding`

-->
