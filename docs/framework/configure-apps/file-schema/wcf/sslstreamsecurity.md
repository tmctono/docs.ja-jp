---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 5ed87adfb3963513602844fc69afce8f7994fa8e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932423"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="ad402-101">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="ad402-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="ad402-102">SSL ストリームを使用するチャネル セキュリティをサポートするカスタム バインディング要素を表します。</span><span class="sxs-lookup"><span data-stu-id="ad402-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="ad402-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ad402-103">\<system.serviceModel></span></span>  
<span data-ttu-id="ad402-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ad402-104">\<bindings></span></span>  
<span data-ttu-id="ad402-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ad402-105">\<customBinding></span></span>  
<span data-ttu-id="ad402-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="ad402-106">\<binding></span></span>  
<span data-ttu-id="ad402-107">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="ad402-107">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad402-108">構文</span><span class="sxs-lookup"><span data-stu-id="ad402-108">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad402-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ad402-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ad402-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ad402-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad402-111">属性</span><span class="sxs-lookup"><span data-stu-id="ad402-111">Attributes</span></span>  
  
|<span data-ttu-id="ad402-112">属性</span><span class="sxs-lookup"><span data-stu-id="ad402-112">Attribute</span></span>|<span data-ttu-id="ad402-113">説明</span><span class="sxs-lookup"><span data-stu-id="ad402-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ad402-114">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="ad402-114">requireClientCertificate</span></span>|<span data-ttu-id="ad402-115">クライアント証明書がこのバインディングに必要かどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="ad402-115">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="ad402-116">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="ad402-116">The default is `false`.</span></span>|  
|<span data-ttu-id="ad402-117">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="ad402-117">sslProtocols</span></span>|<span data-ttu-id="ad402-118">どの SslProtocols がサポートされているのかを指定する SslProtocols 列挙型フラグの値。</span><span class="sxs-lookup"><span data-stu-id="ad402-118">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="ad402-119">既定値は、&#124;Ssl3&#124;Tls&#124;Tls11 Tls12 です。</span><span class="sxs-lookup"><span data-stu-id="ad402-119">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ad402-120">子要素</span><span class="sxs-lookup"><span data-stu-id="ad402-120">Child Elements</span></span>  
 <span data-ttu-id="ad402-121">なし。</span><span class="sxs-lookup"><span data-stu-id="ad402-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ad402-122">親要素</span><span class="sxs-lookup"><span data-stu-id="ad402-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ad402-123">要素</span><span class="sxs-lookup"><span data-stu-id="ad402-123">Element</span></span>|<span data-ttu-id="ad402-124">説明</span><span class="sxs-lookup"><span data-stu-id="ad402-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad402-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="ad402-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="ad402-126">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad402-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad402-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad402-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="ad402-128">バインディング</span><span class="sxs-lookup"><span data-stu-id="ad402-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ad402-129">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="ad402-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ad402-130">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="ad402-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ad402-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ad402-131">\<customBinding></span></span>](custombinding.md)
