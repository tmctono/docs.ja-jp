---
title: <issuerMetadata> の <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: fcdd66ecd162dff5be86a1d4ab1b196f50dbd445
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400340"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="00837-102">\<issuedTokenParameters の\<issuermetadata > ></span><span class="sxs-lookup"><span data-stu-id="00837-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>

<span data-ttu-id="00837-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="00837-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="00837-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="00837-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="00837-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="00837-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="00837-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="00837-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="00837-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="00837-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="00837-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<セキュリティ >** ](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="00837-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="00837-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenParameters >** ](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="00837-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="00837-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerMetadata >**</span><span class="sxs-lookup"><span data-stu-id="00837-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00837-111">構文</span><span class="sxs-lookup"><span data-stu-id="00837-111">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00837-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="00837-112">Attributes and Elements</span></span>  
 <span data-ttu-id="00837-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="00837-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00837-114">属性</span><span class="sxs-lookup"><span data-stu-id="00837-114">Attributes</span></span>  
  
|<span data-ttu-id="00837-115">属性</span><span class="sxs-lookup"><span data-stu-id="00837-115">Attribute</span></span>|<span data-ttu-id="00837-116">説明</span><span class="sxs-lookup"><span data-stu-id="00837-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="00837-117">address</span><span class="sxs-lookup"><span data-stu-id="00837-117">address</span></span>|<span data-ttu-id="00837-118">必須。</span><span class="sxs-lookup"><span data-stu-id="00837-118">Required.</span></span> <span data-ttu-id="00837-119">エンドポイントのアドレスを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="00837-119">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="00837-120">アドレスは、絶対 URI にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00837-120">The address must be an absolute URI.</span></span> <span data-ttu-id="00837-121">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="00837-121">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00837-122">子要素</span><span class="sxs-lookup"><span data-stu-id="00837-122">Child Elements</span></span>  
  
|<span data-ttu-id="00837-123">要素</span><span class="sxs-lookup"><span data-stu-id="00837-123">Element</span></span>|<span data-ttu-id="00837-124">説明</span><span class="sxs-lookup"><span data-stu-id="00837-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00837-125">\<headers></span><span class="sxs-lookup"><span data-stu-id="00837-125">\<headers></span></span>](headers-element.md)|<span data-ttu-id="00837-126">アドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="00837-126">A collection of address headers.</span></span>|  
|[<span data-ttu-id="00837-127">\<identity></span><span class="sxs-lookup"><span data-stu-id="00837-127">\<identity></span></span>](identity.md)|<span data-ttu-id="00837-128">メッセージを交換する他のエンドポイントによるエンドポイントの認証を可能にする ID です。</span><span class="sxs-lookup"><span data-stu-id="00837-128">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00837-129">親要素</span><span class="sxs-lookup"><span data-stu-id="00837-129">Parent Elements</span></span>  
  
|<span data-ttu-id="00837-130">要素</span><span class="sxs-lookup"><span data-stu-id="00837-130">Element</span></span>|<span data-ttu-id="00837-131">説明</span><span class="sxs-lookup"><span data-stu-id="00837-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00837-132">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="00837-132">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="00837-133">フェデレーション セキュリティのシナリオで発行されるセキュリティ トークンのパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="00837-133">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="00837-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="00837-134">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="00837-135">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="00837-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="00837-136">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="00837-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="00837-137">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="00837-137">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="00837-138">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="00837-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="00837-139">バインディング</span><span class="sxs-lookup"><span data-stu-id="00837-139">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="00837-140">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="00837-140">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="00837-141">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="00837-141">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="00837-142">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="00837-142">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="00837-143">方法: 設定を使用してカスタムバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="00837-143">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="00837-144">カスタム バインド セキュリティ</span><span class="sxs-lookup"><span data-stu-id="00837-144">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
