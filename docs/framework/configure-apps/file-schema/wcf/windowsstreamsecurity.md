---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 0f1dfd523e593c82727354db7ce39ffc992bdfb4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932805"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="e6ec1-101">\<windowsStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="e6ec1-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="e6ec1-102">カスタム バインディングの Windows ストリーム セキュリティ設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="e6ec1-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e6ec1-103">\<system.serviceModel></span></span>  
<span data-ttu-id="e6ec1-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e6ec1-104">\<bindings></span></span>  
<span data-ttu-id="e6ec1-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e6ec1-105">\<customBinding></span></span>  
<span data-ttu-id="e6ec1-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="e6ec1-106">\<binding></span></span>  
<span data-ttu-id="e6ec1-107">\<windowsStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="e6ec1-107">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6ec1-108">構文</span><span class="sxs-lookup"><span data-stu-id="e6ec1-108">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6ec1-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e6ec1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e6ec1-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6ec1-111">属性</span><span class="sxs-lookup"><span data-stu-id="e6ec1-111">Attributes</span></span>  
  
|<span data-ttu-id="e6ec1-112">属性</span><span class="sxs-lookup"><span data-stu-id="e6ec1-112">Attribute</span></span>|<span data-ttu-id="e6ec1-113">説明</span><span class="sxs-lookup"><span data-stu-id="e6ec1-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e6ec1-114">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="e6ec1-114">protectionLevel</span></span>|<span data-ttu-id="e6ec1-115">メッセージ レベルのセキュリティを定義します。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-115">Defines message-level security.</span></span> <span data-ttu-id="e6ec1-116">メッセージに署名を付けることで、メッセージの転送中に第三者によって改ざんされるリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-116">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="e6ec1-117">暗号化によって、トランスポート中にデータ レベルのプライバシーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-117">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="e6ec1-118">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e6ec1-119">存在保護されません。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-119">-   None: No protection.</span></span><br /><span data-ttu-id="e6ec1-120">シャープメッセージは署名されます。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-120">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="e6ec1-121">EncryptAndSignメッセージは署名され、暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-121">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="e6ec1-122">既定値は EncryptAndSign です。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-122">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="e6ec1-123">この属性は <xref:System.Net.Security.ProtectionLevel> 型です。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-123">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6ec1-124">子要素</span><span class="sxs-lookup"><span data-stu-id="e6ec1-124">Child Elements</span></span>  
 <span data-ttu-id="e6ec1-125">なし</span><span class="sxs-lookup"><span data-stu-id="e6ec1-125">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e6ec1-126">親要素</span><span class="sxs-lookup"><span data-stu-id="e6ec1-126">Parent Elements</span></span>  
  
|<span data-ttu-id="e6ec1-127">要素</span><span class="sxs-lookup"><span data-stu-id="e6ec1-127">Element</span></span>|<span data-ttu-id="e6ec1-128">説明</span><span class="sxs-lookup"><span data-stu-id="e6ec1-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6ec1-129">\<binding></span><span class="sxs-lookup"><span data-stu-id="e6ec1-129">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="e6ec1-130">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6ec1-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="e6ec1-131">Remarks</span></span>  
 <span data-ttu-id="e6ec1-132">TCP などのストリーム指向プロトコルおよび名前付きパイプを使用するトランスポートは、ストリーム ベースのトランスポート アップグレードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-132">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="e6ec1-133">特に、WCF にはセキュリティ アップグレードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-133">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="e6ec1-134">このトランスポートセキュリティの構成は、この構成要素および[ \<sslstreamsecurity >](sslstreamsecurity.md)によってカプセル化されます。これは、構成してカスタムバインドに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="e6ec1-134">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6ec1-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6ec1-135">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="e6ec1-136">バインディング</span><span class="sxs-lookup"><span data-stu-id="e6ec1-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e6ec1-137">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="e6ec1-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e6ec1-138">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="e6ec1-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e6ec1-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e6ec1-139">\<customBinding></span></span>](custombinding.md)
