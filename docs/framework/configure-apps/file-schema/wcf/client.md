---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 7aa3755be97a839cb576d53852b75cfe50e39276
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72773949"
---
# <a name="client"></a><span data-ttu-id="99797-101">\<client ></span><span class="sxs-lookup"><span data-stu-id="99797-101">\<client></span></span>
<span data-ttu-id="99797-102">`client` 要素は、クライアントが接続可能なエンドポイントの一覧を定義します。</span><span class="sxs-lookup"><span data-stu-id="99797-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>

<span data-ttu-id="99797-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="99797-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="99797-104">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="99797-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="99797-105">&nbsp; &nbsp; &nbsp; &nbsp; **\<client >**</span><span class="sxs-lookup"><span data-stu-id="99797-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**</span></span>

## <a name="syntax"></a><span data-ttu-id="99797-106">構文</span><span class="sxs-lookup"><span data-stu-id="99797-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="99797-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="99797-107">Attributes and Elements</span></span>
 <span data-ttu-id="99797-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="99797-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="99797-109">属性</span><span class="sxs-lookup"><span data-stu-id="99797-109">Attributes</span></span>
 <span data-ttu-id="99797-110">None</span><span class="sxs-lookup"><span data-stu-id="99797-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="99797-111">子要素</span><span class="sxs-lookup"><span data-stu-id="99797-111">Child Elements</span></span>

|<span data-ttu-id="99797-112">要素</span><span class="sxs-lookup"><span data-stu-id="99797-112">Element</span></span>|<span data-ttu-id="99797-113">説明</span><span class="sxs-lookup"><span data-stu-id="99797-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="99797-114">\< エンドポイント ></span><span class="sxs-lookup"><span data-stu-id="99797-114">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="99797-115">このクライアントが接続できるエンドポイントを指定するエンドポイント要素のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="99797-115">Contains a collection of endpoint elements that specify the endpoints that this client can connect to.</span></span>|
|[<span data-ttu-id="99797-116">\<metadata ></span><span class="sxs-lookup"><span data-stu-id="99797-116">\<metadata></span></span>](metadata.md)|<span data-ttu-id="99797-117">メタデータを処理するための設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="99797-117">Contains settings for processing metadata.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="99797-118">親要素</span><span class="sxs-lookup"><span data-stu-id="99797-118">Parent Elements</span></span>

|<span data-ttu-id="99797-119">要素</span><span class="sxs-lookup"><span data-stu-id="99797-119">Element</span></span>|<span data-ttu-id="99797-120">説明</span><span class="sxs-lookup"><span data-stu-id="99797-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="99797-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="99797-121">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="99797-122">すべての Windows Communication Foundation (WCF) 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="99797-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="99797-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="99797-123">Remarks</span></span>
 <span data-ttu-id="99797-124">`client` セクションは、クライアントが接続可能なエンドポイントの一覧を定義します。</span><span class="sxs-lookup"><span data-stu-id="99797-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="99797-125">クライアント セクションに示される各エンドポイントは、独自のバインディング、動作、およびコントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="99797-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="99797-126">各エンドポイントは、`name` 属性と `contract` 属性の組み合わせで一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="99797-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="99797-127">クライアント コードは、クライアントが実装するサービスのエンドポイントに接続するための `name` を指定します。</span><span class="sxs-lookup"><span data-stu-id="99797-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="99797-128">`name` 属性が省略されている場合、クライアントが実装するコントラクトのエンドポイントが既定のエンドポイントとして機能します。</span><span class="sxs-lookup"><span data-stu-id="99797-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>

 <span data-ttu-id="99797-129">さらに、このセクションはメタデータを処理するための設定も指定します。</span><span class="sxs-lookup"><span data-stu-id="99797-129">In addition, this section also specifies settings for processing metadata.</span></span>

## <a name="example"></a><span data-ttu-id="99797-130">例</span><span class="sxs-lookup"><span data-stu-id="99797-130">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="99797-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="99797-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="99797-132">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="99797-132">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="99797-133">クライアント</span><span class="sxs-lookup"><span data-stu-id="99797-133">Clients</span></span>](../../../wcf/feature-details/clients.md)
