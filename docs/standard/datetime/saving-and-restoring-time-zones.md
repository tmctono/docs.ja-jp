---
title: タイム ゾーンの保存と復元
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- restoring time zones
- deserialization [.NET Framework], time zones
- serialization [.NET Framework], time zones
- time zone objects [.NET Framework], restoring
- saving time zones
- time zone objects [.NET Framework], deserializing
- time zones [.NET Framework], saving
- time zones [.NET Framework], restoring
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 4028b310-e7ce-49d4-a646-1e83bfaf6f9d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d783f9e0d098e472dcf67aea394804d6eef2662
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026524"
---
# <a name="saving-and-restoring-time-zones"></a><span data-ttu-id="24b95-102">タイム ゾーンの保存と復元</span><span class="sxs-lookup"><span data-stu-id="24b95-102">Saving and restoring time zones</span></span>

<span data-ttu-id="24b95-103"><xref:System.TimeZoneInfo>クラスが定義済みのタイム ゾーン データを取得するレジストリに依存します。</span><span class="sxs-lookup"><span data-stu-id="24b95-103">The <xref:System.TimeZoneInfo> class relies on the registry to retrieve predefined time zone data.</span></span> <span data-ttu-id="24b95-104">ただし、レジストリは、動的な構造です。</span><span class="sxs-lookup"><span data-stu-id="24b95-104">However, the registry is a dynamic structure.</span></span> <span data-ttu-id="24b95-105">さらに、レジストリを含むタイム ゾーン情報は、現在の年の時刻の調整および変換を処理するには、主に、オペレーティング システムによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="24b95-105">Additionally, the time zone information that the registry contains is used by the operating system primarily to handle time adjustments and conversions for the current year.</span></span> <span data-ttu-id="24b95-106">これは、正確なタイム ゾーン データに依存するアプリケーションの 2 つの主要な影響があります。</span><span class="sxs-lookup"><span data-stu-id="24b95-106">This has two major implications for applications that rely on accurate time zone data:</span></span>

* <span data-ttu-id="24b95-107">アプリケーションで必要とされるタイム ゾーンがレジストリに定義されていませんが、または名前が変更されているか、レジストリから削除します。</span><span class="sxs-lookup"><span data-stu-id="24b95-107">A time zone that is required by an application may not be defined in the registry, or it may have been renamed or removed from the registry.</span></span>

* <span data-ttu-id="24b95-108">レジストリで定義されているタイム ゾーンは、過去のタイム ゾーン変換のために必要な特定の調整ルールに関する情報がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="24b95-108">A time zone that is defined in the registry may lack information about the particular adjustment rules that are necessary for historical time zone conversions.</span></span>

<span data-ttu-id="24b95-109"><xref:System.TimeZoneInfo>クラス (保存) をシリアル化および逆シリアル化のタイム ゾーンのデータを (復元) のサポートにより、これらの制限に対処します。</span><span class="sxs-lookup"><span data-stu-id="24b95-109">The <xref:System.TimeZoneInfo> class addresses these limitations through its support for serialization (saving) and deserialization (restoring) of time zone data.</span></span>

## <a name="time-zone-serialization-and-deserialization"></a><span data-ttu-id="24b95-110">タイム ゾーンのシリアル化および逆シリアル化</span><span class="sxs-lookup"><span data-stu-id="24b95-110">Time zone serialization and deserialization</span></span>

<span data-ttu-id="24b95-111">保存とタイム ゾーンのデータをシリアル化およびタイム ゾーンを復元するには、2 つのメソッド呼び出しにはが含まれます。</span><span class="sxs-lookup"><span data-stu-id="24b95-111">Saving and restoring a time zone by serializing and deserializing time zone data involves just two method calls:</span></span>

* <span data-ttu-id="24b95-112">シリアル化することができます、<xref:System.TimeZoneInfo>オブジェクトを呼び出して、そのオブジェクトの<xref:System.TimeZoneInfo.ToSerializedString%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="24b95-112">You can serialize a <xref:System.TimeZoneInfo> object by calling that object's <xref:System.TimeZoneInfo.ToSerializedString%2A> method.</span></span> <span data-ttu-id="24b95-113">メソッドは、パラメーターを受け取らないし、タイム ゾーン情報を含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="24b95-113">The method takes no parameters and returns a string that contains time zone information.</span></span>

* <span data-ttu-id="24b95-114">逆シリアル化することができます、<xref:System.TimeZoneInfo>にその文字列を渡すことによってシリアル化された文字列からオブジェクト、 `static` (`Shared` Visual Basic で)<xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="24b95-114">You can deserialize a <xref:System.TimeZoneInfo> object from a serialized string by passing that string to the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> method.</span></span>

## <a name="serialization-and-deserialization-scenarios"></a><span data-ttu-id="24b95-115">シリアル化および逆シリアル化シナリオ</span><span class="sxs-lookup"><span data-stu-id="24b95-115">Serialization and deserialization scenarios</span></span>

