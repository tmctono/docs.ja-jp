---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 67ec30b2bf3c322b949700789ce942e4281b77a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757990"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="8de3e-101">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="8de3e-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="8de3e-102">SSL ストリームを使用するチャネル セキュリティをサポートするカスタム バインディング要素を表します。</span><span class="sxs-lookup"><span data-stu-id="8de3e-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="8de3e-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8de3e-103">\<system.serviceModel></span></span>  
<span data-ttu-id="8de3e-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8de3e-104">\<bindings></span></span>  
<span data-ttu-id="8de3e-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="8de3e-105">\<customBinding></span></span>  
<span data-ttu-id="8de3e-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="8de3e-106">\<binding></span></span>  
<span data-ttu-id="8de3e-107">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="8de3e-107">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8de3e-108">構文</span><span class="sxs-lookup"><span data-stu-id="8de3e-108">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8de3e-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8de3e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8de3e-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8de3e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8de3e-111">属性</span><span class="sxs-lookup"><span data-stu-id="8de3e-111">Attributes</span></span>  
  
|<span data-ttu-id="8de3e-112">属性</span><span class="sxs-lookup"><span data-stu-id="8de3e-112">Attribute</span></span>|<span data-ttu-id="8de3e-113">説明</span><span class="sxs-lookup"><span data-stu-id="8de3e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8de3e-114">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="8de3e-114">requireClientCertificate</span></span>|<span data-ttu-id="8de3e-115">クライアント証明書がこのバインディングに必要かどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="8de3e-115">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="8de3e-116">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="8de3e-116">The default is `false`.</span></span>|  
|<span data-ttu-id="8de3e-117">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="8de3e-117">sslProtocols</span></span>|<span data-ttu-id="8de3e-118">どの SslProtocols がサポートされているのかを指定する SslProtocols 列挙型フラグの値。</span><span class="sxs-lookup"><span data-stu-id="8de3e-118">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="8de3e-119">既定値は Ssl3&#124;Tls&#124;Tls11&#124;tls12 です。</span><span class="sxs-lookup"><span data-stu-id="8de3e-119">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8de3e-120">子要素</span><span class="sxs-lookup"><span data-stu-id="8de3e-120">Child Elements</span></span>  
 <span data-ttu-id="8de3e-121">なし。</span><span class="sxs-lookup"><span data-stu-id="8de3e-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8de3e-122">親要素</span><span class="sxs-lookup"><span data-stu-id="8de3e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8de3e-123">要素</span><span class="sxs-lookup"><span data-stu-id="8de3e-123">Element</span></span>|<span data-ttu-id="8de3e-124">説明</span><span class="sxs-lookup"><span data-stu-id="8de3e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8de3e-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="8de3e-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="8de3e-126">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="8de3e-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8de3e-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="8de3e-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="8de3e-128">バインディング</span><span class="sxs-lookup"><span data-stu-id="8de3e-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="8de3e-129">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="8de3e-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8de3e-130">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="8de3e-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="8de3e-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="8de3e-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
