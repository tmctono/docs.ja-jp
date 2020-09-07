---
ms.openlocfilehash: d33d75b4c2d9bc18844f66f1fcca1e2efc6f1eee
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496501"
---
### <a name="xslt-style-sheet-exception-message-changed"></a><span data-ttu-id="56ae0-101">XSLT スタイル シートの例外メッセージが変更された</span><span class="sxs-lookup"><span data-stu-id="56ae0-101">XSLT style sheet exception message changed</span></span>

#### <a name="details"></a><span data-ttu-id="56ae0-102">説明</span><span class="sxs-lookup"><span data-stu-id="56ae0-102">Details</span></span>

<span data-ttu-id="56ae0-103">.NET Framework 4.5 では、XSLT ファイルが複雑すぎるときのエラー メッセージのテキストが &quot;スタイル シートが複雑すぎます&quot; になります。以前のバージョンのエラー メッセージは &quot;XSLT コンパイル エラー&quot; でした。エラー メッセージのテキストに依存するアプリケーション コードは機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="56ae0-103">In the .NET Framework 4.5, the text of the error message when an XSLT file is too complex is &quot;The style sheet is too complex.&quot; In previous versions, the error message was &quot;XSLT compile error.&quot; Application code that depends on the text of the error message will no longer work.</span></span> <span data-ttu-id="56ae0-104">ただし、例外の種類は同じなので、この変更による実質的な影響はありません。</span><span class="sxs-lookup"><span data-stu-id="56ae0-104">However, the exception types remain the same, so this change should have no real impact.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="56ae0-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="56ae0-105">Suggestion</span></span>

<span data-ttu-id="56ae0-106">このエラー条件からの例外メッセージに依存しているアプリケーション コードを、新しいメッセージを予期するように更新するか、(さらに望ましくは) 変更されていない例外の種類 (<xref:System.Xml.Xsl.XsltException?displayProperty=fullName>) のみに依存するようにコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="56ae0-106">Update any app code depending on the exception message from this error condition to expect the new message, or (even better) update the code to depend only on the exception type (<xref:System.Xml.Xsl.XsltException?displayProperty=fullName>), which has not changed.</span></span>

| <span data-ttu-id="56ae0-107">名前</span><span class="sxs-lookup"><span data-stu-id="56ae0-107">Name</span></span>    | <span data-ttu-id="56ae0-108">[値]</span><span class="sxs-lookup"><span data-stu-id="56ae0-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="56ae0-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="56ae0-109">Scope</span></span>   |<span data-ttu-id="56ae0-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="56ae0-110">Edge</span></span>|
|<span data-ttu-id="56ae0-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="56ae0-111">Version</span></span>|<span data-ttu-id="56ae0-112">4.5</span><span class="sxs-lookup"><span data-stu-id="56ae0-112">4.5</span></span>|
|<span data-ttu-id="56ae0-113">種類</span><span class="sxs-lookup"><span data-stu-id="56ae0-113">Type</span></span>|<span data-ttu-id="56ae0-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="56ae0-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="56ae0-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="56ae0-115">Affected APIs</span></span>

- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.String)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)`

-->
