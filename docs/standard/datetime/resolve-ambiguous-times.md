---
title: '方法: あいまいな時刻を解決する'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
ms.openlocfilehash: 0b5b28c588237fb2f7f069aaef06f3f73d5268bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122250"
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="3c856-102">方法: あいまいな時刻を解決する</span><span class="sxs-lookup"><span data-stu-id="3c856-102">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="3c856-103">あいまいな時刻とは、複数の世界協定時刻 (UTC) にマップされる時刻です。</span><span class="sxs-lookup"><span data-stu-id="3c856-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="3c856-104">これは、あるタイム ゾーンの夏時間から標準時間に移行する際など、時計の時刻を前に戻すときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3c856-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="3c856-105">あいまいな時刻を処理する場合は、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3c856-105">When handling an ambiguous time, you can do one of the following:</span></span>

- <span data-ttu-id="3c856-106">時刻が UTC にどのようにマップされるかを想定します。</span><span class="sxs-lookup"><span data-stu-id="3c856-106">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="3c856-107">たとえば、あいまいな時刻は常にタイム ゾーンの標準時刻で表されると想定できます。</span><span class="sxs-lookup"><span data-stu-id="3c856-107">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

- <span data-ttu-id="3c856-108">あいまいな時刻が、ユーザーによって入力されたデータ項目である場合は、あいまいさの解決をユーザーに任せることができます。</span><span class="sxs-lookup"><span data-stu-id="3c856-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="3c856-109">このトピックでは、タイムゾーンの標準時刻を表すと想定して、あいまいな時刻を解決する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c856-109">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="3c856-110">あいまいな時刻をタイム ゾーンの標準時刻にマップするには</span><span class="sxs-lookup"><span data-stu-id="3c856-110">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="3c856-111"><xref:System.TimeZoneInfo.IsAmbiguousTime%2A> メソッドを呼び出して、時刻があいまいであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3c856-111">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="3c856-112">時刻があいまいな場合は、タイムゾーンの <xref:System.TimeZoneInfo.BaseUtcOffset%2A> プロパティによって返された <xref:System.TimeSpan> オブジェクトから時刻を減算します。</span><span class="sxs-lookup"><span data-stu-id="3c856-112">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="3c856-113">`static` (Visual Basic .NET で`Shared`) <xref:System.DateTime.SpecifyKind%2A> メソッドを呼び出して、UTC の日付と時刻の値の <xref:System.DateTime.Kind%2A> プロパティを <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>に設定します。</span><span class="sxs-lookup"><span data-stu-id="3c856-113">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="3c856-114">例</span><span class="sxs-lookup"><span data-stu-id="3c856-114">Example</span></span>

<span data-ttu-id="3c856-115">次の例は、ローカルタイムゾーンの標準時刻を表すと想定して、あいまいな時刻を UTC に変換する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3c856-115">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="3c856-116">この例は、渡された <xref:System.DateTime> 値があいまいであるかどうかを判断する `ResolveAmbiguousTime` という名前のメソッドで構成されています。</span><span class="sxs-lookup"><span data-stu-id="3c856-116">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="3c856-117">値があいまいな場合、メソッドは、対応する UTC 時刻を表す <xref:System.DateTime> 値を返します。</span><span class="sxs-lookup"><span data-stu-id="3c856-117">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="3c856-118">メソッドは、ローカルタイムゾーンの <xref:System.TimeZoneInfo.BaseUtcOffset%2A> プロパティの値をローカル時刻から減算することによって、この変換を処理します。</span><span class="sxs-lookup"><span data-stu-id="3c856-118">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="3c856-119">通常、あいまいな時刻は、<xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> メソッドを呼び出し、あいまいな時刻の UTC オフセットを含む <xref:System.TimeSpan> オブジェクトの配列を取得することによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="3c856-119">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="3c856-120">しかし、この例は、あいまいな時刻は常にタイム ゾーンの標準時刻にマップされるという想定に基づいています。</span><span class="sxs-lookup"><span data-stu-id="3c856-120">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="3c856-121"><xref:System.TimeZoneInfo.BaseUtcOffset%2A> プロパティは、UTC とタイムゾーンの標準時刻の間のオフセットを返します。</span><span class="sxs-lookup"><span data-stu-id="3c856-121">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="3c856-122">この例では、ローカルタイムゾーンへのすべての参照は、<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> プロパティを使用して作成されます。ローカルタイムゾーンがオブジェクト変数に割り当てられることはありません。</span><span class="sxs-lookup"><span data-stu-id="3c856-122">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="3c856-123">これは、<xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> メソッドを呼び出すと、ローカルタイムゾーンが割り当てられているすべてのオブジェクトが無効になるため、推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="3c856-123">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="3c856-124">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="3c856-124">Compiling the code</span></span>

<span data-ttu-id="3c856-125">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3c856-125">This example requires:</span></span>

- <span data-ttu-id="3c856-126"><xref:System> 名前空間は、`using` ステートメント (コードでC#必要) を使用してインポートされます。</span><span class="sxs-lookup"><span data-stu-id="3c856-126">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="3c856-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c856-127">See also</span></span>

- [<span data-ttu-id="3c856-128">日付、時刻およびタイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="3c856-128">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="3c856-129">方法: ユーザーがあいまいな時刻を解決できるようにする</span><span class="sxs-lookup"><span data-stu-id="3c856-129">How to: Let users resolve ambiguous times</span></span>](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
