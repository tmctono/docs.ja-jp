---
title: '方法: 時間ベースのキャッシュ ポリシーをカスタマイズする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- customizing time-based cache policies
- cache [.NET Framework], time-based policies
ms.assetid: 8d84f936-2376-4356-9264-03162e0f9279
ms.openlocfilehash: 5df070bb2cfef42d60247cad39f2a2f76963bae8
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894741"
---
# <a name="how-to-customize-a-time-based-cache-policy"></a><span data-ttu-id="2871d-102">方法: 時間ベースのキャッシュ ポリシーをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="2871d-102">How to: Customize a Time-Based Cache Policy</span></span>
<span data-ttu-id="2871d-103">時間ベースのキャッシュ ポリシーを作成する場合、最大有効期間、最小鮮度、最大期限延長、またはキャッシュ同期日付の値を指定することで、キャッシュの動作をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="2871d-103">When creating a time-based cache policy, you can customize caching behavior by specifying values for maximum age, minimum freshness, maximum staleness, or cache synchronization date.</span></span> <span data-ttu-id="2871d-104"><xref:System.Net.Cache.HttpRequestCachePolicy> オブジェクトは、これらの値の有効な組み合わせを指定できるようにする複数のコンストラクターを提供します。</span><span class="sxs-lookup"><span data-stu-id="2871d-104">The <xref:System.Net.Cache.HttpRequestCachePolicy> object provides several constructors that allow you to specify valid combinations of these values.</span></span>  
  
### <a name="to-create-a-time-based-cache-policy-that-uses-a-cache-synchronization-date"></a><span data-ttu-id="2871d-105">キャッシュ同期日付を使用する時間ベースのキャッシュ ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="2871d-105">To create a time-based cache policy that uses a cache synchronization date</span></span>  
  
- <span data-ttu-id="2871d-106"><xref:System.Net.Cache.HttpRequestCachePolicy> コンストラクターに <xref:System.DateTime> オブジェクトを渡して、キャッシュ同期日付を使用する時間ベースのキャッシュ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2871d-106">Create a time-based cache policy that uses a cache synchronization date by passing a <xref:System.DateTime> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor.</span></span>  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateLastSyncPolicy(DateTime when)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(when);  
        Console.WriteLine("When: {0}", when);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateLastSyncPolicy([when] As DateTime) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy([when])  
        Console.WriteLine("When: {0}", [when])  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 <span data-ttu-id="2871d-107">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2871d-107">The output is similar to the following:</span></span>  
  
```output
When: 1/14/2004 8:07:30 AM  
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM  
```  
  
### <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness"></a><span data-ttu-id="2871d-108">最小鮮度に基づく時間ベースのキャッシュ ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="2871d-108">To create a time-based cache policy that is based on minimum freshness</span></span>  
  
- <span data-ttu-id="2871d-109">`cacheAgeControl` パラメーター値として <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> を指定し、<xref:System.Net.Cache.HttpRequestCachePolicy> コンストラクターに <xref:System.TimeSpan> オブジェクトを渡して、最小鮮度に基づく時間ベースのキャッシュ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2871d-109">Create a time-based cache policy that is based on minimum freshness by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> as the `cacheAgeControl` parameter value and passing a <xref:System.TimeSpan> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor.</span></span>  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateMinFreshPolicy(TimeSpan span)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateMinFreshPolicy(span As TimeSpan) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span)  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 <span data-ttu-id="2871d-110">呼び出しと出力例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="2871d-110">For the following invocation:</span></span>  
  
```csharp
CreateMinFreshPolicy(new TimeSpan(1,0,0));  
```  

 <span data-ttu-id="2871d-111">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2871d-111">The output is:</span></span>
  
```output
Level:Default MinFresh:3600  
```  
  
### <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness-and-maximum-age"></a><span data-ttu-id="2871d-112">最小鮮度と最大有効期間に基づく時間ベースのキャッシュ ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="2871d-112">To create a time-based cache policy that is based on minimum freshness and maximum age</span></span>  
  
- <span data-ttu-id="2871d-113">`cacheAgeControl` パラメーター値として <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> を指定し、<xref:System.Net.Cache.HttpRequestCachePolicy> コンストラクターに 2 つの <xref:System.TimeSpan> オブジェクト (1 つはリソースの最大有効期間を指定し、もう 1 つはキャッシュから返されたオブジェクトで許可される最小鮮度を指定する) を渡して、最小鮮度と最大有効期間に基づく時間ベースのキャッシュ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2871d-113">Create a time-based cache policy that is based on minimum freshness and maximum age by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> as the `cacheAgeControl` parameter value and passing two <xref:System.TimeSpan> objects to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor, one to specify the maximum age for resources and a second to specify the minimum freshness permitted for an object returned from the cache.</span></span>  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateFreshAndAgePolicy(TimeSpan freshMinimum, TimeSpan ageMaximum)  
    {  
        HttpRequestCachePolicy policy =   
        new HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateFreshAndAgePolicy(freshMinimum As TimeSpan, ageMaximum As TimeSpan) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum)  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 <span data-ttu-id="2871d-114">呼び出しと出力例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="2871d-114">For the following invocation:</span></span>  
  
```csharp
CreateFreshAndAgePolicy(new TimeSpan(5,0,0), new TimeSpan(10,0,0));  
```  

<span data-ttu-id="2871d-115">出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2871d-115">The output is:</span></span>
  
```output
Level:Default MaxAge:36000 MinFresh:18000  
```  
  
## <a name="see-also"></a><span data-ttu-id="2871d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2871d-116">See also</span></span>

- [<span data-ttu-id="2871d-117">ネットワーク アプリケーションのキャッシュ管理</span><span class="sxs-lookup"><span data-stu-id="2871d-117">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)
- [<span data-ttu-id="2871d-118">キャッシュ ポリシー</span><span class="sxs-lookup"><span data-stu-id="2871d-118">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)
- [<span data-ttu-id="2871d-119">場所ベースのキャッシュ ポリシー</span><span class="sxs-lookup"><span data-stu-id="2871d-119">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)
- [<span data-ttu-id="2871d-120">時間ベースのキャッシュ ポリシー</span><span class="sxs-lookup"><span data-stu-id="2871d-120">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)
- [<span data-ttu-id="2871d-121">\<requestCaching> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="2871d-121">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
