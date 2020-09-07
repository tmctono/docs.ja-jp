---
ms.openlocfilehash: f61e5670334f4d3674fd0b008d1a476b14c7ba4e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497111"
---
### <a name="calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a><span data-ttu-id="fb28a-101">インデクサー プロパティに対して Attribute.GetCustomAttributes を呼び出しても、インデックスの型によって、あいまいさを解決できる場合、AmbiguousMatchException はスローされなくなった</span><span class="sxs-lookup"><span data-stu-id="fb28a-101">Calling Attribute.GetCustomAttributes on an indexer property no longer throws AmbiguousMatchException if the ambiguity can be resolved by index's type</span></span>

#### <a name="details"></a><span data-ttu-id="fb28a-102">説明</span><span class="sxs-lookup"><span data-stu-id="fb28a-102">Details</span></span>

<span data-ttu-id="fb28a-103">.NET Framework 4.6 より以前には、インデックスの型のみが別のプロパティと異なるインデクサ― プロパティに対して <code>GetCustomAttribute(s)</code> を呼び出すと、<xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName> になりました。</span><span class="sxs-lookup"><span data-stu-id="fb28a-103">Prior to the .NET Framework 4.6, calling <code>GetCustomAttribute(s)</code> on an indexer property which differed from another property only by the type of the index would result in an <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName>.</span></span> <span data-ttu-id="fb28a-104">.NET Framework 4.6 からは、プロパティの属性が正しく返されます。</span><span class="sxs-lookup"><span data-stu-id="fb28a-104">Beginning in the .NET Framework 4.6, the property's attributes will be correctly returned.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fb28a-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="fb28a-105">Suggestion</span></span>

<span data-ttu-id="fb28a-106">GetCustomAttribute(s) が、より頻繁に機能するようになったことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fb28a-106">Be aware that GetCustomAttribute(s) will work more frequently now.</span></span> <span data-ttu-id="fb28a-107">アプリが <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName> に依存していた場合は、代わりにリフレクションを使用して、複数のインデクサーを明示的に検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb28a-107">If an app was previously relying on the <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName>, reflection should now be used to explicitly look for multiple indexers, instead.</span></span>

| <span data-ttu-id="fb28a-108">名前</span><span class="sxs-lookup"><span data-stu-id="fb28a-108">Name</span></span>    | <span data-ttu-id="fb28a-109">値</span><span class="sxs-lookup"><span data-stu-id="fb28a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fb28a-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="fb28a-110">Scope</span></span>   |<span data-ttu-id="fb28a-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="fb28a-111">Edge</span></span>|
|<span data-ttu-id="fb28a-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="fb28a-112">Version</span></span>|<span data-ttu-id="fb28a-113">4.6</span><span class="sxs-lookup"><span data-stu-id="fb28a-113">4.6</span></span>|
|<span data-ttu-id="fb28a-114">種類</span><span class="sxs-lookup"><span data-stu-id="fb28a-114">Type</span></span>|<span data-ttu-id="fb28a-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="fb28a-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="fb28a-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="fb28a-116">Affected APIs</span></span>

- <xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)`
- `M:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute``1(System.Reflection.MemberInfo)``
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute``1(System.Reflection.MemberInfo,System.Boolean)``
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes``1(System.Reflection.MemberInfo)``
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes``1(System.Reflection.MemberInfo,System.Boolean)``

-->
