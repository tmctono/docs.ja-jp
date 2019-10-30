---
title: '方法: 調整規則のないタイムゾーンを作成する'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
ms.openlocfilehash: 344d8307318d5a2e50eddb39ef488cd8c5f2fdac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129108"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a><span data-ttu-id="38ef0-102">方法: 調整規則のないタイムゾーンを作成する</span><span class="sxs-lookup"><span data-stu-id="38ef0-102">How to: Create time zones without adjustment rules</span></span>

<span data-ttu-id="38ef0-103">アプリケーションで必要とされる正確なタイムゾーン情報は、次のような理由で特定のシステムに存在しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="38ef0-103">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

- <span data-ttu-id="38ef0-104">タイムゾーンがローカルシステムのレジストリに定義されていません。</span><span class="sxs-lookup"><span data-stu-id="38ef0-104">The time zone has never been defined in the local system's registry.</span></span>

- <span data-ttu-id="38ef0-105">タイムゾーンに関するデータは、レジストリから変更または削除されています。</span><span class="sxs-lookup"><span data-stu-id="38ef0-105">Data about the time zone has been modified or removed from the registry.</span></span>

- <span data-ttu-id="38ef0-106">タイムゾーンは存在しますが、特定の履歴期間のタイムゾーン調整に関する正確な情報がありません。</span><span class="sxs-lookup"><span data-stu-id="38ef0-106">The time zone exists but does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="38ef0-107">このような場合は、<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> メソッドを呼び出して、アプリケーションで必要とされるタイムゾーンを定義できます。</span><span class="sxs-lookup"><span data-stu-id="38ef0-107">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="38ef0-108">このメソッドのオーバーロードを使用して、調整規則の有無に関係なくタイムゾーンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="38ef0-108">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="38ef0-109">タイムゾーンで夏時間がサポートされている場合は、固定調整規則または浮動調整規則のいずれかを使用して調整を定義できます。</span><span class="sxs-lookup"><span data-stu-id="38ef0-109">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="38ef0-110">(これらの用語の定義については、「タイムゾーンの[概要](../../../docs/standard/datetime/time-zone-overview.md)」の「タイムゾーンの用語」セクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="38ef0-110">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38ef0-111"><xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> メソッドを呼び出すことによって作成されたカスタムタイムゾーンは、レジストリには追加されません。</span><span class="sxs-lookup"><span data-stu-id="38ef0-111">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="38ef0-112">代わりに、<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> メソッド呼び出しによって返されるオブジェクト参照を使用してのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="38ef0-112">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="38ef0-113">このトピックでは、調整規則を使用せずにタイムゾーンを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="38ef0-113">This topic shows how to create a time zone without adjustment rules.</span></span> <span data-ttu-id="38ef0-114">夏時間調整規則をサポートするタイムゾーンを作成するには、「[方法: 調整規則を使用してタイムゾーンを作成](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38ef0-114">To create a time zone that supports daylight saving time adjustment rules, see [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-without-adjustment-rules"></a><span data-ttu-id="38ef0-115">調整規則のないタイムゾーンを作成するには</span><span class="sxs-lookup"><span data-stu-id="38ef0-115">To create a time zone without adjustment rules</span></span>

1. <span data-ttu-id="38ef0-116">タイムゾーンの表示名を定義します。</span><span class="sxs-lookup"><span data-stu-id="38ef0-116">Define the time zone's display name.</span></span>

   <span data-ttu-id="38ef0-117">表示名は、標準の形式に準拠しています。この形式では、世界協定時刻 (UTC) からのタイムゾーンのオフセットがかっこで囲まれ、その後にタイムゾーンを識別する文字列、タイムゾーン内の1つ以上の都市、または1つ以上の cou が続きます。タイムゾーンの ntries またはリージョン。</span><span class="sxs-lookup"><span data-stu-id="38ef0-117">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

2. <span data-ttu-id="38ef0-118">タイムゾーンの標準時刻の名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="38ef0-118">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="38ef0-119">通常、この文字列はタイムゾーンの識別子としても使用されます。</span><span class="sxs-lookup"><span data-stu-id="38ef0-119">Typically, this string is also used as the time zone's identifier.</span></span>

3. <span data-ttu-id="38ef0-120">タイムゾーンの標準名とは異なる識別子を使用する場合は、タイムゾーン識別子を定義します。</span><span class="sxs-lookup"><span data-stu-id="38ef0-120">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

4. <span data-ttu-id="38ef0-121">タイムゾーンの UTC からのオフセットを定義する <xref:System.TimeSpan> オブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="38ef0-121">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="38ef0-122">時刻が UTC より遅いタイムゾーンには、正のオフセットがあります。</span><span class="sxs-lookup"><span data-stu-id="38ef0-122">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="38ef0-123">時刻が UTC より前のタイムゾーンでは、負のオフセットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="38ef0-123">Time zones with times that are earlier than UTC have a negative offset.</span></span>

5. <span data-ttu-id="38ef0-124"><xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> メソッドを呼び出して、新しいタイムゾーンをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="38ef0-124">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="38ef0-125">例</span><span class="sxs-lookup"><span data-stu-id="38ef0-125">Example</span></span>

<span data-ttu-id="38ef0-126">次の例では、調整規則のない Mawson、南極のカスタムタイムゾーンを定義します。</span><span class="sxs-lookup"><span data-stu-id="38ef0-126">The following example defines a custom time zone for Mawson, Antarctica, which has no adjustment rules.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

<span data-ttu-id="38ef0-127"><xref:System.TimeZoneInfo.DisplayName%2A> プロパティに割り当てられた文字列は、標準形式に従います。この形式では、UTC からのタイムゾーンのオフセットの後にタイムゾーンのわかりやすい説明が続きます。</span><span class="sxs-lookup"><span data-stu-id="38ef0-127">The string assigned to the <xref:System.TimeZoneInfo.DisplayName%2A> property follows a standard format in which the time zone's offset from UTC is followed by a friendly description of the time zone.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="38ef0-128">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="38ef0-128">Compiling the code</span></span>

<span data-ttu-id="38ef0-129">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="38ef0-129">This example requires:</span></span>

- <span data-ttu-id="38ef0-130">次の名前空間がインポートされます。</span><span class="sxs-lookup"><span data-stu-id="38ef0-130">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="38ef0-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="38ef0-131">See also</span></span>

- [<span data-ttu-id="38ef0-132">日付、時刻およびタイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="38ef0-132">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="38ef0-133">タイム ゾーンの概要</span><span class="sxs-lookup"><span data-stu-id="38ef0-133">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="38ef0-134">方法: 調整規則のあるタイム ゾーンを作成する</span><span class="sxs-lookup"><span data-stu-id="38ef0-134">How to: Create time zones with adjustment rules</span></span>](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)
