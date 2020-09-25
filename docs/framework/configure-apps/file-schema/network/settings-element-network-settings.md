---
title: <settings> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: c5fe0b9eccd1c429c0041fcfab06b0cc20a20aa2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167276"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="2d97b-102">\<settings> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="2d97b-102">\<settings> Element (Network Settings)</span></span>

<span data-ttu-id="2d97b-103"><xref:System.Net?displayProperty=nameWithType> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="2d97b-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**

## <a name="syntax"></a><span data-ttu-id="2d97b-104">構文</span><span class="sxs-lookup"><span data-stu-id="2d97b-104">Syntax</span></span>  
  
```xml  
<settings>  
  <httpListener>...</httpListener>  
  <httpWebRequest>...</httpWebRequest>  
  <ipv6>...</ipv6>  
  <performanceCounters>...</performanceCounters>  
  <servicePointManager>...</servicePointManager>  
  <socket>...</socket>  
  <webProxyScript>...</webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d97b-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2d97b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="2d97b-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d97b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d97b-107">属性</span><span class="sxs-lookup"><span data-stu-id="2d97b-107">Attributes</span></span>  

 <span data-ttu-id="2d97b-108">なし。</span><span class="sxs-lookup"><span data-stu-id="2d97b-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2d97b-109">子要素</span><span class="sxs-lookup"><span data-stu-id="2d97b-109">Child Elements</span></span>  
  
|<span data-ttu-id="2d97b-110">要素</span><span class="sxs-lookup"><span data-stu-id="2d97b-110">Element</span></span>|<span data-ttu-id="2d97b-111">説明</span><span class="sxs-lookup"><span data-stu-id="2d97b-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d97b-112">httpListener</span><span class="sxs-lookup"><span data-stu-id="2d97b-112">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="2d97b-113">クラスによって使用されるパラメーターをカスタマイズ <xref:System.Net.HttpListener> します。</span><span class="sxs-lookup"><span data-stu-id="2d97b-113">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="2d97b-114">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="2d97b-114">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="2d97b-115">Web 要求パラメーターをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="2d97b-115">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="2d97b-116">ipv6</span><span class="sxs-lookup"><span data-stu-id="2d97b-116">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="2d97b-117">インターネットプロトコルバージョン 6 (IPv6) のサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2d97b-117">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="2d97b-118">\<performanceCounter> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="2d97b-118">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="2d97b-119">ネットワークパフォーマンスカウンターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2d97b-119">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="2d97b-120">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="2d97b-120">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="2d97b-121">ネットワークリソースへの接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="2d97b-121">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="2d97b-122">socket</span><span class="sxs-lookup"><span data-stu-id="2d97b-122">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="2d97b-123">ソケット操作が完了ポートを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2d97b-123">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="2d97b-124">\<webProxyScript> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="2d97b-124">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="2d97b-125">Web プロキシを検出するために使用するスクリプトの特性を構成します。</span><span class="sxs-lookup"><span data-stu-id="2d97b-125">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2d97b-126">親要素</span><span class="sxs-lookup"><span data-stu-id="2d97b-126">Parent Elements</span></span>  
  
|<span data-ttu-id="2d97b-127">要素</span><span class="sxs-lookup"><span data-stu-id="2d97b-127">Element</span></span>|<span data-ttu-id="2d97b-128">説明</span><span class="sxs-lookup"><span data-stu-id="2d97b-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d97b-129">system.net</span><span class="sxs-lookup"><span data-stu-id="2d97b-129">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="2d97b-130">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d97b-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d97b-131">解説</span><span class="sxs-lookup"><span data-stu-id="2d97b-131">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2d97b-132">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="2d97b-132">Configuration Files</span></span>  

 <span data-ttu-id="2d97b-133">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d97b-133">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d97b-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d97b-134">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="2d97b-135">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="2d97b-135">Network Settings Schema</span></span>](index.md)
