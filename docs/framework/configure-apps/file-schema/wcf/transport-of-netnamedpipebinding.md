---
title: <transport> (行中)  <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: a6d3dd2c24e90bdcdc6520e62dcc1dbe7ce797f9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199831"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="c2244-102">\<トランスポート > の\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="c2244-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="c2244-103">名前付きパイプのトランスポート セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="c2244-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="c2244-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c2244-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c2244-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c2244-105">\<bindings></span></span>  
<span data-ttu-id="c2244-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="c2244-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="c2244-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="c2244-107">\<binding></span></span>  
<span data-ttu-id="c2244-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="c2244-108">\<security></span></span>  
<span data-ttu-id="c2244-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="c2244-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2244-110">構文</span><span class="sxs-lookup"><span data-stu-id="c2244-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2244-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c2244-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c2244-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2244-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2244-113">属性</span><span class="sxs-lookup"><span data-stu-id="c2244-113">Attributes</span></span>  
  
|<span data-ttu-id="c2244-114">属性</span><span class="sxs-lookup"><span data-stu-id="c2244-114">Attribute</span></span>|<span data-ttu-id="c2244-115">説明</span><span class="sxs-lookup"><span data-stu-id="c2244-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c2244-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="c2244-116">protectionLevel</span></span>|<span data-ttu-id="c2244-117">名前付きパイプの保護レベルを定義します。</span><span class="sxs-lookup"><span data-stu-id="c2244-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="c2244-118">メッセージに署名すると、転送中のメッセージが第三者によって改ざんされるリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="c2244-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="c2244-119">暗号化によって、トランスポート中にデータ レベルのプライバシーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c2244-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="c2244-120">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="c2244-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c2244-121">-None。保護されません。</span><span class="sxs-lookup"><span data-stu-id="c2244-121">-   None: No protection.</span></span><br /><span data-ttu-id="c2244-122">署名:メッセージは署名されます。</span><span class="sxs-lookup"><span data-stu-id="c2244-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="c2244-123">-EncryptAndSign:メッセージは暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="c2244-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="c2244-124">既定値は EncryptAndSign です。</span><span class="sxs-lookup"><span data-stu-id="c2244-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2244-125">子要素</span><span class="sxs-lookup"><span data-stu-id="c2244-125">Child Elements</span></span>  
 <span data-ttu-id="c2244-126">なし</span><span class="sxs-lookup"><span data-stu-id="c2244-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c2244-127">親要素</span><span class="sxs-lookup"><span data-stu-id="c2244-127">Parent Elements</span></span>  
  
|<span data-ttu-id="c2244-128">要素</span><span class="sxs-lookup"><span data-stu-id="c2244-128">Element</span></span>|<span data-ttu-id="c2244-129">説明</span><span class="sxs-lookup"><span data-stu-id="c2244-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2244-130">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="c2244-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="c2244-131">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="c2244-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2244-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2244-132">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="c2244-133">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="c2244-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c2244-134">バインディング</span><span class="sxs-lookup"><span data-stu-id="c2244-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="c2244-135">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="c2244-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c2244-136">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="c2244-136">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="c2244-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="c2244-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
