---
title: '方法: ユーザーがあいまいな時刻を解決できるようにする'
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae6d16bda7a2cd6f2367129b737ec79d8193ebf9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903787"
---
# <a name="how-to-let-users-resolve-ambiguous-times"></a><span data-ttu-id="2a761-102">方法: ユーザーがあいまいな時刻を解決できるようにする</span><span class="sxs-lookup"><span data-stu-id="2a761-102">How to: Let users resolve ambiguous times</span></span>

<span data-ttu-id="2a761-103">あいまいな時刻とは、複数の世界協定時刻 (UTC) にマップされる時刻です。</span><span class="sxs-lookup"><span data-stu-id="2a761-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="2a761-104">これは、あるタイム ゾーンの夏時間から標準時間に移行する際など、時計の時刻を前に戻すときに発生します。</span><span class="sxs-lookup"><span data-stu-id="2a761-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="2a761-105">あいまいな時刻を処理する場合は、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2a761-105">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="2a761-106">あいまいな時刻が、ユーザーによって入力されたデータの項目の場合は、あいまいさの解決をユーザーに任せることができます。</span><span class="sxs-lookup"><span data-stu-id="2a761-106">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

* <span data-ttu-id="2a761-107">時刻が UTC にどのようにマップされるかを想定します。</span><span class="sxs-lookup"><span data-stu-id="2a761-107">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="2a761-108">たとえば、あいまいな時刻は常にタイム ゾーンの標準時刻で表されると想定できます。</span><span class="sxs-lookup"><span data-stu-id="2a761-108">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

<span data-ttu-id="2a761-109">このトピックでは、ユーザーにあいまいな時刻を解決できるようにする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2a761-109">This topic shows how to let a user resolve an ambiguous time.</span></span>

### <a name="to-let-a-user-resolve-an-ambiguous-time"></a><span data-ttu-id="2a761-110">ユーザーにあいまいな時刻を解決させるには</span><span class="sxs-lookup"><span data-stu-id="2a761-110">To let a user resolve an ambiguous time</span></span>

1. <span data-ttu-id="2a761-111">ユーザーによって入力された日付と時刻を取得します。</span><span class="sxs-lookup"><span data-stu-id="2a761-111">Get the date and time input by the user.</span></span>

2. <span data-ttu-id="2a761-112">呼び出す、<xref:System.TimeZoneInfo.IsAmbiguousTime%2A>時刻があいまいかどうかを判断するメソッド。</span><span class="sxs-lookup"><span data-stu-id="2a761-112">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

3. <span data-ttu-id="2a761-113">時刻があいまいな場合は、呼び出し、<xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A>の配列を取得するメソッドを<xref:System.TimeSpan>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2a761-113">If the time is ambiguous, call the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects.</span></span> <span data-ttu-id="2a761-114">配列内の各要素には、あいまいな時刻にマップできる UTC オフセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2a761-114">Each element in the array contains a UTC offset that the ambiguous time can map to.</span></span>

4. <span data-ttu-id="2a761-115">ユーザーに目的のオフセットを選択させます。</span><span class="sxs-lookup"><span data-stu-id="2a761-115">Let the user select the desired offset.</span></span>

5. <span data-ttu-id="2a761-116">ローカル時刻からユーザーによって選択されたオフセットを減算して、UTC の日時を取得します。</span><span class="sxs-lookup"><span data-stu-id="2a761-116">Get the UTC date and time by subtracting the offset selected by the user from the local time.</span></span>

6. <span data-ttu-id="2a761-117">呼び出す、 `static` (`Shared` Visual Basic .net)<xref:System.DateTime.SpecifyKind%2A>メソッド、UTC の日付と時刻の値の設定を<xref:System.DateTime.Kind%2A>プロパティを<xref:System.DateTimeKind.Utc?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="2a761-117">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="2a761-118">例</span><span class="sxs-lookup"><span data-stu-id="2a761-118">Example</span></span>

<span data-ttu-id="2a761-119">次の例では、ユーザーに日付と時刻を入力するように求め、それがあいまいである場合は、ユーザーにあいまいな時刻をマップする UTC 時刻を選択させています。</span><span class="sxs-lookup"><span data-stu-id="2a761-119">The following example prompts the user to enter a date and time and, if it is ambiguous, lets the user select the UTC time that the ambiguous time maps to.</span></span>

[!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
[!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]

<span data-ttu-id="2a761-120">コード例のコアの配列を使用して<xref:System.TimeSpan>あいまいな時刻を UTC からの可能性のあるオフセットを示すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2a761-120">The core of the example code uses an array of <xref:System.TimeSpan> objects to indicate possible offsets of the ambiguous time from UTC.</span></span> <span data-ttu-id="2a761-121">ただし、これらのオフセットは、ユーザーにとって意味がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a761-121">However, these offsets are unlikely to be meaningful to the user.</span></span> <span data-ttu-id="2a761-122">オフセットの意味を明確にするには、コードで、オフセットがローカル タイム ゾーンの標準時刻を表すか、または夏時間を表すかに注意します。</span><span class="sxs-lookup"><span data-stu-id="2a761-122">To clarify the meaning of the offsets, the code also notes whether an offset represents the local time zone's standard time or its daylight saving time.</span></span> <span data-ttu-id="2a761-123">標準には、コードの決定し、オフセットには、値を比較することで夏時間に移行するには、<xref:System.TimeZoneInfo.BaseUtcOffset%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="2a761-123">The code determines which time is standard and which time is daylight by comparing the offset with the value of the <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span> <span data-ttu-id="2a761-124">このプロパティは、UTC とタイム ゾーンの標準時間の差を示します。</span><span class="sxs-lookup"><span data-stu-id="2a761-124">This property indicates the difference between the UTC and the time zone's standard time.</span></span>

<span data-ttu-id="2a761-125">この例では、ローカル タイム ゾーンへのすべての参照によって行われた、<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>プロパティです。 ローカルのタイム ゾーンは、オブジェクト変数に割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="2a761-125">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="2a761-126">これは、ためにの推奨される方法への呼び出し、<xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>メソッドにローカル タイム ゾーンが割り当てられているすべてのオブジェクトが無効になります。</span><span class="sxs-lookup"><span data-stu-id="2a761-126">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="2a761-127">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="2a761-127">Compiling the code</span></span>

<span data-ttu-id="2a761-128">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2a761-128">This example requires:</span></span>

* <span data-ttu-id="2a761-129">System.Core.dll への参照をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="2a761-129">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="2a761-130"><xref:System>と共に名前空間をインポートする、`using`ステートメント (c# コードで必要)。</span><span class="sxs-lookup"><span data-stu-id="2a761-130">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="2a761-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a761-131">See also</span></span>

- [<span data-ttu-id="2a761-132">日付、時刻、およびタイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="2a761-132">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="2a761-133">方法: あいまいな時刻を解決するには</span><span class="sxs-lookup"><span data-stu-id="2a761-133">How to: Resolve ambiguous times</span></span>](../../../docs/standard/datetime/resolve-ambiguous-times.md)
