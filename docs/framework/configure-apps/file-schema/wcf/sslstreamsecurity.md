---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 9b7092878c604142c29dcd8d27e3c458d203f9fa
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399530"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="6bb70-101">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="6bb70-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="6bb70-102">SSL ストリームを使用するチャネル セキュリティをサポートするカスタム バインディング要素を表します。</span><span class="sxs-lookup"><span data-stu-id="6bb70-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
<span data-ttu-id="6bb70-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6bb70-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6bb70-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6bb70-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6bb70-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="6bb70-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="6bb70-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="6bb70-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="6bb70-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="6bb70-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="6bb70-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<sslStreamSecurity >**</span><span class="sxs-lookup"><span data-stu-id="6bb70-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bb70-109">構文</span><span class="sxs-lookup"><span data-stu-id="6bb70-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6bb70-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6bb70-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6bb70-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6bb70-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6bb70-112">属性</span><span class="sxs-lookup"><span data-stu-id="6bb70-112">Attributes</span></span>  
  
|<span data-ttu-id="6bb70-113">属性</span><span class="sxs-lookup"><span data-stu-id="6bb70-113">Attribute</span></span>|<span data-ttu-id="6bb70-114">説明</span><span class="sxs-lookup"><span data-stu-id="6bb70-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6bb70-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="6bb70-115">requireClientCertificate</span></span>|<span data-ttu-id="6bb70-116">クライアント証明書がこのバインディングに必要かどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="6bb70-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="6bb70-117">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="6bb70-117">The default is `false`.</span></span>|  
|<span data-ttu-id="6bb70-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="6bb70-118">sslProtocols</span></span>|<span data-ttu-id="6bb70-119">どの SslProtocols がサポートされているのかを指定する SslProtocols 列挙型フラグの値。</span><span class="sxs-lookup"><span data-stu-id="6bb70-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="6bb70-120">既定値は、&#124;Ssl3&#124;Tls&#124;Tls11 Tls12 です。</span><span class="sxs-lookup"><span data-stu-id="6bb70-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6bb70-121">子要素</span><span class="sxs-lookup"><span data-stu-id="6bb70-121">Child Elements</span></span>  
 <span data-ttu-id="6bb70-122">なし。</span><span class="sxs-lookup"><span data-stu-id="6bb70-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6bb70-123">親要素</span><span class="sxs-lookup"><span data-stu-id="6bb70-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6bb70-124">要素</span><span class="sxs-lookup"><span data-stu-id="6bb70-124">Element</span></span>|<span data-ttu-id="6bb70-125">説明</span><span class="sxs-lookup"><span data-stu-id="6bb70-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6bb70-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="6bb70-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="6bb70-127">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="6bb70-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6bb70-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bb70-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="6bb70-129">バインディング</span><span class="sxs-lookup"><span data-stu-id="6bb70-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6bb70-130">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="6bb70-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="6bb70-131">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="6bb70-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="6bb70-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6bb70-132">\<customBinding></span></span>](custombinding.md)
