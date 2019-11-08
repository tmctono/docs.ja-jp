---
title: <transport> の <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: d40178e59b89c2912123e1927e9e960f6d880871
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735962"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="21eb2-102">\<netNamedPipeBinding > の \<トランスポート ></span><span class="sxs-lookup"><span data-stu-id="21eb2-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="21eb2-103">名前付きパイプのトランスポート セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="21eb2-103">Defines the transport security settings for a named pipe.</span></span>  
  
<span data-ttu-id="21eb2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="21eb2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="21eb2-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="21eb2-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="21eb2-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="21eb2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="21eb2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netNamedPipeBinding >** ](netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="21eb2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="21eb2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="21eb2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="21eb2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**セキュリティ >** ](security-of-netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="21eb2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)</span></span>\
<span data-ttu-id="21eb2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**トランスポート >**</span><span class="sxs-lookup"><span data-stu-id="21eb2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21eb2-111">構文</span><span class="sxs-lookup"><span data-stu-id="21eb2-111">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21eb2-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="21eb2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="21eb2-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="21eb2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21eb2-114">属性</span><span class="sxs-lookup"><span data-stu-id="21eb2-114">Attributes</span></span>  
  
|<span data-ttu-id="21eb2-115">属性</span><span class="sxs-lookup"><span data-stu-id="21eb2-115">Attribute</span></span>|<span data-ttu-id="21eb2-116">説明</span><span class="sxs-lookup"><span data-stu-id="21eb2-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="21eb2-117">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="21eb2-117">protectionLevel</span></span>|<span data-ttu-id="21eb2-118">名前付きパイプの保護レベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="21eb2-118">Defines protection level of the named pipe.</span></span> <span data-ttu-id="21eb2-119">メッセージに署名すると、転送中のメッセージが第三者によって改ざんされるリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="21eb2-119">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="21eb2-120">暗号化により、転送中にデータレベルのプライバシーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="21eb2-120">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="21eb2-121">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="21eb2-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="21eb2-122">-None: 保護がありません。</span><span class="sxs-lookup"><span data-stu-id="21eb2-122">-   None: No protection.</span></span><br /><span data-ttu-id="21eb2-123">-Sign: メッセージは署名されています。</span><span class="sxs-lookup"><span data-stu-id="21eb2-123">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="21eb2-124">-EncryptAndSign: メッセージは暗号化され、署名されます。</span><span class="sxs-lookup"><span data-stu-id="21eb2-124">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="21eb2-125">既定値は EncryptAndSign です。</span><span class="sxs-lookup"><span data-stu-id="21eb2-125">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21eb2-126">子要素</span><span class="sxs-lookup"><span data-stu-id="21eb2-126">Child Elements</span></span>  
 <span data-ttu-id="21eb2-127">None</span><span class="sxs-lookup"><span data-stu-id="21eb2-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="21eb2-128">親要素</span><span class="sxs-lookup"><span data-stu-id="21eb2-128">Parent Elements</span></span>  
  
|<span data-ttu-id="21eb2-129">要素</span><span class="sxs-lookup"><span data-stu-id="21eb2-129">Element</span></span>|<span data-ttu-id="21eb2-130">説明</span><span class="sxs-lookup"><span data-stu-id="21eb2-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21eb2-131">\< セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="21eb2-131">\<security></span></span>](security-of-netnamedpipebinding.md)|<span data-ttu-id="21eb2-132">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="21eb2-132">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21eb2-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="21eb2-133">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="21eb2-134">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="21eb2-134">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="21eb2-135">バインディング</span><span class="sxs-lookup"><span data-stu-id="21eb2-135">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="21eb2-136">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="21eb2-136">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="21eb2-137">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="21eb2-137">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="21eb2-138">\<binding ></span><span class="sxs-lookup"><span data-stu-id="21eb2-138">\<binding></span></span>](bindings.md)