<span data-ttu-id="24b95-116">保存 (またはシリアル化) する機能、<xref:System.TimeZoneInfo>後で使用できる文字列と復元 (または逆シリアル化) にそのオブジェクトは、ユーティリティとの柔軟性の両方が増加、<xref:System.TimeZoneInfo>クラス。</span><span class="sxs-lookup"><span data-stu-id="24b95-116">The ability to save (or serialize) a <xref:System.TimeZoneInfo> object to a string and to restore (or deserialize) it for later use increases both the utility and the flexibility of the <xref:System.TimeZoneInfo> class.</span></span> <span data-ttu-id="24b95-117">このセクションでは、一部のシリアル化および逆シリアル化は最も役に立つ状況を調べます。</span><span class="sxs-lookup"><span data-stu-id="24b95-117">This section examines some of the situations in which serialization and deserialization are most useful.</span></span>

### <a name="serializing-and-deserializing-time-zone-data-in-an-application"></a><span data-ttu-id="24b95-118">シリアル化して、アプリケーションでのタイム ゾーン データを逆シリアル化</span><span class="sxs-lookup"><span data-stu-id="24b95-118">Serializing and deserializing time zone data in an application</span></span>

<span data-ttu-id="24b95-119">必要がある場合、文字列からシリアル化されたタイム ゾーンを復元できます。</span><span class="sxs-lookup"><span data-stu-id="24b95-119">A serialized time zone can be restored from a string when it is needed.</span></span> <span data-ttu-id="24b95-120">レジストリから取得するタイム ゾーンが特定の日付範囲内の日付を正しく変換できない場合は、アプリケーションでこれを行うことがあります。</span><span class="sxs-lookup"><span data-stu-id="24b95-120">An application might do this if the time zone retrieved from the registry is unable to correctly convert a date and time within a particular date range.</span></span> <span data-ttu-id="24b95-121">Windows XP のレジストリのタイム ゾーン データでは、通常、Windows Vista のレジストリで定義されているタイム ゾーンは 2 つの調整規則の情報を提供します、単一の調整規則をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="24b95-121">For example, time zone data in the Windows XP registry supports a single adjustment rule, while time zones defined in the Windows Vista registry typically provide information about two adjustment rules.</span></span> <span data-ttu-id="24b95-122">これは、過去の時刻の変換が不正確であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="24b95-122">This means that historical time conversions may be inaccurate.</span></span> <span data-ttu-id="24b95-123">シリアル化とタイム ゾーンのデータの逆シリアル化は、この制限を処理できます。</span><span class="sxs-lookup"><span data-stu-id="24b95-123">Serialization and deserialization of time zone data can handle this limitation.</span></span>

<span data-ttu-id="24b95-124">次の例では、カスタム<xref:System.TimeZoneInfo>を表す、米国の調整規則がないクラスが定義されています。東部標準時のゾーンは 1883 1917、米国で夏時間が登場する前にします。</span><span class="sxs-lookup"><span data-stu-id="24b95-124">In the following example, a custom <xref:System.TimeZoneInfo> class that has no adjustment rules is defined to represent the U.S. Eastern Standard Time zone from 1883 to 1917, before the introduction of daylight saving time in the United States.</span></span> <span data-ttu-id="24b95-125">カスタムのタイム ゾーンは、グローバル スコープを持つ変数にシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="24b95-125">The custom time zone is serialized in a variable that has global scope.</span></span> <span data-ttu-id="24b95-126">タイム ゾーン変換メソッド`ConvertUtcTime`は、協定世界協定世界時 (UTC) 時刻が変換に渡されます。</span><span class="sxs-lookup"><span data-stu-id="24b95-126">The time zone conversion method, `ConvertUtcTime`, is passed Coordinated Universal Time (UTC) times to convert.</span></span> <span data-ttu-id="24b95-127">日付と時刻は、1917年またはそれ以前に発生する場合、カスタム東部標準時ゾーンはシリアル化された文字列から復元され、レジストリから取得するタイム ゾーンが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="24b95-127">If the date and time occurs in 1917 or earlier, the custom Eastern Standard Time zone is restored from a serialized string and replaces the time zone retrieved from the registry.</span></span>

