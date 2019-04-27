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
ms.openlocfilehash: a1733803d1f5a5bf64aeb69d0360cef3de3b3a69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674416"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="b19ec-102">\<設定 > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="b19ec-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="b19ec-103"><xref:System.Net?displayProperty=nameWithType> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="b19ec-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="b19ec-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b19ec-104">\<configuration></span></span>  
<span data-ttu-id="b19ec-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b19ec-105">\<system.net></span></span>  
<span data-ttu-id="b19ec-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="b19ec-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b19ec-107">構文</span><span class="sxs-lookup"><span data-stu-id="b19ec-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b19ec-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b19ec-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b19ec-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b19ec-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b19ec-110">属性</span><span class="sxs-lookup"><span data-stu-id="b19ec-110">Attributes</span></span>  
 <span data-ttu-id="b19ec-111">なし。</span><span class="sxs-lookup"><span data-stu-id="b19ec-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b19ec-112">子要素</span><span class="sxs-lookup"><span data-stu-id="b19ec-112">Child Elements</span></span>  
  
|<span data-ttu-id="b19ec-113">要素</span><span class="sxs-lookup"><span data-stu-id="b19ec-113">Element</span></span>|<span data-ttu-id="b19ec-114">説明</span><span class="sxs-lookup"><span data-stu-id="b19ec-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b19ec-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="b19ec-115">httpListener</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|<span data-ttu-id="b19ec-116"><xref:System.Net.HttpListener>クラスで使用されるパラメータをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="b19ec-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="b19ec-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="b19ec-117">httpWebRequest</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|<span data-ttu-id="b19ec-118">Web 要求のパラメーターをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="b19ec-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="b19ec-119">ipv6</span><span class="sxs-lookup"><span data-stu-id="b19ec-119">ipv6</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|<span data-ttu-id="b19ec-120">により、インターネット プロトコル バージョン 6 (IPv6) をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b19ec-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="b19ec-121">\<performanceCounter > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="b19ec-121">\<performanceCounter> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|<span data-ttu-id="b19ec-122">ネットワーク パフォーマンス カウンターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b19ec-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="b19ec-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="b19ec-123">servicePointManager</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|<span data-ttu-id="b19ec-124">ネットワーク リソースへの接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="b19ec-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="b19ec-125">socket</span><span class="sxs-lookup"><span data-stu-id="b19ec-125">socket</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|<span data-ttu-id="b19ec-126">ソケット操作が完了ポートを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b19ec-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="b19ec-127">\<webProxyScript > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="b19ec-127">\<webProxyScript> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|<span data-ttu-id="b19ec-128">Web プロキシを検出するために使用するスクリプトの特性を構成します。</span><span class="sxs-lookup"><span data-stu-id="b19ec-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b19ec-129">親要素</span><span class="sxs-lookup"><span data-stu-id="b19ec-129">Parent Elements</span></span>  
  
|<span data-ttu-id="b19ec-130">要素</span><span class="sxs-lookup"><span data-stu-id="b19ec-130">Element</span></span>|<span data-ttu-id="b19ec-131">説明</span><span class="sxs-lookup"><span data-stu-id="b19ec-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b19ec-132">system.net</span><span class="sxs-lookup"><span data-stu-id="b19ec-132">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="b19ec-133">.NET Framework がネットワークに接続する方法を指定するための設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b19ec-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b19ec-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="b19ec-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b19ec-135">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="b19ec-135">Configuration Files</span></span>  
 <span data-ttu-id="b19ec-136">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b19ec-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b19ec-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="b19ec-137">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="b19ec-138">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="b19ec-138">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
