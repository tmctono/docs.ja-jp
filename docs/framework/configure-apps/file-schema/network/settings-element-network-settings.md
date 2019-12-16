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
ms.openlocfilehash: d510c445c585a36005ed415b14188efc4be03984
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089119"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="61a69-102">\<settings> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="61a69-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="61a69-103"><xref:System.Net?displayProperty=nameWithType> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="61a69-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  

<span data-ttu-id="61a69-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="61a69-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="61a69-105">&nbsp;&nbsp;[ **\<system.net>** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="61a69-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="61a69-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<settings>**</span><span class="sxs-lookup"><span data-stu-id="61a69-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="61a69-107">構文</span><span class="sxs-lookup"><span data-stu-id="61a69-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61a69-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="61a69-108">Attributes and Elements</span></span>  
 <span data-ttu-id="61a69-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="61a69-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61a69-110">属性</span><span class="sxs-lookup"><span data-stu-id="61a69-110">Attributes</span></span>  
 <span data-ttu-id="61a69-111">なし。</span><span class="sxs-lookup"><span data-stu-id="61a69-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="61a69-112">子要素</span><span class="sxs-lookup"><span data-stu-id="61a69-112">Child Elements</span></span>  
  
|<span data-ttu-id="61a69-113">要素</span><span class="sxs-lookup"><span data-stu-id="61a69-113">Element</span></span>|<span data-ttu-id="61a69-114">説明</span><span class="sxs-lookup"><span data-stu-id="61a69-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61a69-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="61a69-115">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="61a69-116"><xref:System.Net.HttpListener> クラスによって使用されるパラメーターをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="61a69-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="61a69-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="61a69-117">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="61a69-118">Web 要求パラメーターをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="61a69-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="61a69-119">ipv6</span><span class="sxs-lookup"><span data-stu-id="61a69-119">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="61a69-120">インターネットプロトコルバージョン 6 (IPv6) のサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="61a69-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="61a69-121">\<performanceCounter > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="61a69-121">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="61a69-122">ネットワークパフォーマンスカウンターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="61a69-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="61a69-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="61a69-123">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="61a69-124">ネットワークリソースへの接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="61a69-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="61a69-125">socket</span><span class="sxs-lookup"><span data-stu-id="61a69-125">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="61a69-126">ソケット操作が完了ポートを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="61a69-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="61a69-127">\<webProxyScript > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="61a69-127">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="61a69-128">Web プロキシを検出するために使用するスクリプトの特性を構成します。</span><span class="sxs-lookup"><span data-stu-id="61a69-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="61a69-129">親要素</span><span class="sxs-lookup"><span data-stu-id="61a69-129">Parent Elements</span></span>  
  
|<span data-ttu-id="61a69-130">要素</span><span class="sxs-lookup"><span data-stu-id="61a69-130">Element</span></span>|<span data-ttu-id="61a69-131">説明</span><span class="sxs-lookup"><span data-stu-id="61a69-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61a69-132">system.net</span><span class="sxs-lookup"><span data-stu-id="61a69-132">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="61a69-133">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="61a69-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61a69-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="61a69-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="61a69-135">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="61a69-135">Configuration Files</span></span>  
 <span data-ttu-id="61a69-136">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="61a69-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a69-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="61a69-137">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="61a69-138">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="61a69-138">Network Settings Schema</span></span>](index.md)
