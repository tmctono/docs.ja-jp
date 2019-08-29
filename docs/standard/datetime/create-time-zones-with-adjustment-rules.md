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
ms.openlocfilehash: 6ae739d3c5dd233c2129950666846979edfba370
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106671"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a><span data-ttu-id="afbf1-102">方法: 調整規則のあるタイム ゾーンを作成する</span><span class="sxs-lookup"><span data-stu-id="afbf1-102">How to: Create time zones with adjustment rules</span></span>

<span data-ttu-id="afbf1-103">アプリケーションで必要とされる正確なタイムゾーン情報は、次のような理由で特定のシステムに存在しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="afbf1-103">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

- <span data-ttu-id="afbf1-104">タイムゾーンがローカルシステムのレジストリに定義されていません。</span><span class="sxs-lookup"><span data-stu-id="afbf1-104">The time zone has never been defined in the local system's registry.</span></span>

- <span data-ttu-id="afbf1-105">タイムゾーンに関するデータは、レジストリから変更または削除されています。</span><span class="sxs-lookup"><span data-stu-id="afbf1-105">Data about the time zone has been modified or removed from the registry.</span></span>

- <span data-ttu-id="afbf1-106">タイムゾーンには、特定の履歴期間のタイムゾーン調整に関する正確な情報がありません。</span><span class="sxs-lookup"><span data-stu-id="afbf1-106">The time zone does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="afbf1-107">このような場合は、 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>メソッドを呼び出して、アプリケーションで必要とされるタイムゾーンを定義できます。</span><span class="sxs-lookup"><span data-stu-id="afbf1-107">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="afbf1-108">このメソッドのオーバーロードを使用して、調整規則の有無に関係なくタイムゾーンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="afbf1-108">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="afbf1-109">タイムゾーンで夏時間がサポートされている場合は、固定調整規則または浮動調整規則のいずれかを使用して調整を定義できます。</span><span class="sxs-lookup"><span data-stu-id="afbf1-109">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="afbf1-110">(これらの用語の定義については、「タイムゾーンの[概要](../../../docs/standard/datetime/time-zone-overview.md)」の「タイムゾーンの用語」セクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="afbf1-110">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="afbf1-111"><xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>メソッドを呼び出すことによって作成されたカスタムタイムゾーンは、レジストリには追加されません。</span><span class="sxs-lookup"><span data-stu-id="afbf1-111">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="afbf1-112">代わりに、 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>メソッド呼び出しによって返されるオブジェクト参照を使用してのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="afbf1-112">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="afbf1-113">このトピックでは、調整規則を使用してタイムゾーンを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-113">This topic shows how to create a time zone with adjustment rules.</span></span> <span data-ttu-id="afbf1-114">夏時間調整規則をサポートしていないタイムゾーンを作成するには[、「方法:調整規則](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)のないタイムゾーンを作成します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-114">To create a time zone that does not support daylight saving time adjustment rules, see [How to: Create Time Zones Without Adjustment Rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a><span data-ttu-id="afbf1-115">浮動調整規則を使用してタイムゾーンを作成するには</span><span class="sxs-lookup"><span data-stu-id="afbf1-115">To create a time zone with floating adjustment rules</span></span>

1. <span data-ttu-id="afbf1-116">それぞれの調整について (つまり、特定の期間にわたって標準時間外に移行するたびに)、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-116">For each adjustment (that is, for each transition away from and back to standard time over a particular time interval), do the following:</span></span>

    1. <span data-ttu-id="afbf1-117">タイムゾーン調整の開始遷移時間を定義します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-117">Define the starting transition time for the time zone adjustment.</span></span>

       <span data-ttu-id="afbf1-118"><xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType>メソッドを呼び出して、遷移の時間を<xref:System.DateTime>定義する値、遷移の月を定義する整数値、 <xref:System.DayOfWeek>遷移を発生させる週を定義する整数値、およびという値を渡す必要があります。移行を実行する曜日を定義する値。</span><span class="sxs-lookup"><span data-stu-id="afbf1-118">You must call the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> method and pass it a <xref:System.DateTime> value that defines the time of the transition, an integer value that defines the month of the transition, an integer value that defines the week on which the transition occurs, and a <xref:System.DayOfWeek> value that defines the day of the week on which the transition occurs.</span></span> <span data-ttu-id="afbf1-119">このメソッド呼び出しは、 <xref:System.TimeZoneInfo.TransitionTime>オブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-119">This method call instantiates a <xref:System.TimeZoneInfo.TransitionTime> object.</span></span>

    2. <span data-ttu-id="afbf1-120">タイムゾーン調整の終了遷移時間を定義します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-120">Define the ending transition time for the time zone adjustment.</span></span> <span data-ttu-id="afbf1-121">これには、メソッドの<xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType>別の呼び出しが必要です。</span><span class="sxs-lookup"><span data-stu-id="afbf1-121">This requires another call to the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="afbf1-122">このメソッド呼び出しは、2 <xref:System.TimeZoneInfo.TransitionTime>番目のオブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-122">This method call instantiates a second <xref:System.TimeZoneInfo.TransitionTime> object.</span></span>

    3. <span data-ttu-id="afbf1-123">メソッドを呼び出し、調整<xref:System.TimeSpan>の有効な開始日と終了日、遷移の時間を定義するオブジェクト、および夏時間との間の切り替えを定義<xref:System.TimeZoneInfo.TransitionTime>する2つのオブジェクトを渡します。 <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A>時間が発生します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-123">Call the <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> method and pass it the effective start and end dates of the adjustment, a <xref:System.TimeSpan> object that defines the amount of time in the transition, and the two <xref:System.TimeZoneInfo.TransitionTime> objects that define when the transitions to and from daylight saving time occur.</span></span> <span data-ttu-id="afbf1-124">このメソッド呼び出しは、 <xref:System.TimeZoneInfo.AdjustmentRule>オブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-124">This method call instantiates a <xref:System.TimeZoneInfo.AdjustmentRule> object.</span></span>

    4. <span data-ttu-id="afbf1-125">オブジェクトをオブジェクトの<xref:System.TimeZoneInfo.AdjustmentRule>配列に割り当てます。 <xref:System.TimeZoneInfo.AdjustmentRule></span><span class="sxs-lookup"><span data-stu-id="afbf1-125">Assign the <xref:System.TimeZoneInfo.AdjustmentRule> object to an array of <xref:System.TimeZoneInfo.AdjustmentRule> objects.</span></span>

2. <span data-ttu-id="afbf1-126">タイムゾーンの表示名を定義します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-126">Define the time zone's display name.</span></span> <span data-ttu-id="afbf1-127">表示名は、標準の形式に準拠しています。この形式では、世界協定時刻 (UTC) からのタイムゾーンのオフセットがかっこで囲まれ、その後にタイムゾーンを識別する文字列、タイムゾーン内の1つ以上の都市、または1つ以上の cou が続きます。タイムゾーンの ntries またはリージョン。</span><span class="sxs-lookup"><span data-stu-id="afbf1-127">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

3. <span data-ttu-id="afbf1-128">タイムゾーンの標準時刻の名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-128">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="afbf1-129">通常、この文字列はタイムゾーンの識別子としても使用されます。</span><span class="sxs-lookup"><span data-stu-id="afbf1-129">Typically, this string is also used as the time zone's identifier.</span></span>

4. <span data-ttu-id="afbf1-130">タイムゾーンの夏時間の名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-130">Define the name of the time zone's daylight time.</span></span>

5. <span data-ttu-id="afbf1-131">タイムゾーンの標準名とは異なる識別子を使用する場合は、タイムゾーン識別子を定義します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-131">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

6. <span data-ttu-id="afbf1-132">タイムゾーン<xref:System.TimeSpan>の UTC からのオフセットを定義するオブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-132">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="afbf1-133">時刻が UTC より遅いタイムゾーンには、正のオフセットがあります。</span><span class="sxs-lookup"><span data-stu-id="afbf1-133">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="afbf1-134">時刻が UTC より前のタイムゾーンでは、負のオフセットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="afbf1-134">Time zones with times that are earlier than UTC have a negative offset.</span></span>

7. <span data-ttu-id="afbf1-135"><xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType>メソッドを呼び出して、新しいタイムゾーンをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-135">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="afbf1-136">例</span><span class="sxs-lookup"><span data-stu-id="afbf1-136">Example</span></span>

<span data-ttu-id="afbf1-137">次の例では、1918から現在のまでのさまざまな時間間隔の調整規則を含む米国の中部標準時のタイムゾーンを定義します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-137">The following example defines a Central Standard Time zone for the United States that includes adjustment rules for a variety of time intervals from 1918 to the present.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

<span data-ttu-id="afbf1-138">この例で作成したタイムゾーンには、複数の調整規則があります。</span><span class="sxs-lookup"><span data-stu-id="afbf1-138">The time zone created in this example has multiple adjustment rules.</span></span> <span data-ttu-id="afbf1-139">調整規則の有効な開始日と終了日が、別の調整規則の日付と重複しないように注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afbf1-139">Care must be taken to ensure that the effective start and end dates of any adjustment rule do not overlap with the dates of another adjustment rule.</span></span> <span data-ttu-id="afbf1-140">重複がある場合は、 <xref:System.InvalidTimeZoneException>がスローされます。</span><span class="sxs-lookup"><span data-stu-id="afbf1-140">If there is an overlap, an <xref:System.InvalidTimeZoneException> is thrown.</span></span>

<span data-ttu-id="afbf1-141">浮動調整規則では、値5が`week` <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A>メソッドのパラメーターに渡され、特定の月の最後の週に移行が行われることを示します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-141">For floating adjustment rules, the value 5 is passed to the `week` parameter of the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> method to indicate that the transition occurs on the last week of a particular month.</span></span>

<span data-ttu-id="afbf1-142">メソッド<xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType>呼び出しで使用する<xref:System.TimeZoneInfo.AdjustmentRule>オブジェクトの配列を作成する場合、コードは、タイムゾーンに対して作成される調整の数に必要なサイズに配列を初期化できます。</span><span class="sxs-lookup"><span data-stu-id="afbf1-142">In creating the array of <xref:System.TimeZoneInfo.AdjustmentRule> objects to use in the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> method call, the code could initialize the array to the size required by the number of adjustments to be created for the time zone.</span></span> <span data-ttu-id="afbf1-143">代わりに、このコード例では<xref:System.Collections.Generic.List%601.Add%2A>メソッドを呼び出して、オブジェクトの<xref:System.TimeZoneInfo.AdjustmentRule>ジェネリック<xref:System.Collections.Generic.List%601>コレクションに各調整規則を追加します。</span><span class="sxs-lookup"><span data-stu-id="afbf1-143">Instead, this code example calls the <xref:System.Collections.Generic.List%601.Add%2A> method to add each adjustment rule to a generic <xref:System.Collections.Generic.List%601> collection of <xref:System.TimeZoneInfo.AdjustmentRule> objects.</span></span> <span data-ttu-id="afbf1-144">次に、 <xref:System.Collections.Generic.List%601.CopyTo%2A>メソッドを呼び出して、このコレクションのメンバーを配列にコピーします。</span><span class="sxs-lookup"><span data-stu-id="afbf1-144">The code then calls the <xref:System.Collections.Generic.List%601.CopyTo%2A> method to copy the members of this collection to the array.</span></span>

<span data-ttu-id="afbf1-145">また、この例で<xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A>は、メソッドを使用して、固定日付の調整を定義しています。</span><span class="sxs-lookup"><span data-stu-id="afbf1-145">The example also uses the <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> method to define fixed-date adjustments.</span></span> <span data-ttu-id="afbf1-146">これは、メソッドの<xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A>呼び出しに似ていますが、移行パラメーターの時刻、月、および日のみが必要です。</span><span class="sxs-lookup"><span data-stu-id="afbf1-146">This is similar to calling the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> method, except that it requires only the time, month, and day of the transition parameters.</span></span>

<span data-ttu-id="afbf1-147">この例は、次のようなコードを使用してテストできます。</span><span class="sxs-lookup"><span data-stu-id="afbf1-147">The example can be tested using code such as the following:</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a><span data-ttu-id="afbf1-148">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="afbf1-148">Compiling the code</span></span>

<span data-ttu-id="afbf1-149">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="afbf1-149">This example requires:</span></span>

- <span data-ttu-id="afbf1-150">次の名前空間がインポートされます。</span><span class="sxs-lookup"><span data-stu-id="afbf1-150">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="afbf1-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="afbf1-151">See also</span></span>

- [<span data-ttu-id="afbf1-152">日付、時刻、およびタイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="afbf1-152">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="afbf1-153">タイム ゾーンの概要</span><span class="sxs-lookup"><span data-stu-id="afbf1-153">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="afbf1-154">方法: 調整規則のないタイムゾーンを作成する</span><span class="sxs-lookup"><span data-stu-id="afbf1-154">How to: Create time zones without adjustment rules</span></span>](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
