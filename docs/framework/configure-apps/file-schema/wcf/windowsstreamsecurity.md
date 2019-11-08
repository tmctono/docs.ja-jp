---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: dab8505a9ddb348a6f7fe16ae9acb3a0119a8b06
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735887"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="f06dd-101">windowsStreamSecurity > の \<</span><span class="sxs-lookup"><span data-stu-id="f06dd-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="f06dd-102">カスタム バインディングの Windows ストリーム セキュリティ設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f06dd-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
<span data-ttu-id="f06dd-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f06dd-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f06dd-104">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="f06dd-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f06dd-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="f06dd-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="f06dd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="f06dd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="f06dd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="f06dd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="f06dd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**windowsStreamSecurity >**</span><span class="sxs-lookup"><span data-stu-id="f06dd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f06dd-109">構文</span><span class="sxs-lookup"><span data-stu-id="f06dd-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f06dd-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f06dd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f06dd-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f06dd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f06dd-112">属性</span><span class="sxs-lookup"><span data-stu-id="f06dd-112">Attributes</span></span>  
  
|<span data-ttu-id="f06dd-113">属性</span><span class="sxs-lookup"><span data-stu-id="f06dd-113">Attribute</span></span>|<span data-ttu-id="f06dd-114">説明</span><span class="sxs-lookup"><span data-stu-id="f06dd-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f06dd-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="f06dd-115">protectionLevel</span></span>|<span data-ttu-id="f06dd-116">メッセージ レベルのセキュリティを定義します。</span><span class="sxs-lookup"><span data-stu-id="f06dd-116">Defines message-level security.</span></span> <span data-ttu-id="f06dd-117">メッセージに署名すると、転送中のメッセージが第三者によって改ざんされるリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="f06dd-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="f06dd-118">暗号化により、転送中にデータレベルのプライバシーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="f06dd-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="f06dd-119">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="f06dd-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f06dd-120">-None: 保護がありません。</span><span class="sxs-lookup"><span data-stu-id="f06dd-120">-   None: No protection.</span></span><br /><span data-ttu-id="f06dd-121">-Sign: メッセージは署名されています。</span><span class="sxs-lookup"><span data-stu-id="f06dd-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="f06dd-122">-EncryptAndSign: メッセージは署名され、暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="f06dd-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="f06dd-123">既定値は EncryptAndSign です。</span><span class="sxs-lookup"><span data-stu-id="f06dd-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="f06dd-124">この属性は <xref:System.Net.Security.ProtectionLevel> 型です。</span><span class="sxs-lookup"><span data-stu-id="f06dd-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f06dd-125">子要素</span><span class="sxs-lookup"><span data-stu-id="f06dd-125">Child Elements</span></span>  
 <span data-ttu-id="f06dd-126">None</span><span class="sxs-lookup"><span data-stu-id="f06dd-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f06dd-127">親要素</span><span class="sxs-lookup"><span data-stu-id="f06dd-127">Parent Elements</span></span>  
  
|<span data-ttu-id="f06dd-128">要素</span><span class="sxs-lookup"><span data-stu-id="f06dd-128">Element</span></span>|<span data-ttu-id="f06dd-129">説明</span><span class="sxs-lookup"><span data-stu-id="f06dd-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f06dd-130">\<binding ></span><span class="sxs-lookup"><span data-stu-id="f06dd-130">\<binding></span></span>](bindings.md)|<span data-ttu-id="f06dd-131">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="f06dd-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f06dd-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="f06dd-132">Remarks</span></span>  
 <span data-ttu-id="f06dd-133">TCP などのストリーム指向プロトコルおよび名前付きパイプを使用するトランスポートは、ストリーム ベースのトランスポート アップグレードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f06dd-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="f06dd-134">特に、WCF にはセキュリティ アップグレードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f06dd-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="f06dd-135">このトランスポートセキュリティの構成は、この構成要素および[\<sslStreamSecurity >](sslstreamsecurity.md)によってカプセル化されます。これは、構成してカスタムバインドに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="f06dd-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f06dd-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="f06dd-136">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="f06dd-137">バインディング</span><span class="sxs-lookup"><span data-stu-id="f06dd-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f06dd-138">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="f06dd-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f06dd-139">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="f06dd-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f06dd-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f06dd-140">\<customBinding></span></span>](custombinding.md)
