---
title: 日付、時刻、およびタイム ゾーン
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zone objects [.NET Framework]
- date and time data [.NET Framework]
- time zones [.NET Framework]
- times [.NET Framework], time zones
- time [.NET Framework], time zones
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03a5594b689a52b641ecece0f9a92fb6cdfe5735
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991287"
---
# <a name="dates-times-and-time-zones"></a><span data-ttu-id="1d99e-102">日付、時刻、およびタイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="1d99e-102">Dates, times, and time zones</span></span>

<span data-ttu-id="1d99e-103">.NET は基本的な <xref:System.DateTime> 構造体だけでなく、タイム ゾーンでの作業をサポートする次のクラスも提供しています。</span><span class="sxs-lookup"><span data-stu-id="1d99e-103">In addition to the basic <xref:System.DateTime> structure, .NET provides the following classes that support working with time zones:</span></span>

* <xref:System.TimeZone>

  <span data-ttu-id="1d99e-104">システムのローカル タイム ゾーンおよび世界協定時刻 (UTC) ゾーンで作業を行うには、このクラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-104">Use this class to work with the system's local time zone and the Coordinated Universal Time (UTC) zone.</span></span> <span data-ttu-id="1d99e-105">クラスの<xref:System.TimeZone>機能は、 <xref:System.TimeZoneInfo>クラスによって主に置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="1d99e-105">The functionality of the <xref:System.TimeZone> class is largely superseded by the <xref:System.TimeZoneInfo> class.</span></span>

* <xref:System.TimeZoneInfo>

  <span data-ttu-id="1d99e-106">このクラスを使用すると、システムに事前に定義されている任意のタイム ゾーンを処理し、新しいタイム ゾーンを作成して、1 つのタイム ゾーンから別のタイム ゾーンに日付/時刻を簡単に変換できます。</span><span class="sxs-lookup"><span data-stu-id="1d99e-106">Use this class to work with any time zone that is predefined on a system, to create new time zones, and to easily convert dates and times from one time zone to another.</span></span> <span data-ttu-id="1d99e-107">新規に開発を行う場合は、<xref:System.TimeZoneInfo> クラスではなく、<xref:System.TimeZone> クラスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d99e-107">For new development, use the <xref:System.TimeZoneInfo> class instead of the <xref:System.TimeZone> class.</span></span>

* <xref:System.DateTimeOffset>

  <span data-ttu-id="1d99e-108">UTC からのオフセット (つまり時差) がわかっている日付および時刻で作業を行う場合は、この構造体を使用します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-108">Use this structure to work with dates and times whose offset (or difference) from UTC is known.</span></span> <span data-ttu-id="1d99e-109"><xref:System.DateTimeOffset> 構造体は、日付および時刻の値と、その時刻の UTC からのオフセットを組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="1d99e-109">The <xref:System.DateTimeOffset> structure combines a date and time value with that time's offset from UTC.</span></span> <span data-ttu-id="1d99e-110">UTC との関係により、個々の日付と時刻の値によって具体的な日時が明確に特定されます。</span><span class="sxs-lookup"><span data-stu-id="1d99e-110">Because of its relationship to UTC, an individual date and time value unambiguously identifies a single point in time.</span></span> <span data-ttu-id="1d99e-111">これにより、<xref:System.DateTime> の値よりも、<xref:System.DateTimeOffset> の値の方がコンピューター間で移植しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="1d99e-111">This makes a <xref:System.DateTimeOffset> value more portable from one computer to another than a <xref:System.DateTime> value.</span></span>

<span data-ttu-id="1d99e-112">ドキュメントのこのセクションでは、タイム ゾーンでの作業を行ったり、あるタイム ゾーンから別のタイム ゾーンに日付と時刻を変換できる、タイム ゾーンに対応したアプリケーションを作成するために必要な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-112">This section of the documentation provides the information that you need to work with time zones and to create time zone-aware applications that can convert dates and times from one time zone to another.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1d99e-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1d99e-113">In this section</span></span>

<span data-ttu-id="1d99e-114">[タイム ゾーンの概要](../../../docs/standard/datetime/time-zone-overview.md) タイム ゾーンに対応したアプリケーションの作成に関連する用語、概念、問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-114">[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md) Discusses the terminology, concepts, and issues involved in creating time zone-aware applications.</span></span>

<span data-ttu-id="1d99e-115">[DateTime、DateTimeOffset、TimeSpan、および TimeZoneInfo の使い分け](../../../docs/standard/datetime/choosing-between-datetime.md) 日付および時刻のデータでの作業を行う場合、どのようなときに <xref:System.DateTime>、<xref:System.DateTimeOffset>、<xref:System.TimeZoneInfo> の型を使用するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-115">[Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md) Discusses when to use the <xref:System.DateTime>, <xref:System.DateTimeOffset>, and <xref:System.TimeZoneInfo> types when working with date and time data.</span></span>

<span data-ttu-id="1d99e-116">[ローカル システムで定義されているタイム ゾーンの検索](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) ローカル システムで検出されたタイム ゾーンを列挙する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-116">[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) Describes how to enumerate the time zones found on a local system.</span></span>

<span data-ttu-id="1d99e-117">[方法: コンピューター](../../../docs/standard/datetime/enumerate-time-zones.md)に存在するタイムゾーンを列挙する例では、コンピューターのレジストリに定義されているタイムゾーンを列挙し、ユーザーが一覧から定義済みのタイムゾーンを選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1d99e-117">[How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md) Provides examples that enumerate the time zones defined in a computer's registry and that let users select a predefined time zone from a list.</span></span>

