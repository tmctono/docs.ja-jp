---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 7dce5984882e48c3e62efc44ef00b6256d9eb64e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919525"
---
# <a name="client"></a><span data-ttu-id="50ec4-101">\<client></span><span class="sxs-lookup"><span data-stu-id="50ec4-101">\<client></span></span>
<span data-ttu-id="50ec4-102">`client` 要素は、クライアントが接続可能なエンドポイントの一覧を定義します。</span><span class="sxs-lookup"><span data-stu-id="50ec4-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="50ec4-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="50ec4-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="50ec4-104">\<client></span><span class="sxs-lookup"><span data-stu-id="50ec4-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50ec4-105">構文</span><span class="sxs-lookup"><span data-stu-id="50ec4-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <client>
    <endpoint>
    </endpoint>
    <metadata>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50ec4-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="50ec4-106">Attributes and Elements</span></span>  
 <span data-ttu-id="50ec4-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="50ec4-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50ec4-108">属性</span><span class="sxs-lookup"><span data-stu-id="50ec4-108">Attributes</span></span>  
 <span data-ttu-id="50ec4-109">なし</span><span class="sxs-lookup"><span data-stu-id="50ec4-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="50ec4-110">子要素</span><span class="sxs-lookup"><span data-stu-id="50ec4-110">Child Elements</span></span>  
  
|<span data-ttu-id="50ec4-111">要素</span><span class="sxs-lookup"><span data-stu-id="50ec4-111">Element</span></span>|<span data-ttu-id="50ec4-112">説明</span><span class="sxs-lookup"><span data-stu-id="50ec4-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50ec4-113">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="50ec4-113">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="50ec4-114">このクライアントが接続可能なエンドポイントを指定するエンドポイント要素のコレクションを含みます。</span><span class="sxs-lookup"><span data-stu-id="50ec4-114">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="50ec4-115">\<metadata ></span><span class="sxs-lookup"><span data-stu-id="50ec4-115">\<metadata></span></span>](metadata.md)|<span data-ttu-id="50ec4-116">メタデータを処理するための設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="50ec4-116">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="50ec4-117">親要素</span><span class="sxs-lookup"><span data-stu-id="50ec4-117">Parent Elements</span></span>  
  
|<span data-ttu-id="50ec4-118">要素</span><span class="sxs-lookup"><span data-stu-id="50ec4-118">Element</span></span>|<span data-ttu-id="50ec4-119">説明</span><span class="sxs-lookup"><span data-stu-id="50ec4-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50ec4-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="50ec4-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="50ec4-121">すべての Windows Communication Foundation (WCF) 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="50ec4-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50ec4-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="50ec4-122">Remarks</span></span>  
 <span data-ttu-id="50ec4-123">`client` セクションは、クライアントが接続可能なエンドポイントの一覧を定義します。</span><span class="sxs-lookup"><span data-stu-id="50ec4-123">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="50ec4-124">クライアント セクションに示される各エンドポイントは、独自のバインディング、動作、およびコントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="50ec4-124">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="50ec4-125">各エンドポイントは、`name` 属性と `contract` 属性の組み合わせで一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="50ec4-125">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="50ec4-126">クライアント コードは、クライアントが実装するサービスのエンドポイントに接続するための `name` を指定します。</span><span class="sxs-lookup"><span data-stu-id="50ec4-126">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="50ec4-127">`name` 属性が省略されている場合、クライアントが実装するコントラクトのエンドポイントが既定のエンドポイントとして機能します。</span><span class="sxs-lookup"><span data-stu-id="50ec4-127">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="50ec4-128">さらに、このセクションはメタデータを処理するための設定も指定します。</span><span class="sxs-lookup"><span data-stu-id="50ec4-128">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50ec4-129">例</span><span class="sxs-lookup"><span data-stu-id="50ec4-129">Example</span></span>  
  
```xml  
<client>
  <endpoint address="/HelloWorld/"
            bindingConfiguration="usingDefaults"
            name="MyBinding"
            binding="customBinding"
            contract="HelloWorld">
    <addressProperties actingAs="http://www.microsoft.com/TestActor"
                       identityData="BasicReadWrite"
                       identityType="Spn"
                       isAddressPrivate="false">
  </endpoint>
</client>
```  
  
## <a name="see-also"></a><span data-ttu-id="50ec4-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="50ec4-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="50ec4-131">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="50ec4-131">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="50ec4-132">クライアント</span><span class="sxs-lookup"><span data-stu-id="50ec4-132">Clients</span></span>](../../../wcf/feature-details/clients.md)
