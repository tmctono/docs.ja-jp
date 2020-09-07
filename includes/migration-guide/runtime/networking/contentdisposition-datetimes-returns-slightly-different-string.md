---
ms.openlocfilehash: eb5c032a020799fa19cc0a8cfaabb56e01417ff4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497177"
---
### <a name="contentdisposition-datetimes-returns-slightly-different-string"></a><span data-ttu-id="e8ee6-101">ContentDisposition DateTimes で少し異なる文字列が返される</span><span class="sxs-lookup"><span data-stu-id="e8ee6-101">ContentDisposition DateTimes returns slightly different string</span></span>

#### <a name="details"></a><span data-ttu-id="e8ee6-102">説明</span><span class="sxs-lookup"><span data-stu-id="e8ee6-102">Details</span></span>

<span data-ttu-id="e8ee6-103"><xref:System.Net.Mime.ContentDisposition?displayProperty=fullName> の文字列表現が更新され、4.6 以降では、常に <xref:System.DateTime?displayProperty=fullName> の時間コンポーネントが 2 桁で表されます。</span><span class="sxs-lookup"><span data-stu-id="e8ee6-103">String representations of <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName>'s have been updated, beginning in 4.6, to always represent the hour component of a <xref:System.DateTime?displayProperty=fullName> with two digits.</span></span> <span data-ttu-id="e8ee6-104">これは、[RFC822](https://www.ietf.org/rfc/rfc0822.txt) と [RFC2822](https://www.ietf.org/rfc/rfc2822.txt) に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="e8ee6-104">This is to comply with [RFC822](https://www.ietf.org/rfc/rfc0822.txt) and [RFC2822](https://www.ietf.org/rfc/rfc2822.txt).</span></span> <span data-ttu-id="e8ee6-105">これにより、4.6 では、配置の時間要素の 1 つが午前 10 時より前のシナリオでは、<xref:System.Net.Mime.ContentDisposition.ToString> は少し異なる文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="e8ee6-105">This causes <xref:System.Net.Mime.ContentDisposition.ToString> to return a slightly different string in 4.6 in scenarios where one of the disposition's time elements was before 10:00 AM.</span></span> <span data-ttu-id="e8ee6-106">ContentDispositions は文字列への変換によってシリアル化される場合があるため、<xref:System.Net.Mime.ContentDisposition.ToString> 操作、シリアル化、または GetHashCode 呼び出しを見直す必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e8ee6-106">Note that ContentDispositions are sometimes serialized via converting them to strings, so any <xref:System.Net.Mime.ContentDisposition.ToString> operations, serialization, or GetHashCode calls should be reviewed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e8ee6-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="e8ee6-107">Suggestion</span></span>

<span data-ttu-id="e8ee6-108">異なるバージョンの .NET Framework からの ContentDispotisions の文字列表現が互いに正しく対応することを期待しないでください。</span><span class="sxs-lookup"><span data-stu-id="e8ee6-108">Do not expect that string representations of ContentDispositions from different .NET Framework versions will correctly compare to one another.</span></span> <span data-ttu-id="e8ee6-109">可能な場合は、比較を行う前に、文字列を ContentDispositions に戻してください。</span><span class="sxs-lookup"><span data-stu-id="e8ee6-109">Convert the strings back to ContentDispositions, if possible, before conducting a comparison.</span></span>

| <span data-ttu-id="e8ee6-110">名前</span><span class="sxs-lookup"><span data-stu-id="e8ee6-110">Name</span></span>    | <span data-ttu-id="e8ee6-111">値</span><span class="sxs-lookup"><span data-stu-id="e8ee6-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e8ee6-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="e8ee6-112">Scope</span></span>   |<span data-ttu-id="e8ee6-113">マイナー</span><span class="sxs-lookup"><span data-stu-id="e8ee6-113">Minor</span></span>|
|<span data-ttu-id="e8ee6-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="e8ee6-114">Version</span></span>|<span data-ttu-id="e8ee6-115">4.6</span><span class="sxs-lookup"><span data-stu-id="e8ee6-115">4.6</span></span>|
|<span data-ttu-id="e8ee6-116">種類</span><span class="sxs-lookup"><span data-stu-id="e8ee6-116">Type</span></span>|<span data-ttu-id="e8ee6-117">ランタイム</span><span class="sxs-lookup"><span data-stu-id="e8ee6-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="e8ee6-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e8ee6-118">Affected APIs</span></span>

- <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=nameWithType>
- <xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Net.Mime.ContentDisposition.ToString`
- `M:System.Net.Mime.ContentDisposition.GetHashCode`

-->
