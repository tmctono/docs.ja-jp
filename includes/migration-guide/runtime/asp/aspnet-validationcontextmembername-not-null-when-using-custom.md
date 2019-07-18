---
ms.openlocfilehash: df13f6938ebaf8e96bb2825c1495044621f1c31b
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802626"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a><span data-ttu-id="fc9d3-101">ASP.NET カスタムの DataAnnotations.ValidationAttribute を使用すると、ValidationContext.MemberName が NULL にならない</span><span class="sxs-lookup"><span data-stu-id="fc9d3-101">ASP.NET ValidationContext.MemberName is not NULL when using custom DataAnnotations.ValidationAttribute</span></span>

|   |   |
|---|---|
|<span data-ttu-id="fc9d3-102">説明</span><span class="sxs-lookup"><span data-stu-id="fc9d3-102">Details</span></span>|<span data-ttu-id="fc9d3-103">.NET Framework 4.7.2 以前のバージョンでは、カスタムの <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> を使用すると、<xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> プロパティで <code>null</code> が返されます。</span><span class="sxs-lookup"><span data-stu-id="fc9d3-103">In .NET Framework 4.7.2 and earlier versions, when using a custom <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>, the <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> property returns <code>null</code>.</span></span>  <span data-ttu-id="fc9d3-104">.NET Framework 4.8 では、メンバー名が返されます。</span><span class="sxs-lookup"><span data-stu-id="fc9d3-104">In .NET Framework 4.8, it returns the member name.</span></span>|
|<span data-ttu-id="fc9d3-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="fc9d3-105">Suggestion</span></span>|<span data-ttu-id="fc9d3-106"><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> プロパティの既定の動作は変わりません。</span><span class="sxs-lookup"><span data-stu-id="fc9d3-106">The default behavior of the <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> property remains the same.</span></span>  <span data-ttu-id="fc9d3-107"><code>ValidationContext.MemberName</code> プロパティから有効な値を取得するには、アプリ構成ファイルに次の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="fc9d3-107">To retrieve a valid value from the <code>ValidationContext.MemberName</code> property, add the following setting to your app config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="fc9d3-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="fc9d3-108">Scope</span></span>|<span data-ttu-id="fc9d3-109">不明</span><span class="sxs-lookup"><span data-stu-id="fc9d3-109">Unknown</span></span>|
|<span data-ttu-id="fc9d3-110">Version</span><span class="sxs-lookup"><span data-stu-id="fc9d3-110">Version</span></span>|<span data-ttu-id="fc9d3-111">4.8</span><span class="sxs-lookup"><span data-stu-id="fc9d3-111">4.8</span></span>|
|<span data-ttu-id="fc9d3-112">型</span><span class="sxs-lookup"><span data-stu-id="fc9d3-112">Type</span></span>|<span data-ttu-id="fc9d3-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="fc9d3-113">Runtime</span></span>|
|<span data-ttu-id="fc9d3-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="fc9d3-114">Affected APIs</span></span>|<ul><li><xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|

