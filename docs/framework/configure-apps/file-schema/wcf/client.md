---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: b3234bfa60cd1e3c88778951fc27301c615c84ba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148959"
---
# \<client>

<span data-ttu-id="1e4f6-101">`client` 要素は、クライアントが接続可能なエンドポイントの一覧を定義します。</span><span class="sxs-lookup"><span data-stu-id="1e4f6-101">The `client` element defines a list of endpoints that a client can connect to.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**

## <a name="syntax"></a><span data-ttu-id="1e4f6-102">構文</span><span class="sxs-lookup"><span data-stu-id="1e4f6-102">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="1e4f6-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1e4f6-103">Attributes and Elements</span></span>

 <span data-ttu-id="1e4f6-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e4f6-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1e4f6-105">属性</span><span class="sxs-lookup"><span data-stu-id="1e4f6-105">Attributes</span></span>

 <span data-ttu-id="1e4f6-106">None</span><span class="sxs-lookup"><span data-stu-id="1e4f6-106">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="1e4f6-107">子要素</span><span class="sxs-lookup"><span data-stu-id="1e4f6-107">Child Elements</span></span>

|<span data-ttu-id="1e4f6-108">要素</span><span class="sxs-lookup"><span data-stu-id="1e4f6-108">Element</span></span>|<span data-ttu-id="1e4f6-109">説明</span><span class="sxs-lookup"><span data-stu-id="1e4f6-109">Description</span></span>|
|-------------|-----------------|
|[\<endpoint>](endpoint-of-client.md)|<span data-ttu-id="1e4f6-110">このクライアントが接続できるエンドポイントを指定するエンドポイント要素のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="1e4f6-110">Contains a collection of endpoint elements that specify the endpoints that this client can connect to.</span></span>|
|[\<metadata>](metadata.md)|<span data-ttu-id="1e4f6-111">メタデータを処理するための設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="1e4f6-111">Contains settings for processing metadata.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1e4f6-112">親要素</span><span class="sxs-lookup"><span data-stu-id="1e4f6-112">Parent Elements</span></span>

|<span data-ttu-id="1e4f6-113">要素</span><span class="sxs-lookup"><span data-stu-id="1e4f6-113">Element</span></span>|<span data-ttu-id="1e4f6-114">説明</span><span class="sxs-lookup"><span data-stu-id="1e4f6-114">Description</span></span>|
|-------------|-----------------|
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="1e4f6-115">すべての Windows Communication Foundation (WCF) 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="1e4f6-115">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1e4f6-116">解説</span><span class="sxs-lookup"><span data-stu-id="1e4f6-116">Remarks</span></span>

 <span data-ttu-id="1e4f6-117">`client` セクションは、クライアントが接続可能なエンドポイントの一覧を定義します。</span><span class="sxs-lookup"><span data-stu-id="1e4f6-117">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="1e4f6-118">クライアント セクションに示される各エンドポイントは、独自のバインディング、動作、およびコントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="1e4f6-118">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="1e4f6-119">各エンドポイントは、`name` 属性と `contract` 属性の組み合わせで一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="1e4f6-119">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="1e4f6-120">クライアント コードは、クライアントが実装するサービスのエンドポイントに接続するための `name` を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e4f6-120">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="1e4f6-121">`name` 属性が省略されている場合、クライアントが実装するコントラクトのエンドポイントが既定のエンドポイントとして機能します。</span><span class="sxs-lookup"><span data-stu-id="1e4f6-121">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>

 <span data-ttu-id="1e4f6-122">さらに、このセクションはメタデータを処理するための設定も指定します。</span><span class="sxs-lookup"><span data-stu-id="1e4f6-122">In addition, this section also specifies settings for processing metadata.</span></span>

## <a name="example"></a><span data-ttu-id="1e4f6-123">例</span><span class="sxs-lookup"><span data-stu-id="1e4f6-123">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1e4f6-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e4f6-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="1e4f6-125">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="1e4f6-125">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="1e4f6-126">クライアント</span><span class="sxs-lookup"><span data-stu-id="1e4f6-126">Clients</span></span>](../../../wcf/feature-details/clients.md)
