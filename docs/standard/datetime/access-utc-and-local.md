---
title: '方法: 定義済みの UTC オブジェクトおよびローカル タイム ゾーン オブジェクトにアクセスする'
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8aa19118ce0837b9ce0eb523f3e086fcbcecb9e8
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106565"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="e76da-102">方法: 定義済みの UTC オブジェクトおよびローカル タイム ゾーン オブジェクトにアクセスする</span><span class="sxs-lookup"><span data-stu-id="e76da-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="e76da-103">クラス<xref:System.TimeZoneInfo>には、 <xref:System.TimeZoneInfo.Utc%2A>とという<xref:System.TimeZoneInfo.Local%2A>2 つのプロパティが用意されており、これにより、定義済みのタイムゾーンオブジェクトにコードからアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="e76da-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="e76da-104">このトピックでは、これらのプロパティから返される <xref:System.TimeZoneInfo> オブジェクトにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e76da-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="e76da-105">世界協定時刻 (UTC) の TimeZoneInfo オブジェクトにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="e76da-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="e76da-106">( `static` VisualBasic`Shared` )プロパティを使用して、協定世界時に<xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>アクセスします。</span><span class="sxs-lookup"><span data-stu-id="e76da-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="e76da-107">プロパティによって<xref:System.TimeZoneInfo>返されたオブジェクトをオブジェクト変数に割り当てるのではなく、 <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>プロパティを使用して世界協定時刻にアクセスし続けます。</span><span class="sxs-lookup"><span data-stu-id="e76da-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="e76da-108">ローカル タイム ゾーンにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="e76da-108">To access the local time zone</span></span>

1. <span data-ttu-id="e76da-109">ローカルシステム`static`の`Shared`タイムゾーンに<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>アクセスするには、(Visual Basic) プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="e76da-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="e76da-110">プロパティによって<xref:System.TimeZoneInfo>返されたオブジェクトをオブジェクト変数に割り当てるのではなく、引き続き<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>プロパティを使用してローカルタイムゾーンにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e76da-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="e76da-111">例</span><span class="sxs-lookup"><span data-stu-id="e76da-111">Example</span></span>

<span data-ttu-id="e76da-112">次のコードでは<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 、 <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>プロパティとプロパティを使用して、米国およびカナダ東部標準時のタイムゾーンから時刻を変換し、タイムゾーン名をコンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="e76da-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="e76da-113">ローカルタイムゾーンは、ローカルタイムゾーンを<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> <xref:System.TimeZoneInfo>オブジェクト変数に割り当てるのではなく、常にプロパティを使用してアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e76da-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="e76da-114">同様に、UTC ゾーン<xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> <xref:System.TimeZoneInfo>をオブジェクト変数に割り当てるのではなく、常にプロパティを使用して世界協定時刻にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e76da-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="e76da-115">これにより<xref:System.TimeZoneInfo> 、メソッドの<xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>呼び出しによってオブジェクト変数が無効になるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="e76da-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="e76da-116">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="e76da-116">Compiling the code</span></span>

<span data-ttu-id="e76da-117">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e76da-117">This example requires:</span></span>

- <span data-ttu-id="e76da-118">ステートメントを使用してC# 名前空間をインポートする(コードに必要<xref:System>) `using` 。</span><span class="sxs-lookup"><span data-stu-id="e76da-118">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="e76da-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e76da-119">See also</span></span>

- [<span data-ttu-id="e76da-120">日付、時刻、およびタイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="e76da-120">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="e76da-121">ローカル システムで定義されているタイム ゾーンの検索</span><span class="sxs-lookup"><span data-stu-id="e76da-121">Finding the time zones defined on a local system</span></span>](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [<span data-ttu-id="e76da-122">方法: TimeZoneInfo オブジェクトのインスタンス化</span><span class="sxs-lookup"><span data-stu-id="e76da-122">How to: Instantiate a TimeZoneInfo object</span></span>](../../../docs/standard/datetime/instantiate-time-zone-info.md)
