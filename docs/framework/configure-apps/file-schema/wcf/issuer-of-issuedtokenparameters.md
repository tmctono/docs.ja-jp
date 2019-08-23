---
title: <issuer> の <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 77ed9534ce872e805a6a6ea2c21a38710e6bc0fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925266"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="5677d-102">\<issuedTokenParameters > の\<発行者 ></span><span class="sxs-lookup"><span data-stu-id="5677d-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="5677d-103">セキュリティ トークンを発行するセキュリティ トークン サービス (STS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="5677d-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="5677d-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5677d-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5677d-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5677d-105">\<bindings></span></span>  
<span data-ttu-id="5677d-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5677d-106">\<customBinding></span></span>  
<span data-ttu-id="5677d-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="5677d-107">\<binding></span></span>  
<span data-ttu-id="5677d-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="5677d-108">\<security></span></span>  
<span data-ttu-id="5677d-109">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="5677d-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="5677d-110">\<発行者の ></span><span class="sxs-lookup"><span data-stu-id="5677d-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5677d-111">構文</span><span class="sxs-lookup"><span data-stu-id="5677d-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5677d-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5677d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5677d-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5677d-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5677d-114">属性</span><span class="sxs-lookup"><span data-stu-id="5677d-114">Attributes</span></span>  
  
|<span data-ttu-id="5677d-115">属性</span><span class="sxs-lookup"><span data-stu-id="5677d-115">Attribute</span></span>|<span data-ttu-id="5677d-116">説明</span><span class="sxs-lookup"><span data-stu-id="5677d-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5677d-117">address</span><span class="sxs-lookup"><span data-stu-id="5677d-117">address</span></span>|<span data-ttu-id="5677d-118">必須の文字列。</span><span class="sxs-lookup"><span data-stu-id="5677d-118">Required string.</span></span> <span data-ttu-id="5677d-119">STS の URL です。</span><span class="sxs-lookup"><span data-stu-id="5677d-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5677d-120">子要素</span><span class="sxs-lookup"><span data-stu-id="5677d-120">Child Elements</span></span>  
  
|<span data-ttu-id="5677d-121">要素</span><span class="sxs-lookup"><span data-stu-id="5677d-121">Element</span></span>|<span data-ttu-id="5677d-122">説明</span><span class="sxs-lookup"><span data-stu-id="5677d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5677d-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="5677d-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="5677d-124">ビルダーが作成できるエンドポイントのアドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="5677d-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="5677d-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="5677d-125">\<identity></span></span>](identity.md)|<span data-ttu-id="5677d-126">発行されたトークンを使用する場合、クライアントでサーバーの認証を有効にする設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="5677d-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5677d-127">親要素</span><span class="sxs-lookup"><span data-stu-id="5677d-127">Parent Elements</span></span>  
  
|<span data-ttu-id="5677d-128">要素</span><span class="sxs-lookup"><span data-stu-id="5677d-128">Element</span></span>|<span data-ttu-id="5677d-129">説明</span><span class="sxs-lookup"><span data-stu-id="5677d-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5677d-130">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="5677d-130">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="5677d-131">現在発行されているトークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="5677d-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5677d-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="5677d-132">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5677d-133">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="5677d-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="5677d-134">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="5677d-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5677d-135">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="5677d-135">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="5677d-136">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="5677d-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5677d-137">バインディング</span><span class="sxs-lookup"><span data-stu-id="5677d-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5677d-138">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="5677d-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5677d-139">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="5677d-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5677d-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5677d-140">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="5677d-141">方法: 設定を使用してカスタムバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="5677d-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="5677d-142">カスタム バインド セキュリティ</span><span class="sxs-lookup"><span data-stu-id="5677d-142">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
