---
title: <transport> の <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 837d01540fa63579877ab4085bd8034c78f2fbe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915559"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="e262d-102">\<netpeertcpbinding > の\<トランスポート ></span><span class="sxs-lookup"><span data-stu-id="e262d-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="e262d-103">Netpeertcpbinding > を使用[ \<](netpeertcpbinding.md)する場合のトランスポートレベルのセキュリティ設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e262d-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="e262d-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e262d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e262d-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e262d-105">\<bindings></span></span>  
<span data-ttu-id="e262d-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="e262d-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="e262d-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="e262d-107">\<binding></span></span>  
<span data-ttu-id="e262d-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="e262d-108">\<security></span></span>  
<span data-ttu-id="e262d-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="e262d-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e262d-110">構文</span><span class="sxs-lookup"><span data-stu-id="e262d-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e262d-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e262d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e262d-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e262d-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e262d-113">属性</span><span class="sxs-lookup"><span data-stu-id="e262d-113">Attributes</span></span>  
  
|<span data-ttu-id="e262d-114">属性</span><span class="sxs-lookup"><span data-stu-id="e262d-114">Attribute</span></span>|<span data-ttu-id="e262d-115">説明</span><span class="sxs-lookup"><span data-stu-id="e262d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e262d-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="e262d-116">credentialType</span></span>|<span data-ttu-id="e262d-117">任意。</span><span class="sxs-lookup"><span data-stu-id="e262d-117">Optional.</span></span> <span data-ttu-id="e262d-118">ピア トランスポートにより送信されるメッセージの検証に使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="e262d-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="e262d-119">この属性は <xref:System.ServiceModel.PeerTransportCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="e262d-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="e262d-120">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="e262d-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="e262d-121">値</span><span class="sxs-lookup"><span data-stu-id="e262d-121">Value</span></span>|<span data-ttu-id="e262d-122">説明</span><span class="sxs-lookup"><span data-stu-id="e262d-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e262d-123">証明書</span><span class="sxs-lookup"><span data-stu-id="e262d-123">Certificate</span></span>|<span data-ttu-id="e262d-124">ピア チャネル トランスポートの認証には X 509 証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="e262d-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="e262d-125">Password</span><span class="sxs-lookup"><span data-stu-id="e262d-125">Password</span></span>|<span data-ttu-id="e262d-126">ピア チャネル トランスポートの認証には正しいパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="e262d-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e262d-127">子要素</span><span class="sxs-lookup"><span data-stu-id="e262d-127">Child Elements</span></span>  
 <span data-ttu-id="e262d-128">なし</span><span class="sxs-lookup"><span data-stu-id="e262d-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e262d-129">親要素</span><span class="sxs-lookup"><span data-stu-id="e262d-129">Parent Elements</span></span>  
  
|<span data-ttu-id="e262d-130">要素</span><span class="sxs-lookup"><span data-stu-id="e262d-130">Element</span></span>|<span data-ttu-id="e262d-131">説明</span><span class="sxs-lookup"><span data-stu-id="e262d-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e262d-132">\<security></span><span class="sxs-lookup"><span data-stu-id="e262d-132">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="e262d-133">Netpeertcpbinding > のセキュリティ設定を[ \<](netpeertcpbinding.md)定義します。</span><span class="sxs-lookup"><span data-stu-id="e262d-133">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e262d-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="e262d-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="e262d-135">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="e262d-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e262d-136">バインディング</span><span class="sxs-lookup"><span data-stu-id="e262d-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e262d-137">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="e262d-137">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e262d-138">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="e262d-138">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e262d-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="e262d-139">\<binding></span></span>](../../../misc/binding.md)
