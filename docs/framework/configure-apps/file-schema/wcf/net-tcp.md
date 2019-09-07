---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 4a3a17655f5469fe84c0b684ebdac9848bbfba84
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397692"
---
# <a name="nettcp"></a><span data-ttu-id="f1b69-102">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="f1b69-102">\<net.tcp></span></span>
<span data-ttu-id="f1b69-103">複数のプロセスが同じ TCP ポートを共有できる NET.TCP ポート共有サービスの構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1b69-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
<span data-ttu-id="f1b69-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f1b69-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f1b69-105">&nbsp;&nbsp;[ **\<System.servicemodel. activation >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="f1b69-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="f1b69-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<net.tcp >**</span><span class="sxs-lookup"><span data-stu-id="f1b69-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<net.tcp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1b69-107">構文</span><span class="sxs-lookup"><span data-stu-id="f1b69-107">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="f1b69-108">型</span><span class="sxs-lookup"><span data-stu-id="f1b69-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1b69-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f1b69-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f1b69-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1b69-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1b69-111">属性</span><span class="sxs-lookup"><span data-stu-id="f1b69-111">Attributes</span></span>  
  
|<span data-ttu-id="f1b69-112">属性</span><span class="sxs-lookup"><span data-stu-id="f1b69-112">Attribute</span></span>|<span data-ttu-id="f1b69-113">説明</span><span class="sxs-lookup"><span data-stu-id="f1b69-113">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="f1b69-114">共有接続から受け入れられ、まだ Windows Communication Foundation (WCF) サービスにディスパッチされていない未処理の接続の最大数を指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="f1b69-114">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="f1b69-115">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="f1b69-115">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="f1b69-116">整数は、共有サービスの待機エンドポイントで同時に受け入れる未処理のスレッドの最大数を示しています。</span><span class="sxs-lookup"><span data-stu-id="f1b69-116">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="f1b69-117">既定値は 2 です。</span><span class="sxs-lookup"><span data-stu-id="f1b69-117">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="f1b69-118">アプリケーションによる受け入れをリスナーで待機できる最大接続数。</span><span class="sxs-lookup"><span data-stu-id="f1b69-118">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="f1b69-119">このクォータ値を超過すると、新規の受信接続は受け入れられるのを待機せずに切断されます。</span><span class="sxs-lookup"><span data-stu-id="f1b69-119">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="f1b69-120">メッセージ セキュリティのような接続機能では、クライアントは複数の接続を開くことがあります。</span><span class="sxs-lookup"><span data-stu-id="f1b69-120">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="f1b69-121">このクォータ値を設定する場合、サービス管理者はこのような追加の接続も考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1b69-121">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="f1b69-122">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="f1b69-122">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="f1b69-123">フレーム データを読み取り、基礎となる接続から接続ディスパッチを実行するタイムアウトを指定する <xref:System.TimeSpan> です。</span><span class="sxs-lookup"><span data-stu-id="f1b69-123">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="f1b69-124">既定値は "00:00:10" です。</span><span class="sxs-lookup"><span data-stu-id="f1b69-124">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="f1b69-125">ポート共有サービスが Microsoft Teredo サービスを使用して、WCF サービスの代わりに TCP ポートをリッスンするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="f1b69-125">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="f1b69-126">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="f1b69-126">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1b69-127">子要素</span><span class="sxs-lookup"><span data-stu-id="f1b69-127">Child Elements</span></span>  
  
|<span data-ttu-id="f1b69-128">要素</span><span class="sxs-lookup"><span data-stu-id="f1b69-128">Element</span></span>|<span data-ttu-id="f1b69-129">説明</span><span class="sxs-lookup"><span data-stu-id="f1b69-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1b69-130">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="f1b69-130">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="f1b69-131">WCF サービスをホストするプロセスのユーザー `securityIdentifier`アカウントを指定する属性を含む構成要素のコレクション。共有サービスへの接続アクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="f1b69-131">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1b69-132">親要素</span><span class="sxs-lookup"><span data-stu-id="f1b69-132">Parent Elements</span></span>  
  
|<span data-ttu-id="f1b69-133">要素</span><span class="sxs-lookup"><span data-stu-id="f1b69-133">Element</span></span>|<span data-ttu-id="f1b69-134">説明</span><span class="sxs-lookup"><span data-stu-id="f1b69-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1b69-135">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="f1b69-135">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="f1b69-136">リスナー プロセス SMSvcHost.exe の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1b69-136">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1b69-137">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1b69-137">Remarks</span></span>  
 <span data-ttu-id="f1b69-138">ポート共有の詳細については、「 [Net.tcp ポート共有](../../../wcf/feature-details/net-tcp-port-sharing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1b69-138">For more information on port sharing, see [Net.TCP Port Sharing](../../../wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="f1b69-139">ポート共有サービスの構成方法については、「 [Net.tcp ポート共有サービスの構成](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1b69-139">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1b69-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1b69-140">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="f1b69-141">Net.TCP ポート共有</span><span class="sxs-lookup"><span data-stu-id="f1b69-141">Net.TCP Port Sharing</span></span>](../../../wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="f1b69-142">Net.TCP ポート共有サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="f1b69-142">Configuring the Net.TCP Port Sharing Service</span></span>](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
