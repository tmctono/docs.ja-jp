---
ms.openlocfilehash: 5c8ea3565fbe599dd53a71ba8bd339704f7d7f8a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497791"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a><span data-ttu-id="c76f4-101">SignedXml と EncryptedXml の互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="c76f4-101">SignedXml and EncryptedXml Breaking Changes</span></span>

#### <a name="details"></a><span data-ttu-id="c76f4-102">説明</span><span class="sxs-lookup"><span data-stu-id="c76f4-102">Details</span></span>

<span data-ttu-id="c76f4-103">.NET Framework 4.6.2 では、<xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> および <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> のセキュリティ修正プログラムにより、実行時の動作が変わります。</span><span class="sxs-lookup"><span data-stu-id="c76f4-103">In .NET Framework 4.6.2, Security fixes in <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> and <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> lead to different run-time behaviors.</span></span> <span data-ttu-id="c76f4-104">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c76f4-104">For example,</span></span><ul><li><span data-ttu-id="c76f4-105">ドキュメントに <code>id</code> 属性が同じ値の複数の要素があり、署名でそれらの要素の 1 つが署名のルートとして指定されている場合、ドキュメントは無効と見なされるようになります。</span><span class="sxs-lookup"><span data-stu-id="c76f4-105">If a document has multiple elements with the same <code>id</code> attribute and a signature targets one of those elements as the root of the signature, the document will now be considered invalid.</span></span></li><li><span data-ttu-id="c76f4-106">参照で非正規 XPath 変換アルゴリズムを使っているドキュメントは、無効と見なされるようになります。</span><span class="sxs-lookup"><span data-stu-id="c76f4-106">Documents using non-canonical XPath transform algorithms in references are now considered invalid.</span></span></li><li><span data-ttu-id="c76f4-107">参照で非正規 XSLT 変換アルゴリズムを使っているドキュメントは、無効と見なされるようになります。</span><span class="sxs-lookup"><span data-stu-id="c76f4-107">Documents using non-canonical XSLT transform algorithms in references are now consider invalid.</span></span></li><li><span data-ttu-id="c76f4-108">外部リソースのデタッチされた署名を利用しているプログラムは、利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c76f4-108">Any program making use of external resource detached signatures will be unable to do so.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="c76f4-109">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="c76f4-109">Suggestion</span></span>

<span data-ttu-id="c76f4-110">ドキュメントの受信者が処理できない可能性があるため、開発者は <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> と <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> の使用、および <xref:System.Security.Cryptography.Xml.Transform> の派生型を確認することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c76f4-110">Developers might want to review the usage of <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> and <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, as well as types derived from <xref:System.Security.Cryptography.Xml.Transform> since a document receiver may not be able to process it.</span></span>

| <span data-ttu-id="c76f4-111">名前</span><span class="sxs-lookup"><span data-stu-id="c76f4-111">Name</span></span>    | <span data-ttu-id="c76f4-112">値</span><span class="sxs-lookup"><span data-stu-id="c76f4-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c76f4-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="c76f4-113">Scope</span></span>   |<span data-ttu-id="c76f4-114">マイナー</span><span class="sxs-lookup"><span data-stu-id="c76f4-114">Minor</span></span>|
|<span data-ttu-id="c76f4-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="c76f4-115">Version</span></span>|<span data-ttu-id="c76f4-116">4.6.2</span><span class="sxs-lookup"><span data-stu-id="c76f4-116">4.6.2</span></span>|
|<span data-ttu-id="c76f4-117">種類</span><span class="sxs-lookup"><span data-stu-id="c76f4-117">Type</span></span>|<span data-ttu-id="c76f4-118">ランタイム</span><span class="sxs-lookup"><span data-stu-id="c76f4-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c76f4-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c76f4-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.Xml.Transform`
- `T:System.Security.Cryptography.Xml.XmlDsigXPathTransform`
- `T:System.Security.Cryptography.Xml.XmlDsigXsltTransform`

-->