[!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
[!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]

### <a name="handling-time-zone-exceptions"></a><span data-ttu-id="24b95-128">タイム ゾーンの例外の処理</span><span class="sxs-lookup"><span data-stu-id="24b95-128">Handling time zone exceptions</span></span>

<span data-ttu-id="24b95-129">レジストリは、動的な構造であるために、その内容は、偶発的または意図的な変更が適用されます。</span><span class="sxs-lookup"><span data-stu-id="24b95-129">Because the registry is a dynamic structure, its contents are subject to accidental or deliberate modification.</span></span> <span data-ttu-id="24b95-130">つまり、レジストリで定義されていると、正常に実行するアプリケーションに必要なタイム ゾーンを指定しなくてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="24b95-130">This means that a time zone that should be defined in the registry and that is required for an application to execute successfully may be absent.</span></span> <span data-ttu-id="24b95-131">タイム ゾーンのシリアル化および逆シリアル化、サポートされていない場合、その結果を処理するが、ほとんどの選択肢がある<xref:System.TimeZoneNotFoundException>によってアプリケーションが終了します。</span><span class="sxs-lookup"><span data-stu-id="24b95-131">Without support for time zone serialization and deserialization, you have little choice but to handle the resulting <xref:System.TimeZoneNotFoundException> by ending the application.</span></span> <span data-ttu-id="24b95-132">ただし、タイム ゾーンのシリアル化および逆シリアル化を使用して処理できます予期しない<xref:System.TimeZoneNotFoundException>復元することによって、シリアル化された文字列と、アプリケーションから必要なタイム ゾーンは引き続き実行します。</span><span class="sxs-lookup"><span data-stu-id="24b95-132">However, by using time zone serialization and deserialization, you can handle an unexpected <xref:System.TimeZoneNotFoundException> by restoring the required time zone from a serialized string, and the application will continue to run.</span></span>

<span data-ttu-id="24b95-133">次の例では、作成し、カスタムの中部標準時ゾーンのシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="24b95-133">The following example creates and serializes a custom Central Standard Time zone.</span></span> <span data-ttu-id="24b95-134">レジストリから中部標準時ゾーンの取得が試行されます。</span><span class="sxs-lookup"><span data-stu-id="24b95-134">It then tries to retrieve the Central Standard Time zone from the registry.</span></span> <span data-ttu-id="24b95-135">取得操作では、いずれかがスローした場合、<xref:System.TimeZoneNotFoundException>または<xref:System.InvalidTimeZoneException>、例外ハンドラーには、タイム ゾーンが逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="24b95-135">If the retrieval operation throws either a <xref:System.TimeZoneNotFoundException> or an <xref:System.InvalidTimeZoneException>, the exception handler deserializes the time zone.</span></span>

[!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
[!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]

### <a name="storing-a-serialized-string-and-restoring-it-when-needed"></a><span data-ttu-id="24b95-136">シリアル化された文字列を保存して、必要なときに復元します。</span><span class="sxs-lookup"><span data-stu-id="24b95-136">Storing a serialized string and restoring it when needed</span></span>

<span data-ttu-id="24b95-137">前の例では、タイム ゾーン情報を文字列変数を格納し、必要なときに復元します。</span><span class="sxs-lookup"><span data-stu-id="24b95-137">The previous examples have stored time zone information to a string variable and restored it when needed.</span></span> <span data-ttu-id="24b95-138">ただし、シリアル化された時刻がゾーンの情報自体に格納できる外部ファイル、リソース ファイルなど、いくつかのストレージ メディアを格納する文字列は、アプリケーション、またはレジストリに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="24b95-138">However, the string that contains serialized time zone information can itself be stored in some storage medium, such as an external file, a resource file embedded in the application, or the registry.</span></span> <span data-ttu-id="24b95-139">(カスタムのタイム ゾーンに関する情報がレジストリで、システムのタイム ゾーンのキーとは別に格納することに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="24b95-139">(Note that information about custom time zones should be stored apart from the system's time zone keys in the registry.)</span></span>

<span data-ttu-id="24b95-140">この方法でシリアル化されたタイム ゾーン文字列を格納すると、タイム ゾーンの作成のルーチンも、アプリケーション自体とは別になります。</span><span class="sxs-lookup"><span data-stu-id="24b95-140">Storing a serialized time zone string in this manner also separates the time zone creation routine from the application itself.</span></span> <span data-ttu-id="24b95-141">たとえば、タイム ゾーンの作成ルーチンは、実行し、アプリケーションが使用できる過去のタイム ゾーン情報を含むデータ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="24b95-141">For example, a time zone creation routine can execute and create a data file that contains historical time zone information that an application can use.</span></span> <span data-ttu-id="24b95-142">データ ファイルを指定できます、アプリケーションと共にインストールして開くことができ、1 つまたは複数のタイム ゾーンのことが逆シリアル化、アプリケーションで必要なときにします。</span><span class="sxs-lookup"><span data-stu-id="24b95-142">The data file can be then be installed with the application, and it can be opened and one or more of its time zones can be deserialized when the application requires them.</span></span>

<span data-ttu-id="24b95-143">タイム ゾーンのシリアル化されたデータの格納に埋め込みリソースを使用する例を参照してください。[方法。埋め込みリソースにタイム ゾーンを保存](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)と[方法。埋め込みリソースからタイム ゾーンを復元](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)します。</span><span class="sxs-lookup"><span data-stu-id="24b95-143">For an example that uses an embedded resource to store serialized time zone data, see [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) and [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="24b95-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="24b95-144">See also</span></span>

- [<span data-ttu-id="24b95-145">日付、時刻、およびタイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="24b95-145">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
