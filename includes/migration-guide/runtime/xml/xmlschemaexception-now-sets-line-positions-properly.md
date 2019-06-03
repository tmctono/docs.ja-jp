---
ms.openlocfilehash: a5b3e325c13d2f56532ebc6ebb5c259d565a4952
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379638"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a><span data-ttu-id="dde46-101">XmlSchemaException で行位置が正しく設定されるようになった</span><span class="sxs-lookup"><span data-stu-id="dde46-101">XmlSchemaException now sets line positions properly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="dde46-102">説明</span><span class="sxs-lookup"><span data-stu-id="dde46-102">Details</span></span>|<span data-ttu-id="dde46-103"><xref:System.Xml.Linq.LoadOptions.SetLineInfo> 値が Load メソッドに渡されたときに検証エラーが発生すると、<xref:System.Xml.Schema.XmlSchemaException.LineNumber> プロパティと <xref:System.Xml.Schema.XmlSchemaException.LinePosition> プロパティに行情報が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="dde46-103">If the <xref:System.Xml.Linq.LoadOptions.SetLineInfo> value is passed to the Load method and a validation error occurs, the <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> properties now contain line information.</span></span>|
|<span data-ttu-id="dde46-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="dde46-104">Suggestion</span></span>|<span data-ttu-id="dde46-105">XML の読み込み中に SetLineInfo が使用されるとき、<xref:System.Xml.Schema.XmlSchemaException.LineNumber> と <xref:System.Xml.Schema.XmlSchemaException.LinePosition> は正しく設定されるようになったので、これらのプロパティが設定されないことを想定している例外処理コードは、更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dde46-105">Exception-handling code that assumes <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> will not be set should be updated since these properties will now be set properly when SetLineInfo is used while loading XML.</span></span>|
|<span data-ttu-id="dde46-106">スコープ</span><span class="sxs-lookup"><span data-stu-id="dde46-106">Scope</span></span>|<span data-ttu-id="dde46-107">エッジ</span><span class="sxs-lookup"><span data-stu-id="dde46-107">Edge</span></span>|
|<span data-ttu-id="dde46-108">Version</span><span class="sxs-lookup"><span data-stu-id="dde46-108">Version</span></span>|<span data-ttu-id="dde46-109">4.5</span><span class="sxs-lookup"><span data-stu-id="dde46-109">4.5</span></span>|
|<span data-ttu-id="dde46-110">型</span><span class="sxs-lookup"><span data-stu-id="dde46-110">Type</span></span>|<span data-ttu-id="dde46-111">ランタイム</span><span class="sxs-lookup"><span data-stu-id="dde46-111">Runtime</span></span>|
|<span data-ttu-id="dde46-112">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="dde46-112">Affected APIs</span></span>|<ul><li><xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
