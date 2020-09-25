---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 12709d58d9192825598b15a50baa10a54450226e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178074"
---
# \<net.tcp>

<span data-ttu-id="67075-102">複数のプロセスが同じ TCP ポートを共有できる NET.TCP ポート共有サービスの構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="67075-102">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<net.tcp>**  
  
## <a name="syntax"></a><span data-ttu-id="67075-103">構文</span><span class="sxs-lookup"><span data-stu-id="67075-103">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="Integer"
             maxPendingAccepts="Integer"
             maxPendingConnections="Integer"
             receiveTimeout="TimeSpan"
             teredoEnabled="Boolean">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only)-->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="67075-104">種類</span><span class="sxs-lookup"><span data-stu-id="67075-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67075-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="67075-105">Attributes and Elements</span></span>  

 <span data-ttu-id="67075-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="67075-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67075-107">属性</span><span class="sxs-lookup"><span data-stu-id="67075-107">Attributes</span></span>  
  
|<span data-ttu-id="67075-108">属性</span><span class="sxs-lookup"><span data-stu-id="67075-108">Attribute</span></span>|<span data-ttu-id="67075-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="67075-109">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="67075-110">共有接続から受け入れられ、まだ Windows Communication Foundation (WCF) サービスにディスパッチされていない未処理の接続の最大数を指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="67075-110">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="67075-111">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="67075-111">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="67075-112">整数は、共有サービスの待機エンドポイントで同時に受け入れる未処理のスレッドの最大数を示しています。</span><span class="sxs-lookup"><span data-stu-id="67075-112">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="67075-113">既定値は 2 です。</span><span class="sxs-lookup"><span data-stu-id="67075-113">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="67075-114">アプリケーションによる受け入れをリスナーで待機できる最大接続数。</span><span class="sxs-lookup"><span data-stu-id="67075-114">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="67075-115">このクォータ値を超過すると、新規の受信接続は受け入れられるのを待機せずに切断されます。</span><span class="sxs-lookup"><span data-stu-id="67075-115">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="67075-116">メッセージ セキュリティのような接続機能では、クライアントは複数の接続を開くことがあります。</span><span class="sxs-lookup"><span data-stu-id="67075-116">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="67075-117">このクォータ値を設定する場合、サービス管理者はこのような追加の接続も考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67075-117">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="67075-118">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="67075-118">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="67075-119">フレーム データを読み取り、基礎となる接続から接続ディスパッチを実行するタイムアウトを指定する <xref:System.TimeSpan> です。</span><span class="sxs-lookup"><span data-stu-id="67075-119">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="67075-120">既定値は "00:00:10" です。</span><span class="sxs-lookup"><span data-stu-id="67075-120">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="67075-121">ポート共有サービスが Microsoft Teredo サービスを使用して、WCF サービスの代わりに TCP ポートをリッスンするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="67075-121">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="67075-122">既定では、 `false`です。</span><span class="sxs-lookup"><span data-stu-id="67075-122">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67075-123">子要素</span><span class="sxs-lookup"><span data-stu-id="67075-123">Child Elements</span></span>  
  
|<span data-ttu-id="67075-124">要素</span><span class="sxs-lookup"><span data-stu-id="67075-124">Element</span></span>|<span data-ttu-id="67075-125">説明</span><span class="sxs-lookup"><span data-stu-id="67075-125">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="67075-126">`securityIdentifier`WCF サービスをホストするプロセスのユーザーアカウントを指定する属性を含む構成要素のコレクション。共有サービスへの接続アクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="67075-126">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="67075-127">親要素</span><span class="sxs-lookup"><span data-stu-id="67075-127">Parent Elements</span></span>  
  
|<span data-ttu-id="67075-128">要素</span><span class="sxs-lookup"><span data-stu-id="67075-128">Element</span></span>|<span data-ttu-id="67075-129">説明</span><span class="sxs-lookup"><span data-stu-id="67075-129">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="67075-130">リスナー プロセス SMSvcHost.exe の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67075-130">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67075-131">解説</span><span class="sxs-lookup"><span data-stu-id="67075-131">Remarks</span></span>  

 <span data-ttu-id="67075-132">ポート共有の詳細については、「 [Net.tcp ポート共有](../../../wcf/feature-details/net-tcp-port-sharing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67075-132">For more information on port sharing, see [Net.TCP Port Sharing](../../../wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="67075-133">ポート共有サービスの構成方法については、「 [Net.tcp ポート共有サービスの構成](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67075-133">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67075-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="67075-134">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="67075-135">Net.TCP ポート共有</span><span class="sxs-lookup"><span data-stu-id="67075-135">Net.TCP Port Sharing</span></span>](../../../wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="67075-136">Net.TCP ポート共有サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="67075-136">Configuring the Net.TCP Port Sharing Service</span></span>](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
