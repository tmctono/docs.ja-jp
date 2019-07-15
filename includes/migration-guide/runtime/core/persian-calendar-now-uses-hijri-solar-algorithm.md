---
ms.openlocfilehash: 130c26b7d135db232eb40a2c466aa3bdb2481ace
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858422"
---
### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a><span data-ttu-id="e83d6-101">ペルシャ暦でイスラム暦の太陽アルゴリズムが使用されるようになった</span><span class="sxs-lookup"><span data-stu-id="e83d6-101">Persian calendar now uses the Hijri solar algorithm</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e83d6-102">説明</span><span class="sxs-lookup"><span data-stu-id="e83d6-102">Details</span></span>|<span data-ttu-id="e83d6-103">.NET Framework 4.6 以降では、<xref:System.Globalization.PersianCalendar?displayProperty=name> クラスでイスラム暦の太陽アルゴリズムが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e83d6-103">Starting with the .NET Framework 4.6, the <xref:System.Globalization.PersianCalendar?displayProperty=name> class uses the Hijri solar algorithm.</span></span> <span data-ttu-id="e83d6-104"><xref:System.Globalization.PersianCalendar?displayProperty=name> と他のカレンダーの間で日付を変換すると、.NET Framework 4.6 以降では、1800 年より前か 2023 年 (グレゴリオ暦) よりも後の日付について、わずかに異なる結果になることがあります。また、<xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> は <code>March 21, 0622</code> ではなく <code>March 22, 0622</code> になります。</span><span class="sxs-lookup"><span data-stu-id="e83d6-104">Converting dates between the <xref:System.Globalization.PersianCalendar?displayProperty=name> and other calendars may produce a slightly different result beginning with the .NET Framework 4.6 for dates earlier than 1800 or later than 2023 (Gregorian).Also, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> is now <code>March 22, 0622</code> instead of <code>March 21, 0622</code>.</span></span>|
|<span data-ttu-id="e83d6-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="e83d6-105">Suggestion</span></span>|<span data-ttu-id="e83d6-106">.NET Framework 4.6 で PersianCalendar を使用するときには、一部の早い日付または遅い日付に若干の差が生じる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e83d6-106">Be aware that some early or late dates may be slightly different when using the PersianCalendar in .NET Framework 4.6.</span></span> <span data-ttu-id="e83d6-107">また、異なるバージョンの .NET Framework で実行する可能性のあるプロセス間で日付をシリアル化するときには、PersianCalendar の日付文字列として格納しないでください (これらの値が異なる場合があるため)。</span><span class="sxs-lookup"><span data-stu-id="e83d6-107">Also, when serializing dates between processes which may run on different .NET Framework versions, do not store them as PersianCalendar date strings (since those values may be different).</span></span>|
|<span data-ttu-id="e83d6-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="e83d6-108">Scope</span></span>|<span data-ttu-id="e83d6-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="e83d6-109">Minor</span></span>|
|<span data-ttu-id="e83d6-110">Version</span><span class="sxs-lookup"><span data-stu-id="e83d6-110">Version</span></span>|<span data-ttu-id="e83d6-111">4.6</span><span class="sxs-lookup"><span data-stu-id="e83d6-111">4.6</span></span>|
|<span data-ttu-id="e83d6-112">型</span><span class="sxs-lookup"><span data-stu-id="e83d6-112">Type</span></span>|<span data-ttu-id="e83d6-113">ランタイム</span><span class="sxs-lookup"><span data-stu-id="e83d6-113">Runtime</span></span>|
|<span data-ttu-id="e83d6-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e83d6-114">Affected APIs</span></span>|<ul><li><xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|

