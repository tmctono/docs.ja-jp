---
title: <transport> の <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: d40178e59b89c2912123e1927e9e960f6d880871
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735962"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="e829e-102">\<transport> の \<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="e829e-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="e829e-103">名前付きパイプのトランスポート セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e829e-103">Defines the transport security settings for a named pipe.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="e829e-104">構文</span><span class="sxs-lookup"><span data-stu-id="e829e-104">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e829e-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e829e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e829e-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e829e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e829e-107">属性</span><span class="sxs-lookup"><span data-stu-id="e829e-107">Attributes</span></span>  
  
|<span data-ttu-id="e829e-108">属性</span><span class="sxs-lookup"><span data-stu-id="e829e-108">Attribute</span></span>|<span data-ttu-id="e829e-109">説明</span><span class="sxs-lookup"><span data-stu-id="e829e-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e829e-110">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="e829e-110">protectionLevel</span></span>|<span data-ttu-id="e829e-111">名前付きパイプの保護レベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="e829e-111">Defines protection level of the named pipe.</span></span> <span data-ttu-id="e829e-112">メッセージに署名を付けることで、メッセージの転送中に第三者によって改ざんされるリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="e829e-112">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="e829e-113">暗号化によって、トランスポート中にデータ レベルのプライバシーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="e829e-113">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="e829e-114">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e829e-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e829e-115">-None: 保護がありません。</span><span class="sxs-lookup"><span data-stu-id="e829e-115">-   None: No protection.</span></span><br /><span data-ttu-id="e829e-116">-Sign: メッセージは署名されています。</span><span class="sxs-lookup"><span data-stu-id="e829e-116">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="e829e-117">-EncryptAndSign: メッセージは暗号化され、署名されます。</span><span class="sxs-lookup"><span data-stu-id="e829e-117">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="e829e-118">既定値は EncryptAndSign です。</span><span class="sxs-lookup"><span data-stu-id="e829e-118">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e829e-119">子要素</span><span class="sxs-lookup"><span data-stu-id="e829e-119">Child Elements</span></span>  
 <span data-ttu-id="e829e-120">なし</span><span class="sxs-lookup"><span data-stu-id="e829e-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e829e-121">親要素</span><span class="sxs-lookup"><span data-stu-id="e829e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e829e-122">要素</span><span class="sxs-lookup"><span data-stu-id="e829e-122">Element</span></span>|<span data-ttu-id="e829e-123">Description</span><span class="sxs-lookup"><span data-stu-id="e829e-123">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netnamedpipebinding.md)|<span data-ttu-id="e829e-124">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="e829e-124">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e829e-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="e829e-125">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="e829e-126">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="e829e-126">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e829e-127">バインド</span><span class="sxs-lookup"><span data-stu-id="e829e-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e829e-128">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="e829e-128">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e829e-129">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="e829e-129">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
