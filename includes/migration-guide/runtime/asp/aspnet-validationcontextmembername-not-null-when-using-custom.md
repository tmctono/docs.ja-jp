---
ms.openlocfilehash: 7002c74594993ac6bf28643ef3271da356190c66
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621963"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a><span data-ttu-id="e9bd6-101">ASP.NET カスタムの DataAnnotations.ValidationAttribute を使用すると、ValidationContext.MemberName が NULL にならない</span><span class="sxs-lookup"><span data-stu-id="e9bd6-101">ASP.NET ValidationContext.MemberName is not NULL when using custom DataAnnotations.ValidationAttribute</span></span>

#### <a name="details"></a><span data-ttu-id="e9bd6-102">説明</span><span class="sxs-lookup"><span data-stu-id="e9bd6-102">Details</span></span>

<span data-ttu-id="e9bd6-103">.NET Framework 4.7.2 以前のバージョンでは、カスタムの <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> を使用すると、<xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> プロパティで `null` が返されます。</span><span class="sxs-lookup"><span data-stu-id="e9bd6-103">In .NET Framework 4.7.2 and earlier versions, when using a custom <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>, the <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> property returns `null`.</span></span> <span data-ttu-id="e9bd6-104">October 2019 Update より前の .NET Framework 4.8 バージョンでは、メンバー名が返されます。</span><span class="sxs-lookup"><span data-stu-id="e9bd6-104">In .NET Framework 4.8 version prior to the October 2019 update, it returns the member name.</span></span> <span data-ttu-id="e9bd6-105">.NET Framework 4.8 の [.NET Framework October 2019 Preview の品質ロールアップ](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/)以降、既定では `null` が返されますが、代わりにメンバー名を返すように設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9bd6-105">Starting with [.NET Framework October 2019 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) for .NET Framework 4.8, it returns `null` by default, but you can opt in to return the member name instead.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e9bd6-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="e9bd6-106">Suggestion</span></span>

<span data-ttu-id="e9bd6-107">.NET Framework 4.8 以降のバージョン用の [.NET Framework October 2019 Preview の品質ロールアップ](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/)で、メンバー名を返すプロパティに対して次の設定を *web.config* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="e9bd6-107">Add the following setting to your *web.config* file for the property to return the member name in [.NET Framework October 2019 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) for .NET Framework 4.8 and later versions:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="e9bd6-108">October 2019 Update より前の .NET Framework 4.8 バージョンでは、これを *web.config* ファイルに追加すると、以前の動作が復元され、プロパティで `null` が返されます。</span><span class="sxs-lookup"><span data-stu-id="e9bd6-108">In .NET Framework 4.8 version prior to the October 2019 update,  adding this to your *web.config* file restores the previous behavior and the property returns `null`.</span></span>

| <span data-ttu-id="e9bd6-109">名前</span><span class="sxs-lookup"><span data-stu-id="e9bd6-109">Name</span></span>    | <span data-ttu-id="e9bd6-110">[値]</span><span class="sxs-lookup"><span data-stu-id="e9bd6-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e9bd6-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="e9bd6-111">Scope</span></span>   |<span data-ttu-id="e9bd6-112">不明</span><span class="sxs-lookup"><span data-stu-id="e9bd6-112">Unknown</span></span>|
|<span data-ttu-id="e9bd6-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="e9bd6-113">Version</span></span>|<span data-ttu-id="e9bd6-114">4.8</span><span class="sxs-lookup"><span data-stu-id="e9bd6-114">4.8</span></span>|
|<span data-ttu-id="e9bd6-115">種類</span><span class="sxs-lookup"><span data-stu-id="e9bd6-115">Type</span></span>|<span data-ttu-id="e9bd6-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="e9bd6-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e9bd6-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e9bd6-117">Affected APIs</span></span>

-<xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType></li></ul>|
