---
ms.openlocfilehash: c3e39e49747be709977d7fba3c39b59f5575c40d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620505"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a><span data-ttu-id="75bc6-101">XmlSchemaException で行位置が正しく設定されるようになった</span><span class="sxs-lookup"><span data-stu-id="75bc6-101">XmlSchemaException now sets line positions properly</span></span>

#### <a name="details"></a><span data-ttu-id="75bc6-102">説明</span><span class="sxs-lookup"><span data-stu-id="75bc6-102">Details</span></span>

<span data-ttu-id="75bc6-103"><xref:System.Xml.Linq.LoadOptions.SetLineInfo> 値が Load メソッドに渡されたときに検証エラーが発生すると、<xref:System.Xml.Schema.XmlSchemaException.LineNumber> プロパティと <xref:System.Xml.Schema.XmlSchemaException.LinePosition> プロパティに行情報が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="75bc6-103">If the <xref:System.Xml.Linq.LoadOptions.SetLineInfo> value is passed to the Load method and a validation error occurs, the <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> properties now contain line information.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="75bc6-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="75bc6-104">Suggestion</span></span>

<span data-ttu-id="75bc6-105">XML の読み込み中に SetLineInfo が使用されるとき、<xref:System.Xml.Schema.XmlSchemaException.LineNumber> と <xref:System.Xml.Schema.XmlSchemaException.LinePosition> は正しく設定されるようになったので、これらのプロパティが設定されないことを想定している例外処理コードは、更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75bc6-105">Exception-handling code that assumes <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> will not be set should be updated since these properties will now be set properly when SetLineInfo is used while loading XML.</span></span>

| <span data-ttu-id="75bc6-106">名前</span><span class="sxs-lookup"><span data-stu-id="75bc6-106">Name</span></span>    | <span data-ttu-id="75bc6-107">[値]</span><span class="sxs-lookup"><span data-stu-id="75bc6-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="75bc6-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="75bc6-108">Scope</span></span>   |<span data-ttu-id="75bc6-109">エッジ</span><span class="sxs-lookup"><span data-stu-id="75bc6-109">Edge</span></span>|
|<span data-ttu-id="75bc6-110">バージョン</span><span class="sxs-lookup"><span data-stu-id="75bc6-110">Version</span></span>|<span data-ttu-id="75bc6-111">4.5</span><span class="sxs-lookup"><span data-stu-id="75bc6-111">4.5</span></span>|
|<span data-ttu-id="75bc6-112">種類</span><span class="sxs-lookup"><span data-stu-id="75bc6-112">Type</span></span>|<span data-ttu-id="75bc6-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="75bc6-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="75bc6-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="75bc6-114">Affected APIs</span></span>

-<xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
