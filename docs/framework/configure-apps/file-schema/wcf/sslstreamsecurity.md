---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: c5c7ec2b18143ff4d71540a60e24b8225ca4db16
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738591"
---
# \<sslStreamSecurity>
<span data-ttu-id="f016a-101">SSL ストリームを使用するチャネル セキュリティをサポートするカスタム バインディング要素を表します。</span><span class="sxs-lookup"><span data-stu-id="f016a-101">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="f016a-102">構文</span><span class="sxs-lookup"><span data-stu-id="f016a-102">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f016a-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f016a-103">Attributes and Elements</span></span>  
 <span data-ttu-id="f016a-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f016a-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f016a-105">属性</span><span class="sxs-lookup"><span data-stu-id="f016a-105">Attributes</span></span>  
  
|<span data-ttu-id="f016a-106">属性</span><span class="sxs-lookup"><span data-stu-id="f016a-106">Attribute</span></span>|<span data-ttu-id="f016a-107">説明</span><span class="sxs-lookup"><span data-stu-id="f016a-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f016a-108">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="f016a-108">requireClientCertificate</span></span>|<span data-ttu-id="f016a-109">クライアント証明書がこのバインディングに必要かどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="f016a-109">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="f016a-110">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="f016a-110">The default is `false`.</span></span>|  
|<span data-ttu-id="f016a-111">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="f016a-111">sslProtocols</span></span>|<span data-ttu-id="f016a-112">どの SslProtocols がサポートされているのかを指定する SslProtocols 列挙型フラグの値。</span><span class="sxs-lookup"><span data-stu-id="f016a-112">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="f016a-113">既定値は、Ssl3&#124;Tls&#124;Tls11&#124;Tls12 です。</span><span class="sxs-lookup"><span data-stu-id="f016a-113">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f016a-114">子要素</span><span class="sxs-lookup"><span data-stu-id="f016a-114">Child Elements</span></span>  
 <span data-ttu-id="f016a-115">なし。</span><span class="sxs-lookup"><span data-stu-id="f016a-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f016a-116">親要素</span><span class="sxs-lookup"><span data-stu-id="f016a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f016a-117">要素</span><span class="sxs-lookup"><span data-stu-id="f016a-117">Element</span></span>|<span data-ttu-id="f016a-118">Description</span><span class="sxs-lookup"><span data-stu-id="f016a-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="f016a-119">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="f016a-119">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f016a-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="f016a-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="f016a-121">バインド</span><span class="sxs-lookup"><span data-stu-id="f016a-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f016a-122">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="f016a-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f016a-123">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="f016a-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
