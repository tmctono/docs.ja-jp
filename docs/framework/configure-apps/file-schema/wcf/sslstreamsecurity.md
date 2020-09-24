---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: aa6bc7f5a94afc8a190d3d9d2d71ea8b38d8c25b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153574"
---
# \<sslStreamSecurity>

<span data-ttu-id="c0ee7-101">SSL ストリームを使用するチャネル セキュリティをサポートするカスタム バインディング要素を表します。</span><span class="sxs-lookup"><span data-stu-id="c0ee7-101">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="c0ee7-102">構文</span><span class="sxs-lookup"><span data-stu-id="c0ee7-102">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0ee7-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c0ee7-103">Attributes and Elements</span></span>  

 <span data-ttu-id="c0ee7-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0ee7-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0ee7-105">属性</span><span class="sxs-lookup"><span data-stu-id="c0ee7-105">Attributes</span></span>  
  
|<span data-ttu-id="c0ee7-106">属性</span><span class="sxs-lookup"><span data-stu-id="c0ee7-106">Attribute</span></span>|<span data-ttu-id="c0ee7-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="c0ee7-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0ee7-108">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="c0ee7-108">requireClientCertificate</span></span>|<span data-ttu-id="c0ee7-109">クライアント証明書がこのバインディングに必要かどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="c0ee7-109">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="c0ee7-110">既定では、 `false`です。</span><span class="sxs-lookup"><span data-stu-id="c0ee7-110">The default is `false`.</span></span>|  
|<span data-ttu-id="c0ee7-111">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="c0ee7-111">sslProtocols</span></span>|<span data-ttu-id="c0ee7-112">どの SslProtocols がサポートされているのかを指定する SslProtocols 列挙型フラグの値。</span><span class="sxs-lookup"><span data-stu-id="c0ee7-112">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="c0ee7-113">既定値は、Ssl3&#124;Tls&#124;Tls11&#124;Tls12 です。</span><span class="sxs-lookup"><span data-stu-id="c0ee7-113">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0ee7-114">子要素</span><span class="sxs-lookup"><span data-stu-id="c0ee7-114">Child Elements</span></span>  

 <span data-ttu-id="c0ee7-115">なし。</span><span class="sxs-lookup"><span data-stu-id="c0ee7-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0ee7-116">親要素</span><span class="sxs-lookup"><span data-stu-id="c0ee7-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c0ee7-117">要素</span><span class="sxs-lookup"><span data-stu-id="c0ee7-117">Element</span></span>|<span data-ttu-id="c0ee7-118">説明</span><span class="sxs-lookup"><span data-stu-id="c0ee7-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="c0ee7-119">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="c0ee7-119">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0ee7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0ee7-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="c0ee7-121">バインド</span><span class="sxs-lookup"><span data-stu-id="c0ee7-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c0ee7-122">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="c0ee7-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c0ee7-123">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="c0ee7-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
