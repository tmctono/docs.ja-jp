---
title: <issuer> の <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: bdd5ad45984fae7b39defe82c4af75845dfda1b6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397942"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="d3d71-102">\<issuer> の \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="d3d71-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="d3d71-103">セキュリティ トークンを発行するセキュリティ トークン サービス (STS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="d3d71-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="d3d71-104">構文</span><span class="sxs-lookup"><span data-stu-id="d3d71-104">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3d71-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d3d71-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d3d71-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3d71-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3d71-107">属性</span><span class="sxs-lookup"><span data-stu-id="d3d71-107">Attributes</span></span>  
  
|<span data-ttu-id="d3d71-108">属性</span><span class="sxs-lookup"><span data-stu-id="d3d71-108">Attribute</span></span>|<span data-ttu-id="d3d71-109">説明</span><span class="sxs-lookup"><span data-stu-id="d3d71-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d3d71-110">address</span><span class="sxs-lookup"><span data-stu-id="d3d71-110">address</span></span>|<span data-ttu-id="d3d71-111">必須の文字列。</span><span class="sxs-lookup"><span data-stu-id="d3d71-111">Required string.</span></span> <span data-ttu-id="d3d71-112">STS の URL です。</span><span class="sxs-lookup"><span data-stu-id="d3d71-112">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3d71-113">子要素</span><span class="sxs-lookup"><span data-stu-id="d3d71-113">Child Elements</span></span>  
  
|<span data-ttu-id="d3d71-114">要素</span><span class="sxs-lookup"><span data-stu-id="d3d71-114">Element</span></span>|<span data-ttu-id="d3d71-115">Description</span><span class="sxs-lookup"><span data-stu-id="d3d71-115">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="d3d71-116">ビルダーが作成できるエンドポイントのアドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="d3d71-116">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="d3d71-117">発行されたトークンを使用する場合、クライアントでサーバーの認証を有効にする設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="d3d71-117">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d3d71-118">親要素</span><span class="sxs-lookup"><span data-stu-id="d3d71-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d3d71-119">要素</span><span class="sxs-lookup"><span data-stu-id="d3d71-119">Element</span></span>|<span data-ttu-id="d3d71-120">Description</span><span class="sxs-lookup"><span data-stu-id="d3d71-120">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="d3d71-121">現在発行されているトークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="d3d71-121">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3d71-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3d71-122">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d3d71-123">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="d3d71-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d3d71-124">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="d3d71-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d3d71-125">カスタム バインディングを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="d3d71-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="d3d71-126">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="d3d71-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d3d71-127">バインド</span><span class="sxs-lookup"><span data-stu-id="d3d71-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d3d71-128">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="d3d71-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d3d71-129">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="d3d71-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="d3d71-130">方法: SecurityBindingElement を使用してカスタム バインドを作成する</span><span class="sxs-lookup"><span data-stu-id="d3d71-130">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="d3d71-131">カスタム バインディング セキュリティ</span><span class="sxs-lookup"><span data-stu-id="d3d71-131">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
