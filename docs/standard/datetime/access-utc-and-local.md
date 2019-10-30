---
title: '方法: 定義済みの UTC オブジェクトおよびローカルタイムゾーンオブジェクトにアクセスする'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET Framework], retrieving
- time zones [.NET Framework], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
ms.openlocfilehash: ef22753d9934a52d955412a4493b608f265519aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132608"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="923d5-102">方法: 定義済みの UTC オブジェクトおよびローカルタイムゾーンオブジェクトにアクセスする</span><span class="sxs-lookup"><span data-stu-id="923d5-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="923d5-103"><xref:System.TimeZoneInfo> クラスには、定義済みのタイムゾーンオブジェクトへのコードアクセスを提供する、<xref:System.TimeZoneInfo.Utc%2A> と <xref:System.TimeZoneInfo.Local%2A>という2つのプロパティが用意されています。</span><span class="sxs-lookup"><span data-stu-id="923d5-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="923d5-104">このトピックでは、これらのプロパティから返される <xref:System.TimeZoneInfo> オブジェクトにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="923d5-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="923d5-105">世界協定時刻 (UTC) の TimeZoneInfo オブジェクトにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="923d5-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="923d5-106">`static` (Visual Basic で`Shared`) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> プロパティを使用して、世界協定時刻にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="923d5-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="923d5-107">プロパティによって返される <xref:System.TimeZoneInfo> オブジェクトをオブジェクト変数に割り当てるのではなく、<xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> プロパティを使用して、世界協定時刻に引き続きアクセスします。</span><span class="sxs-lookup"><span data-stu-id="923d5-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="923d5-108">ローカル タイム ゾーンにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="923d5-108">To access the local time zone</span></span>

1. <span data-ttu-id="923d5-109">ローカルシステムのタイムゾーンにアクセスするには、`static` (Visual Basic で`Shared`) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="923d5-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="923d5-110">プロパティによって返される <xref:System.TimeZoneInfo> オブジェクトをオブジェクト変数に割り当てるのではなく、引き続き <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> プロパティを使用してローカルタイムゾーンにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="923d5-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="923d5-111">例</span><span class="sxs-lookup"><span data-stu-id="923d5-111">Example</span></span>

<span data-ttu-id="923d5-112">次のコードでは、<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> と <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> のプロパティを使用して、米国およびカナダ東部標準時のタイムゾーンから時刻を変換し、タイムゾーン名をコンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="923d5-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="923d5-113">ローカルタイムゾーンには、ローカルタイムゾーンを <xref:System.TimeZoneInfo> オブジェクト変数に割り当てるのではなく、常に <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> プロパティを使用してアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="923d5-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="923d5-114">同様に、UTC ゾーンを <xref:System.TimeZoneInfo> オブジェクト変数に割り当てるのではなく、常に <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> プロパティを使用して世界協定時刻にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="923d5-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="923d5-115">これにより、<xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> メソッドの呼び出しによって <xref:System.TimeZoneInfo> オブジェクト変数が無効になるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="923d5-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="923d5-116">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="923d5-116">Compiling the code</span></span>

<span data-ttu-id="923d5-117">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="923d5-117">This example requires:</span></span>

- <span data-ttu-id="923d5-118"><xref:System> 名前空間は、`using` ステートメント (コードでC#必要) を使用してインポートされます。</span><span class="sxs-lookup"><span data-stu-id="923d5-118">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="923d5-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="923d5-119">See also</span></span>

- [<span data-ttu-id="923d5-120">日付、時刻およびタイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="923d5-120">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="923d5-121">ローカル システムで定義されているタイム ゾーンの検索</span><span class="sxs-lookup"><span data-stu-id="923d5-121">Finding the time zones defined on a local system</span></span>](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [<span data-ttu-id="923d5-122">方法: TimeZoneInfo オブジェクトをインスタンス化する</span><span class="sxs-lookup"><span data-stu-id="923d5-122">How to: Instantiate a TimeZoneInfo object</span></span>](../../../docs/standard/datetime/instantiate-time-zone-info.md)
