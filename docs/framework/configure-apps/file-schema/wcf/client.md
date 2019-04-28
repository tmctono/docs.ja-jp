---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 2e0352efdd5b709984338fe4484b120bddb7d545
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704298"
---
# <a name="client"></a><span data-ttu-id="0037b-101">\<client></span><span class="sxs-lookup"><span data-stu-id="0037b-101">\<client></span></span>
<span data-ttu-id="0037b-102">`client` 要素は、クライアントが接続可能なエンドポイントの一覧を定義します。</span><span class="sxs-lookup"><span data-stu-id="0037b-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="0037b-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0037b-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="0037b-104">\<client></span><span class="sxs-lookup"><span data-stu-id="0037b-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0037b-105">構文</span><span class="sxs-lookup"><span data-stu-id="0037b-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0037b-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0037b-106">Attributes and Elements</span></span>  
 <span data-ttu-id="0037b-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0037b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0037b-108">属性</span><span class="sxs-lookup"><span data-stu-id="0037b-108">Attributes</span></span>  
 <span data-ttu-id="0037b-109">なし</span><span class="sxs-lookup"><span data-stu-id="0037b-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0037b-110">子要素</span><span class="sxs-lookup"><span data-stu-id="0037b-110">Child Elements</span></span>  
  
|<span data-ttu-id="0037b-111">要素</span><span class="sxs-lookup"><span data-stu-id="0037b-111">Element</span></span>|<span data-ttu-id="0037b-112">説明</span><span class="sxs-lookup"><span data-stu-id="0037b-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0037b-113">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="0037b-113">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="0037b-114">このクライアントが接続可能なエンドポイントを指定するエンドポイント要素のコレクションを含みます。</span><span class="sxs-lookup"><span data-stu-id="0037b-114">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="0037b-115">\<metadata ></span><span class="sxs-lookup"><span data-stu-id="0037b-115">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="0037b-116">メタデータを処理するための設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="0037b-116">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0037b-117">親要素</span><span class="sxs-lookup"><span data-stu-id="0037b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0037b-118">要素</span><span class="sxs-lookup"><span data-stu-id="0037b-118">Element</span></span>|<span data-ttu-id="0037b-119">説明</span><span class="sxs-lookup"><span data-stu-id="0037b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0037b-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0037b-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="0037b-121">すべての Windows Communication Foundation (WCF) 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="0037b-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0037b-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="0037b-122">Remarks</span></span>  
 <span data-ttu-id="0037b-123">`client` セクションは、クライアントが接続可能なエンドポイントの一覧を定義します。</span><span class="sxs-lookup"><span data-stu-id="0037b-123">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="0037b-124">クライアント セクションに示される各エンドポイントは、独自のバインディング、動作、およびコントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="0037b-124">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="0037b-125">各エンドポイントは、`name` 属性と `contract` 属性の組み合わせで一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="0037b-125">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="0037b-126">クライアント コードは、クライアントが実装するサービスのエンドポイントに接続するための `name` を指定します。</span><span class="sxs-lookup"><span data-stu-id="0037b-126">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="0037b-127">`name` 属性が省略されている場合、クライアントが実装するコントラクトのエンドポイントが既定のエンドポイントとして機能します。</span><span class="sxs-lookup"><span data-stu-id="0037b-127">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="0037b-128">さらに、このセクションはメタデータを処理するための設定も指定します。</span><span class="sxs-lookup"><span data-stu-id="0037b-128">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0037b-129">例</span><span class="sxs-lookup"><span data-stu-id="0037b-129">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0037b-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="0037b-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="0037b-131">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="0037b-131">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="0037b-132">クライアント</span><span class="sxs-lookup"><span data-stu-id="0037b-132">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
