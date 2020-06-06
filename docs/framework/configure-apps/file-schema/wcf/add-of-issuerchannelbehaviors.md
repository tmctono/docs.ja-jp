---
title: <add> の <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: cf7ac2691ad1c641352a8047373ced538b19e983
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398331"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="312c8-102">\<add> の \<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="312c8-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="312c8-103">STS と通信するときに使用されるエンドポイントの動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="312c8-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="312c8-104">いずれかのエンドポイント動作に要素が含まれている場合は [\<clientCredentials>](clientcredentials.md) 、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="312c8-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerChannelBehaviors>**](issuerchannelbehaviors-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  

## <a name="syntax"></a><span data-ttu-id="312c8-105">構文</span><span class="sxs-lookup"><span data-stu-id="312c8-105">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="312c8-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="312c8-106">Attributes and Elements</span></span>

<span data-ttu-id="312c8-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="312c8-107">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="312c8-108">属性</span><span class="sxs-lookup"><span data-stu-id="312c8-108">Attributes</span></span>

|<span data-ttu-id="312c8-109">属性</span><span class="sxs-lookup"><span data-stu-id="312c8-109">Attribute</span></span>|<span data-ttu-id="312c8-110">説明</span><span class="sxs-lookup"><span data-stu-id="312c8-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="312c8-111">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="312c8-111">issuerAddress</span></span>|<span data-ttu-id="312c8-112">通信するためのセキュリティ トークン発行者の URI。</span><span class="sxs-lookup"><span data-stu-id="312c8-112">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="312c8-113">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="312c8-113">behaviorConfiguration</span></span>|<span data-ttu-id="312c8-114">同じ構成ファイルに定義されたエンドポイントの動作の名前。</span><span class="sxs-lookup"><span data-stu-id="312c8-114">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="312c8-115">子要素</span><span class="sxs-lookup"><span data-stu-id="312c8-115">Child Elements</span></span>

<span data-ttu-id="312c8-116">なし。</span><span class="sxs-lookup"><span data-stu-id="312c8-116">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="312c8-117">親要素</span><span class="sxs-lookup"><span data-stu-id="312c8-117">Parent Elements</span></span>

|<span data-ttu-id="312c8-118">要素</span><span class="sxs-lookup"><span data-stu-id="312c8-118">Element</span></span>|<span data-ttu-id="312c8-119">Description</span><span class="sxs-lookup"><span data-stu-id="312c8-119">Description</span></span>|
|-------------|-----------------|
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|<span data-ttu-id="312c8-120">指定されたサービストークンサービスと通信するときに使用される Windows Communication Foundation (WCF) クライアントエンドポイントの動作のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="312c8-120">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="312c8-121">解説</span><span class="sxs-lookup"><span data-stu-id="312c8-121">Remarks</span></span>

<span data-ttu-id="312c8-122">`issuerAddress` には、クライアントの通信相手となるセキュリティ トークン サービスの URI が含まれます。</span><span class="sxs-lookup"><span data-stu-id="312c8-122">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="312c8-123">`behaviorConfiguration`セキュリティトークンサービスから発行済みトークンを取得するために Windows Communication Foundation (WCF) によって作成されたチャネルでアプリケーションが使用するエンドポイント動作を指します。</span><span class="sxs-lookup"><span data-stu-id="312c8-123">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="312c8-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="312c8-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="312c8-125">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="312c8-125">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="312c8-126">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="312c8-126">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="312c8-127">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="312c8-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="312c8-128">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="312c8-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="312c8-129">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="312c8-129">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="312c8-130">方法: フェデレーション クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="312c8-130">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="312c8-131">方法: ローカル発行者を設定する</span><span class="sxs-lookup"><span data-stu-id="312c8-131">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="312c8-132">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="312c8-132">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)
