---
title: <transport> の <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 49b31a889d192d190125214e89ba09305114eb7f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735978"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="5e605-102">\<transport> の \<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="5e605-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="5e605-103">を使用する場合のトランスポートレベルのセキュリティ設定を指定し [\<netPeerTcpBinding>](netpeertcpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="5e605-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="5e605-104">構文</span><span class="sxs-lookup"><span data-stu-id="5e605-104">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e605-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5e605-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5e605-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e605-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e605-107">属性</span><span class="sxs-lookup"><span data-stu-id="5e605-107">Attributes</span></span>  
  
|<span data-ttu-id="5e605-108">属性</span><span class="sxs-lookup"><span data-stu-id="5e605-108">Attribute</span></span>|<span data-ttu-id="5e605-109">説明</span><span class="sxs-lookup"><span data-stu-id="5e605-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e605-110">credentialType</span><span class="sxs-lookup"><span data-stu-id="5e605-110">credentialType</span></span>|<span data-ttu-id="5e605-111">省略可能。</span><span class="sxs-lookup"><span data-stu-id="5e605-111">Optional.</span></span> <span data-ttu-id="5e605-112">ピア トランスポートにより送信されるメッセージの検証に使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e605-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="5e605-113">この属性は <xref:System.ServiceModel.PeerTransportCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="5e605-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="5e605-114">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="5e605-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="5e605-115">値</span><span class="sxs-lookup"><span data-stu-id="5e605-115">Value</span></span>|<span data-ttu-id="5e605-116">Description</span><span class="sxs-lookup"><span data-stu-id="5e605-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5e605-117">Certificate</span><span class="sxs-lookup"><span data-stu-id="5e605-117">Certificate</span></span>|<span data-ttu-id="5e605-118">ピア チャネル トランスポートの認証には X 509 証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="5e605-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="5e605-119">Password</span><span class="sxs-lookup"><span data-stu-id="5e605-119">Password</span></span>|<span data-ttu-id="5e605-120">ピア チャネル トランスポートの認証には正しいパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="5e605-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e605-121">子要素</span><span class="sxs-lookup"><span data-stu-id="5e605-121">Child Elements</span></span>  
 <span data-ttu-id="5e605-122">なし</span><span class="sxs-lookup"><span data-stu-id="5e605-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5e605-123">親要素</span><span class="sxs-lookup"><span data-stu-id="5e605-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5e605-124">要素</span><span class="sxs-lookup"><span data-stu-id="5e605-124">Element</span></span>|<span data-ttu-id="5e605-125">Description</span><span class="sxs-lookup"><span data-stu-id="5e605-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="5e605-126">のセキュリティ設定を定義し [\<netPeerTcpBinding>](netpeertcpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="5e605-126">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e605-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e605-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="5e605-128">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="5e605-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5e605-129">バインド</span><span class="sxs-lookup"><span data-stu-id="5e605-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5e605-130">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="5e605-130">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5e605-131">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="5e605-131">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
