---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: dd984b2ab89060451b1b2d02c324e803766908ce
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397724"
---
# \<net.pipe>
<span data-ttu-id="c2e28-102">名前付きパイプ接続の有効期間を管理し、名前付きパイプを介して到着するアクティベーション要求を処理する名前付きパイプ アクティベーション サービスの構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="c2e28-102">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<net.pipe>**  
  
## <a name="syntax"></a><span data-ttu-id="c2e28-103">構文</span><span class="sxs-lookup"><span data-stu-id="c2e28-103">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.pipe maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              receiveTimeout="TimeSpan">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="c2e28-104">Type</span><span class="sxs-lookup"><span data-stu-id="c2e28-104">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2e28-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c2e28-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c2e28-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2e28-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2e28-107">属性</span><span class="sxs-lookup"><span data-stu-id="c2e28-107">Attributes</span></span>  
  
|<span data-ttu-id="c2e28-108">属性</span><span class="sxs-lookup"><span data-stu-id="c2e28-108">Attribute</span></span>|<span data-ttu-id="c2e28-109">説明</span><span class="sxs-lookup"><span data-stu-id="c2e28-109">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="c2e28-110">整数は、共有サービスの待機エンドポイントで同時に受け入れる未処理のスレッドの最大数を示しています。</span><span class="sxs-lookup"><span data-stu-id="c2e28-110">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="c2e28-111">既定値は 2 です。</span><span class="sxs-lookup"><span data-stu-id="c2e28-111">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="c2e28-112">ディスパッチを待機できる最大接続数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="c2e28-112">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="c2e28-113">既定値は、100 です。</span><span class="sxs-lookup"><span data-stu-id="c2e28-113">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="c2e28-114">フレーム データを読み取り、基礎となる接続から接続ディスパッチを実行するタイムアウトを指定する <xref:System.TimeSpan> です。</span><span class="sxs-lookup"><span data-stu-id="c2e28-114">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="c2e28-115">既定値は "00:00:10" です。</span><span class="sxs-lookup"><span data-stu-id="c2e28-115">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2e28-116">子要素</span><span class="sxs-lookup"><span data-stu-id="c2e28-116">Child Elements</span></span>  
  
|<span data-ttu-id="c2e28-117">要素</span><span class="sxs-lookup"><span data-stu-id="c2e28-117">Element</span></span>|<span data-ttu-id="c2e28-118">Description</span><span class="sxs-lookup"><span data-stu-id="c2e28-118">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="c2e28-119">`securityIdentifier`WCF サービスをホストするプロセスのユーザーアカウントを指定する属性を含む構成要素のコレクション。共有サービスへの接続アクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="c2e28-119">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c2e28-120">親要素</span><span class="sxs-lookup"><span data-stu-id="c2e28-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c2e28-121">要素</span><span class="sxs-lookup"><span data-stu-id="c2e28-121">Element</span></span>|<span data-ttu-id="c2e28-122">Description</span><span class="sxs-lookup"><span data-stu-id="c2e28-122">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="c2e28-123">リスナー プロセス SMSvcHost.exe の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2e28-123">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2e28-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2e28-124">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
