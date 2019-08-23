---
title: <issuerChannelBehaviors> 要素
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: e0e41b4f6d66cd4455c43dda7c77798553f2b58f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929925"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="62121-102">\<issuerChannelBehaviors > 要素</span><span class="sxs-lookup"><span data-stu-id="62121-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="62121-103">指定されたサービストークンサービスとの通信時に使用される Windows Communication Foundation (WCF) クライアントエンドポイントの動作 (構成で定義されている) のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="62121-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="62121-104">定義された動作には、 [ \<clientCredentials >](clientcredentials.md)要素を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="62121-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

```xml
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior>
        <clientCredentials>
          <issuedToken>
            <issuerChannelBehaviors>
```

## <a name="syntax"></a><span data-ttu-id="62121-105">構文</span><span class="sxs-lookup"><span data-stu-id="62121-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="62121-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="62121-106">Attributes and Elements</span></span>

<span data-ttu-id="62121-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="62121-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="62121-108">属性</span><span class="sxs-lookup"><span data-stu-id="62121-108">Attributes</span></span>

<span data-ttu-id="62121-109">なし。</span><span class="sxs-lookup"><span data-stu-id="62121-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="62121-110">子要素</span><span class="sxs-lookup"><span data-stu-id="62121-110">Child Elements</span></span>

|<span data-ttu-id="62121-111">要素</span><span class="sxs-lookup"><span data-stu-id="62121-111">Element</span></span>|<span data-ttu-id="62121-112">説明</span><span class="sxs-lookup"><span data-stu-id="62121-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="62121-113">\<add></span><span class="sxs-lookup"><span data-stu-id="62121-113">\<add></span></span>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="62121-114">コレクションに動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="62121-114">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="62121-115">親要素</span><span class="sxs-lookup"><span data-stu-id="62121-115">Parent Elements</span></span>

|<span data-ttu-id="62121-116">要素</span><span class="sxs-lookup"><span data-stu-id="62121-116">Element</span></span>|<span data-ttu-id="62121-117">説明</span><span class="sxs-lookup"><span data-stu-id="62121-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="62121-118">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="62121-118">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="62121-119">サービスに対するクライアントの認証に使用されるカスタム トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="62121-119">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="62121-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="62121-120">Remarks</span></span>

<span data-ttu-id="62121-121">この要素を使用するのは、なんらかの動作 (`<clientCredentials>` 要素を含む動作以外) を使用してサービスと通信する必要がある場合です。</span><span class="sxs-lookup"><span data-stu-id="62121-121">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="62121-122">たとえば、 [ \<dataContractSerializer >](datacontractserializer-element.md) behavior 要素を含める必要がある場合です。</span><span class="sxs-lookup"><span data-stu-id="62121-122">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="62121-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="62121-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="62121-124">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="62121-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="62121-125">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="62121-125">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="62121-126">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="62121-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="62121-127">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="62121-127">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="62121-128">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="62121-128">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="62121-129">方法: フェデレーションクライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="62121-129">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="62121-130">方法: ローカル発行者を構成する</span><span class="sxs-lookup"><span data-stu-id="62121-130">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="62121-131">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="62121-131">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
