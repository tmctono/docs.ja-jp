---
title: <issuerMetadata> の <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: e46e56c6285af24941a550b2c4f7dec3b441db69
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214807"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="1738c-102">\<issuerMetadata > の\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="1738c-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>
<span data-ttu-id="1738c-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1738c-103">\<system.serviceModel></span></span>  
<span data-ttu-id="1738c-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1738c-104">\<bindings></span></span>  
<span data-ttu-id="1738c-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1738c-105">\<customBinding></span></span>  
<span data-ttu-id="1738c-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="1738c-106">\<binding></span></span>  
<span data-ttu-id="1738c-107">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="1738c-107">\<security></span></span>  
<span data-ttu-id="1738c-108">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="1738c-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="1738c-109">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="1738c-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1738c-110">構文</span><span class="sxs-lookup"><span data-stu-id="1738c-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1738c-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1738c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1738c-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1738c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1738c-113">属性</span><span class="sxs-lookup"><span data-stu-id="1738c-113">Attributes</span></span>  
  
|<span data-ttu-id="1738c-114">属性</span><span class="sxs-lookup"><span data-stu-id="1738c-114">Attribute</span></span>|<span data-ttu-id="1738c-115">説明</span><span class="sxs-lookup"><span data-stu-id="1738c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1738c-116">アドレス</span><span class="sxs-lookup"><span data-stu-id="1738c-116">address</span></span>|<span data-ttu-id="1738c-117">必須。</span><span class="sxs-lookup"><span data-stu-id="1738c-117">Required.</span></span> <span data-ttu-id="1738c-118">エンドポイントのアドレスを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1738c-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="1738c-119">アドレスは、絶対 URI にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1738c-119">The address must be an absolute URI.</span></span> <span data-ttu-id="1738c-120">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="1738c-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1738c-121">子要素</span><span class="sxs-lookup"><span data-stu-id="1738c-121">Child Elements</span></span>  
  
|<span data-ttu-id="1738c-122">要素</span><span class="sxs-lookup"><span data-stu-id="1738c-122">Element</span></span>|<span data-ttu-id="1738c-123">説明</span><span class="sxs-lookup"><span data-stu-id="1738c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1738c-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="1738c-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="1738c-125">アドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="1738c-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="1738c-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="1738c-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="1738c-127">メッセージを交換する他のエンドポイントによるエンドポイントの認証を可能にする ID です。</span><span class="sxs-lookup"><span data-stu-id="1738c-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1738c-128">親要素</span><span class="sxs-lookup"><span data-stu-id="1738c-128">Parent Elements</span></span>  
  
|<span data-ttu-id="1738c-129">要素</span><span class="sxs-lookup"><span data-stu-id="1738c-129">Element</span></span>|<span data-ttu-id="1738c-130">説明</span><span class="sxs-lookup"><span data-stu-id="1738c-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1738c-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="1738c-131">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="1738c-132">フェデレーション セキュリティのシナリオで発行されるセキュリティ トークンのパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="1738c-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1738c-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="1738c-133">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="1738c-134">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="1738c-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="1738c-135">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="1738c-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="1738c-136">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="1738c-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="1738c-137">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="1738c-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="1738c-138">バインディング</span><span class="sxs-lookup"><span data-stu-id="1738c-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="1738c-139">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="1738c-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="1738c-140">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="1738c-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="1738c-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1738c-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="1738c-142">方法: SecurityBindingElement を使用してカスタム バインディングを作成します。</span><span class="sxs-lookup"><span data-stu-id="1738c-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="1738c-143">カスタム バインド セキュリティ</span><span class="sxs-lookup"><span data-stu-id="1738c-143">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
