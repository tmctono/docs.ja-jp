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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aae3e5145d2fa85cd55fc5b1288ef4aaa0fef48f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796410"
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="dfe8f-102">方法: あいまいな時刻を解決する</span><span class="sxs-lookup"><span data-stu-id="dfe8f-102">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="dfe8f-103">あいまいな時刻とは、複数の世界協定時刻 (UTC) にマップされる時刻です。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="dfe8f-104">これは、あるタイム ゾーンの夏時間から標準時間に移行する際など、時計の時刻を前に戻すときに発生します。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="dfe8f-105">あいまいな時刻を処理する場合は、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-105">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="dfe8f-106">時刻が UTC にどのようにマップされるかを想定します。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-106">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="dfe8f-107">たとえば、あいまいな時刻は常にタイム ゾーンの標準時刻で表されると想定できます。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-107">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

* <span data-ttu-id="dfe8f-108">あいまいな時刻が、ユーザーによって入力されたデータ項目である場合は、あいまいさの解決をユーザーに任せることができます。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="dfe8f-109">このトピックでは、タイム ゾーンの標準時刻を表すと想定してあいまいな時刻を解決する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-109">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="dfe8f-110">あいまいな時刻をタイム ゾーンの標準時刻にマップするには</span><span class="sxs-lookup"><span data-stu-id="dfe8f-110">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="dfe8f-111">呼び出す、<xref:System.TimeZoneInfo.IsAmbiguousTime%2A>時刻があいまいかどうかを判断するメソッド。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-111">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="dfe8f-112">時間を時刻があいまいな場合は、減算、<xref:System.TimeSpan>タイム ゾーンのによって返されるオブジェクト<xref:System.TimeZoneInfo.BaseUtcOffset%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-112">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="dfe8f-113">呼び出す、 `static` (`Shared` Visual Basic .net)<xref:System.DateTime.SpecifyKind%2A>メソッド、UTC の日付と時刻の値の設定を<xref:System.DateTime.Kind%2A>プロパティを<xref:System.DateTimeKind.Utc?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-113">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="dfe8f-114">例</span><span class="sxs-lookup"><span data-stu-id="dfe8f-114">Example</span></span>

<span data-ttu-id="dfe8f-115">次の例では、ローカル タイム ゾーンの標準時刻を表すと仮定すると、あいまいな時刻を UTC に変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-115">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="dfe8f-116">例では、という名前のメソッドから成る`ResolveAmbiguousTime`を決定するかどうか、<xref:System.DateTime>は渡された値があいまいです。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-116">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="dfe8f-117">値があいまい、メソッドを返します、<xref:System.DateTime>対応する UTC 時刻を表す値です。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-117">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="dfe8f-118">メソッドでは、この変換を処理のローカル タイム ゾーンの値を減算<xref:System.TimeZoneInfo.BaseUtcOffset%2A>からローカル時刻のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-118">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="dfe8f-119">呼び出すことによって、あいまいな時刻を処理する、通常、<xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A>の配列を取得するメソッドを<xref:System.TimeSpan>あいまいな時刻の考えられる UTC が含まれているオブジェクトのオフセットします。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-119">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="dfe8f-120">しかし、この例は、あいまいな時刻は常にタイム ゾーンの標準時刻にマップされるという想定に基づいています。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-120">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="dfe8f-121"><xref:System.TimeZoneInfo.BaseUtcOffset%2A>プロパティは、UTC とタイム ゾーンの標準時刻の間のオフセットを返します。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-121">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="dfe8f-122">この例では、ローカル タイム ゾーンへのすべての参照によって行われた、<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>プロパティです。 ローカルのタイム ゾーンは、オブジェクト変数に割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-122">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="dfe8f-123">これは、ためにの推奨される方法への呼び出し、<xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>メソッドにローカル タイム ゾーンが割り当てられているすべてのオブジェクトが無効になります。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-123">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="dfe8f-124">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="dfe8f-124">Compiling the code</span></span>

<span data-ttu-id="dfe8f-125">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-125">This example requires:</span></span>

* <span data-ttu-id="dfe8f-126">System.Core.dll への参照をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-126">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="dfe8f-127"><xref:System>と共に名前空間をインポートする、`using`ステートメント (c# コードで必要)。</span><span class="sxs-lookup"><span data-stu-id="dfe8f-127">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="dfe8f-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfe8f-128">See also</span></span>

- [<span data-ttu-id="dfe8f-129">日付、時刻、およびタイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="dfe8f-129">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="dfe8f-130">方法: ユーザーがあいまいな時刻を解決できるように</span><span class="sxs-lookup"><span data-stu-id="dfe8f-130">How to: Let users resolve ambiguous times</span></span>](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
