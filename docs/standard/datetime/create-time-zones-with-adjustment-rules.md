---
title: '方法: 調整規則のあるタイム ゾーンを作成する'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], creating
- time zones [.NET Framework], and adjustment rules
- adjustment rule [.NET Framework]
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: face995dbd5ba4b0b12e80bcef10a90b46c093ff
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586415"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a><span data-ttu-id="4d430-102">方法: 調整規則のあるタイム ゾーンを作成する</span><span class="sxs-lookup"><span data-stu-id="4d430-102">How to: Create time zones with adjustment rules</span></span>

<span data-ttu-id="4d430-103">アプリケーションで必要とされる正確なタイム ゾーン情報は、いくつかの理由で特定のシステムに存在しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d430-103">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

* <span data-ttu-id="4d430-104">タイム ゾーンがローカル システムのレジストリで定義されていません。</span><span class="sxs-lookup"><span data-stu-id="4d430-104">The time zone has never been defined in the local system's registry.</span></span>

* <span data-ttu-id="4d430-105">タイム ゾーンに関するデータが変更されたか、レジストリから削除します。</span><span class="sxs-lookup"><span data-stu-id="4d430-105">Data about the time zone has been modified or removed from the registry.</span></span>

* <span data-ttu-id="4d430-106">タイム ゾーンには、過去の特定の期間のタイム ゾーンの調整に関する正確な情報はありません。</span><span class="sxs-lookup"><span data-stu-id="4d430-106">The time zone does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="4d430-107">このような場合を呼び出すことができます、<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>アプリケーションに必要なタイム ゾーンを定義するメソッド。</span><span class="sxs-lookup"><span data-stu-id="4d430-107">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="4d430-108">このメソッドのオーバー ロードを使用すると、調整規則の有無、タイム ゾーンを作成します。</span><span class="sxs-lookup"><span data-stu-id="4d430-108">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="4d430-109">タイム ゾーンが夏時間をサポートする場合は、いずれかの固定長または浮動調整規則の調整を定義できます。</span><span class="sxs-lookup"><span data-stu-id="4d430-109">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="4d430-110">(これらの用語の定義は、「タイム ゾーンの用語」のセクションを参照してください[タイム ゾーンの概要](../../../docs/standard/datetime/time-zone-overview.md)。)。</span><span class="sxs-lookup"><span data-stu-id="4d430-110">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d430-111">呼び出すことによって作成されたカスタムのタイム ゾーン、<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>メソッドは、レジストリに追加されません。</span><span class="sxs-lookup"><span data-stu-id="4d430-111">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="4d430-112">代わりに、によって返されるオブジェクトの参照を介してのみアクセスすることができます、<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>メソッドの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="4d430-112">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="4d430-113">このトピックでは、調整規則のあるタイム ゾーンを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4d430-113">This topic shows how to create a time zone with adjustment rules.</span></span> <span data-ttu-id="4d430-114">夏時間調整規則がサポートされていないタイム ゾーンを作成するを参照してください。[方法。調整規則のないタイム ゾーンを作成](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)です。</span><span class="sxs-lookup"><span data-stu-id="4d430-114">To create a time zone that does not support daylight saving time adjustment rules, see [How to: Create Time Zones Without Adjustment Rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a><span data-ttu-id="4d430-115">浮動調整規則のあるタイム ゾーンを作成するには</span><span class="sxs-lookup"><span data-stu-id="4d430-115">To create a time zone with floating adjustment rules</span></span>

1. <span data-ttu-id="4d430-116">調整 (つまりは、各遷移から離れると標準時に、特定の時間間隔の間) ごとに、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4d430-116">For each adjustment (that is, for each transition away from and back to standard time over a particular time interval), do the following:</span></span>

    1. <span data-ttu-id="4d430-117">タイム ゾーン調整の切り替えの開始時刻を定義します。</span><span class="sxs-lookup"><span data-stu-id="4d430-117">Define the starting transition time for the time zone adjustment.</span></span>

       <span data-ttu-id="4d430-118">呼び出す必要があります、<xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType>メソッドを渡して、 <xref:System.DateTime> 、遷移、遷移の月を定義する整数値、遷移が発生する曜日を定義する整数値の時刻を定義する値と<xref:System.DayOfWeek>遷移が発生する曜日を定義する値。</span><span class="sxs-lookup"><span data-stu-id="4d430-118">You must call the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> method and pass it a <xref:System.DateTime> value that defines the time of the transition, an integer value that defines the month of the transition, an integer value that defines the week on which the transition occurs, and a <xref:System.DayOfWeek> value that defines the day of the week on which the transition occurs.</span></span> <span data-ttu-id="4d430-119">このメソッドの呼び出しをインスタンス化、<xref:System.TimeZoneInfo.TransitionTime>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4d430-119">This method call instantiates a <xref:System.TimeZoneInfo.TransitionTime> object.</span></span>

    2. <span data-ttu-id="4d430-120">タイム ゾーン調整の切り替えの終了時刻を定義します。</span><span class="sxs-lookup"><span data-stu-id="4d430-120">Define the ending transition time for the time zone adjustment.</span></span> <span data-ttu-id="4d430-121">別の呼び出しを必要があります、<xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="4d430-121">This requires another call to the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4d430-122">このメソッドを呼び出す 2 つ目のインスタンスを作成<xref:System.TimeZoneInfo.TransitionTime>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4d430-122">This method call instantiates a second <xref:System.TimeZoneInfo.TransitionTime> object.</span></span>

    3. <span data-ttu-id="4d430-123">呼び出す、<xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A>メソッドを渡して、有効な開始と終了日、調整の<xref:System.TimeSpan>遷移、および 2 つの時間を定義するオブジェクト<xref:System.TimeZoneInfo.TransitionTime>タイミングを定義するオブジェクトと夏時間の間の遷移時間が発生します。</span><span class="sxs-lookup"><span data-stu-id="4d430-123">Call the <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> method and pass it the effective start and end dates of the adjustment, a <xref:System.TimeSpan> object that defines the amount of time in the transition, and the two <xref:System.TimeZoneInfo.TransitionTime> objects that define when the transitions to and from daylight saving time occur.</span></span> <span data-ttu-id="4d430-124">このメソッドの呼び出しをインスタンス化、<xref:System.TimeZoneInfo.AdjustmentRule>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4d430-124">This method call instantiates a <xref:System.TimeZoneInfo.AdjustmentRule> object.</span></span>

    4. <span data-ttu-id="4d430-125">割り当てる、<xref:System.TimeZoneInfo.AdjustmentRule>オブジェクトの配列を<xref:System.TimeZoneInfo.AdjustmentRule>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4d430-125">Assign the <xref:System.TimeZoneInfo.AdjustmentRule> object to an array of <xref:System.TimeZoneInfo.AdjustmentRule> objects.</span></span>

2. <span data-ttu-id="4d430-126">タイム ゾーンの表示名を定義します。</span><span class="sxs-lookup"><span data-stu-id="4d430-126">Define the time zone's display name.</span></span> <span data-ttu-id="4d430-127">表示名を世界協定時刻 (UTC) からのタイム ゾーンのオフセットがかっこで囲まれているし、タイム ゾーンを 1 つまたは複数のタイム ゾーン、または 1 つの都市または、cou の詳細を識別する文字列の後に、ごく標準的な形式に依存します。ntries またはタイム ゾーン内の領域。</span><span class="sxs-lookup"><span data-stu-id="4d430-127">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

3. <span data-ttu-id="4d430-128">タイム ゾーンの標準時刻の名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="4d430-128">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="4d430-129">通常、この文字列は、タイム ゾーンの識別子としても使用します。</span><span class="sxs-lookup"><span data-stu-id="4d430-129">Typically, this string is also used as the time zone's identifier.</span></span>

4. <span data-ttu-id="4d430-130">タイム ゾーンの夏時間の名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="4d430-130">Define the name of the time zone's daylight time.</span></span>

5. <span data-ttu-id="4d430-131">タイム ゾーンの標準の名前とは異なる id を使用する場合は、タイム ゾーン id を定義します。</span><span class="sxs-lookup"><span data-stu-id="4d430-131">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

6. <span data-ttu-id="4d430-132">インスタンスを作成、 <xref:System.TimeSpan> UTC からのタイム ゾーンのオフセットを定義するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4d430-132">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="4d430-133">UTC より後の時刻のタイム ゾーン オフセットを正の値があります。</span><span class="sxs-lookup"><span data-stu-id="4d430-133">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="4d430-134">時刻は UTC よりも前のタイム ゾーンでは、負のオフセットがあります。</span><span class="sxs-lookup"><span data-stu-id="4d430-134">Time zones with times that are earlier than UTC have a negative offset.</span></span>

7. <span data-ttu-id="4d430-135">呼び出す、<xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType>新しいタイム ゾーンをインスタンス化するメソッド。</span><span class="sxs-lookup"><span data-stu-id="4d430-135">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="4d430-136">例</span><span class="sxs-lookup"><span data-stu-id="4d430-136">Example</span></span>

<span data-ttu-id="4d430-137">次の例では、さまざまな 1918年から現在までの時間間隔の調整規則を含む米国の中部標準時ゾーンを定義します。</span><span class="sxs-lookup"><span data-stu-id="4d430-137">The following example defines a Central Standard Time zone for the United States that includes adjustment rules for a variety of time intervals from 1918 to the present.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

<span data-ttu-id="4d430-138">この例で作成したタイム ゾーンでは、複数の調整規則があります。</span><span class="sxs-lookup"><span data-stu-id="4d430-138">The time zone created in this example has multiple adjustment rules.</span></span> <span data-ttu-id="4d430-139">有効な開始と終了日の任意の調整規則は別の調整規則の日付で重複していないことを確認する注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d430-139">Care must be taken to ensure that the effective start and end dates of any adjustment rule do not overlap with the dates of another adjustment rule.</span></span> <span data-ttu-id="4d430-140">、重複がある場合、<xref:System.InvalidTimeZoneException>がスローされます。</span><span class="sxs-lookup"><span data-stu-id="4d430-140">If there is an overlap, an <xref:System.InvalidTimeZoneException> is thrown.</span></span>

<span data-ttu-id="4d430-141">渡される 5 の値の浮動調整規則を`week`のパラメーター、<xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A>メソッドを特定の月の最終週の遷移が発生することを示します。</span><span class="sxs-lookup"><span data-stu-id="4d430-141">For floating adjustment rules, the value 5 is passed to the `week` parameter of the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> method to indicate that the transition occurs on the last week of a particular month.</span></span>

<span data-ttu-id="4d430-142">配列を作成することで<xref:System.TimeZoneInfo.AdjustmentRule>で使用するオブジェクト、<xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType>メソッドの呼び出し、コードは、初期化、調整の数とタイム ゾーンの作成に必要なサイズの配列。</span><span class="sxs-lookup"><span data-stu-id="4d430-142">In creating the array of <xref:System.TimeZoneInfo.AdjustmentRule> objects to use in the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> method call, the code could initialize the array to the size required by the number of adjustments to be created for the time zone.</span></span> <span data-ttu-id="4d430-143">このコード例では、代わりに、<xref:System.Collections.Generic.List%601.Add%2A>ジェネリックに各調整規則を追加するメソッド<xref:System.Collections.Generic.List%601>のコレクション<xref:System.TimeZoneInfo.AdjustmentRule>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4d430-143">Instead, this code example calls the <xref:System.Collections.Generic.List%601.Add%2A> method to add each adjustment rule to a generic <xref:System.Collections.Generic.List%601> collection of <xref:System.TimeZoneInfo.AdjustmentRule> objects.</span></span> <span data-ttu-id="4d430-144">コードを呼び出して、<xref:System.Collections.Generic.List%601.CopyTo%2A>メソッドをこのコレクションのメンバーを配列にコピーします。</span><span class="sxs-lookup"><span data-stu-id="4d430-144">The code then calls the <xref:System.Collections.Generic.List%601.CopyTo%2A> method to copy the members of this collection to the array.</span></span>

<span data-ttu-id="4d430-145">また、例では、<xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A>固定日付の調整を定義するメソッド。</span><span class="sxs-lookup"><span data-stu-id="4d430-145">The example also uses the <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> method to define fixed-date adjustments.</span></span> <span data-ttu-id="4d430-146">これは、呼び出しに似ています、<xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A>ことは、時間、月、および遷移パラメーターの 1 日のみが必要です。 ただし、メソッド。</span><span class="sxs-lookup"><span data-stu-id="4d430-146">This is similar to calling the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> method, except that it requires only the time, month, and day of the transition parameters.</span></span>

<span data-ttu-id="4d430-147">例は、次のコードを使用してテストできます。</span><span class="sxs-lookup"><span data-stu-id="4d430-147">The example can be tested using code such as the following:</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a><span data-ttu-id="4d430-148">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="4d430-148">Compiling the code</span></span>

<span data-ttu-id="4d430-149">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4d430-149">This example requires:</span></span>

* <span data-ttu-id="4d430-150">次の名前空間は、インポートします。</span><span class="sxs-lookup"><span data-stu-id="4d430-150">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="4d430-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d430-151">See also</span></span>

- [<span data-ttu-id="4d430-152">日付、時刻、およびタイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="4d430-152">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="4d430-153">タイム ゾーンの概要</span><span class="sxs-lookup"><span data-stu-id="4d430-153">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="4d430-154">方法: 調整規則のないタイム ゾーンを作成します。</span><span class="sxs-lookup"><span data-stu-id="4d430-154">How to: Create time zones without adjustment rules</span></span>](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
