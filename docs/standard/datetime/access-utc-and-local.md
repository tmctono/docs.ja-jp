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
ms.openlocfilehash: c10c07c08a4e676cf3c84a5722814eaed85f74a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026610"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="33fd4-102">方法: 定義済みの UTC オブジェクトおよびローカル タイム ゾーン オブジェクトにアクセスする</span><span class="sxs-lookup"><span data-stu-id="33fd4-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="33fd4-103"><xref:System.TimeZoneInfo>クラスは、2 つのプロパティを提供します。<xref:System.TimeZoneInfo.Utc%2A>と<xref:System.TimeZoneInfo.Local%2A>、定義済みのタイム ゾーン オブジェクトへのコード アクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="33fd4-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="33fd4-104">このトピックでは、これらのプロパティから返される <xref:System.TimeZoneInfo> オブジェクトにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="33fd4-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="33fd4-105">世界協定時刻 (UTC) の TimeZoneInfo オブジェクトにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="33fd4-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="33fd4-106">使用して、 `static` (`Shared` Visual Basic で)<xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>世界協定時刻にアクセスするプロパティ。</span><span class="sxs-lookup"><span data-stu-id="33fd4-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="33fd4-107">割り当てではなく、<xref:System.TimeZoneInfo>引き続きを世界協定時刻にアクセスするオブジェクトが、オブジェクト変数に、プロパティによって返される、<xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="33fd4-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="33fd4-108">ローカル タイム ゾーンにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="33fd4-108">To access the local time zone</span></span>

1. <span data-ttu-id="33fd4-109">使用して、 `static` (`Shared` Visual Basic で)<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>ローカル システムのタイム ゾーンにアクセスするプロパティ。</span><span class="sxs-lookup"><span data-stu-id="33fd4-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="33fd4-110">割り当てではなく、<xref:System.TimeZoneInfo>引き続きを通じて、ローカル タイム ゾーンにアクセスするオブジェクトが、オブジェクト変数に、プロパティによって返される、<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="33fd4-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="33fd4-111">例</span><span class="sxs-lookup"><span data-stu-id="33fd4-111">Example</span></span>

<span data-ttu-id="33fd4-112">次のコードでは、<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>と<xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>米国およびカナダ東部標準時ゾーンの時刻を変換するだけでなく、タイム ゾーン名をコンソールに表示するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="33fd4-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="33fd4-113">使用してローカル タイム ゾーンを常にアクセスする必要があります、<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>にゾーンのローカル時刻を割り当てるのではなく、プロパティ、<xref:System.TimeZoneInfo>オブジェクト変数です。</span><span class="sxs-lookup"><span data-stu-id="33fd4-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="33fd4-114">同様に、アクセスするには常に協定世界時で、<xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>にゾーンの UTC を割り当てるのではなく、プロパティ、<xref:System.TimeZoneInfo>オブジェクト変数です。</span><span class="sxs-lookup"><span data-stu-id="33fd4-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="33fd4-115">これにより、<xref:System.TimeZoneInfo>オブジェクト変数への呼び出しによって無効になることから、<xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="33fd4-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="33fd4-116">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="33fd4-116">Compiling the code</span></span>

<span data-ttu-id="33fd4-117">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="33fd4-117">This example requires:</span></span>

* <span data-ttu-id="33fd4-118">System.Core.dll への参照をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="33fd4-118">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="33fd4-119"><xref:System>と共に名前空間をインポートする、`using`ステートメント (c# コードで必要)。</span><span class="sxs-lookup"><span data-stu-id="33fd4-119">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="33fd4-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="33fd4-120">See also</span></span>

- [<span data-ttu-id="33fd4-121">日付、時刻、およびタイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="33fd4-121">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="33fd4-122">ローカル システムで定義されているタイム ゾーンの検索</span><span class="sxs-lookup"><span data-stu-id="33fd4-122">Finding the time zones defined on a local system</span></span>](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [<span data-ttu-id="33fd4-123">方法: TimeZoneInfo オブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="33fd4-123">How to: Instantiate a TimeZoneInfo object</span></span>](../../../docs/standard/datetime/instantiate-time-zone-info.md)
