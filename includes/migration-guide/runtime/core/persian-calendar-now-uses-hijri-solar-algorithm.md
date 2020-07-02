---
ms.openlocfilehash: e4d9efe7d2a06a1e501b070c23184dcd913dba71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621284"
---
### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a><span data-ttu-id="ecec6-101">ペルシャ暦でイスラム暦の太陽アルゴリズムが使用されるようになった</span><span class="sxs-lookup"><span data-stu-id="ecec6-101">Persian calendar now uses the Hijri solar algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="ecec6-102">説明</span><span class="sxs-lookup"><span data-stu-id="ecec6-102">Details</span></span>

<span data-ttu-id="ecec6-103">.NET Framework 4.6 以降では、<xref:System.Globalization.PersianCalendar?displayProperty=fullName> クラスでイスラム暦の太陽アルゴリズムが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ecec6-103">Starting with the .NET Framework 4.6, the <xref:System.Globalization.PersianCalendar?displayProperty=fullName> class uses the Hijri solar algorithm.</span></span> <span data-ttu-id="ecec6-104"><xref:System.Globalization.PersianCalendar?displayProperty=fullName> と他のカレンダーの間で日付を変換すると、.NET Framework 4.6 以降では、1800 年より前か 2023 年 (グレゴリオ暦) よりも後の日付について、わずかに異なる結果になることがあります。また、<xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> は <code>March 21, 0622</code> ではなく <code>March 22, 0622</code> になります。</span><span class="sxs-lookup"><span data-stu-id="ecec6-104">Converting dates between the <xref:System.Globalization.PersianCalendar?displayProperty=fullName> and other calendars may produce a slightly different result beginning with the .NET Framework 4.6 for dates earlier than 1800 or later than 2023 (Gregorian).Also, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> is now <code>March 22, 0622</code> instead of <code>March 21, 0622</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ecec6-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="ecec6-105">Suggestion</span></span>

<span data-ttu-id="ecec6-106">.NET Framework 4.6 で PersianCalendar を使用するときには、一部の早い日付または遅い日付に若干の差が生じる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ecec6-106">Be aware that some early or late dates may be slightly different when using the PersianCalendar in .NET Framework 4.6.</span></span> <span data-ttu-id="ecec6-107">また、異なるバージョンの .NET Framework で実行する可能性のあるプロセス間で日付をシリアル化するときには、PersianCalendar の日付文字列として格納しないでください (これらの値が異なる場合があるため)。</span><span class="sxs-lookup"><span data-stu-id="ecec6-107">Also, when serializing dates between processes which may run on different .NET Framework versions, do not store them as PersianCalendar date strings (since those values may be different).</span></span>

| <span data-ttu-id="ecec6-108">名前</span><span class="sxs-lookup"><span data-stu-id="ecec6-108">Name</span></span>    | <span data-ttu-id="ecec6-109">値</span><span class="sxs-lookup"><span data-stu-id="ecec6-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ecec6-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="ecec6-110">Scope</span></span>   |<span data-ttu-id="ecec6-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="ecec6-111">Minor</span></span>|
|<span data-ttu-id="ecec6-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="ecec6-112">Version</span></span>|<span data-ttu-id="ecec6-113">4.6</span><span class="sxs-lookup"><span data-stu-id="ecec6-113">4.6</span></span>|
|<span data-ttu-id="ecec6-114">種類</span><span class="sxs-lookup"><span data-stu-id="ecec6-114">Type</span></span>|<span data-ttu-id="ecec6-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="ecec6-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ecec6-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="ecec6-116">Affected APIs</span></span>

-<xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|