<span data-ttu-id="1d99e-118">[方法: 定義済みの UTC およびローカルタイムゾーンオブジェクト](../../../docs/standard/datetime/access-utc-and-local.md)にアクセスする方法については、世界協定時刻とローカルタイムゾーンにアクセスする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-118">[How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) Describes how to access Coordinated Universal Time and the local time zone.</span></span>

<span data-ttu-id="1d99e-119">[方法: TimeZoneInfo オブジェクト](../../../docs/standard/datetime/instantiate-time-zone-info.md)のインスタンス化ローカルシステムレジストリから<xref:System.TimeZoneInfo>オブジェクトをインスタンス化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-119">[How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md) Describes how to instantiate a <xref:System.TimeZoneInfo> object from the local system registry.</span></span>

<span data-ttu-id="1d99e-120">[DateTimeOffset オブジェクトのインスタンス化](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md) <xref:System.DateTimeOffset> オブジェクトをインスタンス化する方法、および <xref:System.DateTime> の値を <xref:System.DateTimeOffset> の値に変換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-120">[Instantiating a DateTimeOffset object](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md) Discusses the ways in which a <xref:System.DateTimeOffset> object can be instantiated, and the ways in which a <xref:System.DateTime> value can be converted to a <xref:System.DateTimeOffset> value.</span></span>

<span data-ttu-id="1d99e-121">[方法: 調整規則](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)のないタイムゾーンを作成する夏時間との間の切り替えをサポートしないカスタムタイムゾーンを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-121">[How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) Describes how to create a custom time zone that does not support the transition to and from daylight saving time.</span></span>

<span data-ttu-id="1d99e-122">[方法: 調整規則](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)が設定されたタイムゾーンを作成する夏時間との間の1つ以上の遷移をサポートするカスタムタイムゾーンを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-122">[How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) Describes how to create a custom time zone that supports one or more transitions to and from daylight saving time.</span></span>

<span data-ttu-id="1d99e-123">[タイム ゾーンの保存と復元](../../../docs/standard/datetime/saving-and-restoring-time-zones.md) タイム ゾーン データのシリアル化と逆シリアル化が <xref:System.TimeZoneInfo> でどのようにサポートされるかを説明し、これらの機能を使用できるいくつかのシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-123">[Saving and restoring time zones](../../../docs/standard/datetime/saving-and-restoring-time-zones.md) Describes <xref:System.TimeZoneInfo> support for serialization and deserialization of time zone data and illustrates some of the scenarios in which these features can be used.</span></span>

<span data-ttu-id="1d99e-124">[方法: 埋め込みリソース](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)にタイムゾーンを保存するカスタムタイムゾーンを作成し、その情報をリソースファイルに保存する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-124">[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) Describes how to create a custom time zone and save its information in a resource file.</span></span>

<span data-ttu-id="1d99e-125">[方法: 埋め込みリソース](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)からタイムゾーンを復元する埋め込みリソースファイルに保存されているカスタムタイムゾーンをインスタンス化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-125">[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) Describes how to instantiate custom time zones that have been saved to an embedded resource file.</span></span>

<span data-ttu-id="1d99e-126">[日付と時刻を使用した算術演算の実行](../../../docs/standard/datetime/performing-arithmetic-operations.md) <xref:System.DateTime> および <xref:System.DateTimeOffset> の値の加算、減算、比較に関連する問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-126">[Performing arithmetic operations with dates and times](../../../docs/standard/datetime/performing-arithmetic-operations.md) Discusses the issues involved in adding, subtracting, and comparing <xref:System.DateTime> and <xref:System.DateTimeOffset> values.</span></span>

<span data-ttu-id="1d99e-127">[方法: 日付と時刻の演算](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)でタイムゾーンを使用するタイムゾーンの調整規則を反映する日付と時刻の演算を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-127">[How to: Use time zones in date and time arithmetic](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md) Discusses how to perform date and time arithmetic that reflects a time zone's adjustment rules.</span></span>

<span data-ttu-id="1d99e-128">[DateTime と DateTimeOffset 間の変換](../../../docs/standard/datetime/converting-between-datetime-and-offset.md) <xref:System.DateTime> の値と <xref:System.DateTimeOffset> の値の変換方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-128">[Converting between DateTime and DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md) Describes how to convert between <xref:System.DateTime> and <xref:System.DateTimeOffset> values.</span></span>

<span data-ttu-id="1d99e-129">[タイム ゾーン間での時刻の変換](../../../docs/standard/datetime/converting-between-time-zones.md) タイム ゾーン間での時刻の変換方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-129">[Converting times between time zones](../../../docs/standard/datetime/converting-between-time-zones.md) Describes how to convert times from one time zone to another.</span></span>

<span data-ttu-id="1d99e-130">[方法: あいまい](../../../docs/standard/datetime/resolve-ambiguous-times.md)な時刻を解決する時刻をタイムゾーンの標準時刻にマップして、あいまいな時刻を解決する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-130">[How to: Resolve ambiguous times](../../../docs/standard/datetime/resolve-ambiguous-times.md) Describes how to resolve an ambiguous time by mapping it to the time zone's standard time.</span></span>

<span data-ttu-id="1d99e-131">[方法: ユーザーがあいまい](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)な時刻を解決できるようにするユーザーがあいまいな現地時刻と世界協定時刻の間のマッピングを決定できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d99e-131">[How to: Let users resolve ambiguous times](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md) Describes how to let a user determine the mapping between an ambiguous local time and Coordinated Universal Time.</span></span>

## <a name="reference"></a><span data-ttu-id="1d99e-132">参照</span><span class="sxs-lookup"><span data-stu-id="1d99e-132">Reference</span></span>

<xref:System.TimeZoneInfo?displayProperty=nameWithType>
