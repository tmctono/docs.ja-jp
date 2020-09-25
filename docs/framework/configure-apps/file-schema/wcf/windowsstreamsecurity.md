---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 3c82bd81bd0fabf10f2dd835188b346f62d038b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167081"
---
# \<windowsStreamSecurity>

<span data-ttu-id="51878-101">カスタム バインディングの Windows ストリーム セキュリティ設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="51878-101">Specify Windows stream security settings of the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="51878-102">構文</span><span class="sxs-lookup"><span data-stu-id="51878-102">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51878-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="51878-103">Attributes and Elements</span></span>  

 <span data-ttu-id="51878-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="51878-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51878-105">属性</span><span class="sxs-lookup"><span data-stu-id="51878-105">Attributes</span></span>  
  
|<span data-ttu-id="51878-106">属性</span><span class="sxs-lookup"><span data-stu-id="51878-106">Attribute</span></span>|<span data-ttu-id="51878-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="51878-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51878-108">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="51878-108">protectionLevel</span></span>|<span data-ttu-id="51878-109">メッセージ レベルのセキュリティを定義します。</span><span class="sxs-lookup"><span data-stu-id="51878-109">Defines message-level security.</span></span> <span data-ttu-id="51878-110">メッセージに署名を付けることで、メッセージの転送中に第三者によって改ざんされるリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="51878-110">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="51878-111">暗号化によって、トランスポート中にデータ レベルのプライバシーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="51878-111">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="51878-112">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="51878-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="51878-113">-None: 保護がありません。</span><span class="sxs-lookup"><span data-stu-id="51878-113">-   None: No protection.</span></span><br /><span data-ttu-id="51878-114">-Sign: メッセージは署名されています。</span><span class="sxs-lookup"><span data-stu-id="51878-114">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="51878-115">-EncryptAndSign: メッセージは署名され、暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="51878-115">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="51878-116">既定値は EncryptAndSign です。</span><span class="sxs-lookup"><span data-stu-id="51878-116">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="51878-117">この属性は <xref:System.Net.Security.ProtectionLevel> 型です。</span><span class="sxs-lookup"><span data-stu-id="51878-117">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51878-118">子要素</span><span class="sxs-lookup"><span data-stu-id="51878-118">Child Elements</span></span>  

 <span data-ttu-id="51878-119">None</span><span class="sxs-lookup"><span data-stu-id="51878-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="51878-120">親要素</span><span class="sxs-lookup"><span data-stu-id="51878-120">Parent Elements</span></span>  
  
|<span data-ttu-id="51878-121">要素</span><span class="sxs-lookup"><span data-stu-id="51878-121">Element</span></span>|<span data-ttu-id="51878-122">説明</span><span class="sxs-lookup"><span data-stu-id="51878-122">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="51878-123">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="51878-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51878-124">解説</span><span class="sxs-lookup"><span data-stu-id="51878-124">Remarks</span></span>  

 <span data-ttu-id="51878-125">TCP などのストリーム指向プロトコルおよび名前付きパイプを使用するトランスポートは、ストリーム ベースのトランスポート アップグレードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="51878-125">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="51878-126">特に、WCF にはセキュリティ アップグレードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="51878-126">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="51878-127">このトランスポートセキュリティの構成は、この構成要素およびによってカプセル化され、これを [\<sslStreamSecurity>](sslstreamsecurity.md) 構成してカスタムバインドに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="51878-127">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51878-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="51878-128">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="51878-129">バインド</span><span class="sxs-lookup"><span data-stu-id="51878-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="51878-130">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="51878-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="51878-131">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="51878-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
