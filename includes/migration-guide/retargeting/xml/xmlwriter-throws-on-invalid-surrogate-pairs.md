---
ms.openlocfilehash: f87b70708398226516ab5eac32c24a9fc2c1106b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615737"
---
### <a name="xmlwriter-throws-on-invalid-surrogate-pairs"></a><span data-ttu-id="5be8f-101">無効なサロゲート ペアで XmlWriter がスローされる</span><span class="sxs-lookup"><span data-stu-id="5be8f-101">XmlWriter throws on invalid surrogate pairs</span></span>

#### <a name="details"></a><span data-ttu-id="5be8f-102">説明</span><span class="sxs-lookup"><span data-stu-id="5be8f-102">Details</span></span>

<span data-ttu-id="5be8f-103">.NET Framework 4.5.2 またはそれ以前のバージョンをターゲットとするアプリケーションの場合、例外フォールバック処理を使用した無効なサロゲート ペアを作成しても、必ず例外がスローされるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="5be8f-103">For apps that target the .NET Framework 4.5.2 or previous versions, writing an invalid surrogate pair using exception fallback handling does not always throw an exception.</span></span> <span data-ttu-id="5be8f-104">.NET Framework 4.6 を対象とするアプリでは、無効なサロゲート ペアを作成しようとすると、<xref:System.ArgumentException?displayProperty=fullName> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5be8f-104">For apps that target the .NET Framework 4.6, attempting to write an invalid surrogate pair throws an <xref:System.ArgumentException?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5be8f-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="5be8f-105">Suggestion</span></span>

<span data-ttu-id="5be8f-106">必要に応じて、.NET Framework 4.5.2 以前をターゲットとすることでこの問題を回避できます。</span><span class="sxs-lookup"><span data-stu-id="5be8f-106">If necessary, this break can be avoided by targeting the .NET Framework 4.5.2 or earlier.</span></span> <span data-ttu-id="5be8f-107">または、無効なサロゲート ペアを有効な xml に書き込む前に事前処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="5be8f-107">Alternatively, invalid surrogate pairs can be pre-processed into valid xml prior to writing them.</span></span>

| <span data-ttu-id="5be8f-108">名前</span><span class="sxs-lookup"><span data-stu-id="5be8f-108">Name</span></span>    | <span data-ttu-id="5be8f-109">値</span><span class="sxs-lookup"><span data-stu-id="5be8f-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5be8f-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="5be8f-110">Scope</span></span>   | <span data-ttu-id="5be8f-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="5be8f-111">Edge</span></span>        |
| <span data-ttu-id="5be8f-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="5be8f-112">Version</span></span> | <span data-ttu-id="5be8f-113">4.6</span><span class="sxs-lookup"><span data-stu-id="5be8f-113">4.6</span></span>         |
| <span data-ttu-id="5be8f-114">種類</span><span class="sxs-lookup"><span data-stu-id="5be8f-114">Type</span></span>    | <span data-ttu-id="5be8f-115">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="5be8f-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="5be8f-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="5be8f-116">Affected APIs</span></span>

- <xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteAttributeStringAsync(System.String,System.String,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCData(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCDataAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteChars(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCharsAsync(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteComment(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCommentAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteEntityRef(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteEntityRefAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRaw(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteProcessingInstruction(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteProcessingInstructionAsync(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRaw(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRawAsync(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRawAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteString(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteStringAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteSurrogateCharEntity(System.Char,System.Char)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteSurrogateCharEntityAsync(System.Char,System.Char)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteValue(System.String)?displayProperty=nameWithType>
