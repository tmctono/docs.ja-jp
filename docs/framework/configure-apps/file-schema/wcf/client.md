---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 7aa3755be97a839cb576d53852b75cfe50e39276
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "72773949"
---
# \<client>
<span data-ttu-id="84041-101">`client` 要素は、クライアントが接続可能なエンドポイントの一覧を定義します。</span><span class="sxs-lookup"><span data-stu-id="84041-101">The `client` element defines a list of endpoints that a client can connect to.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**

## <a name="syntax"></a><span data-ttu-id="84041-102">構文</span><span class="sxs-lookup"><span data-stu-id="84041-102">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="84041-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="84041-103">Attributes and Elements</span></span>
 <span data-ttu-id="84041-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="84041-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="84041-105">属性</span><span class="sxs-lookup"><span data-stu-id="84041-105">Attributes</span></span>
 <span data-ttu-id="84041-106">なし</span><span class="sxs-lookup"><span data-stu-id="84041-106">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="84041-107">子要素</span><span class="sxs-lookup"><span data-stu-id="84041-107">Child Elements</span></span>

|<span data-ttu-id="84041-108">要素</span><span class="sxs-lookup"><span data-stu-id="84041-108">Element</span></span>|<span data-ttu-id="84041-109">説明</span><span class="sxs-lookup"><span data-stu-id="84041-109">Description</span></span>|
|-------------|-----------------|
|[\<endpoint>](endpoint-of-client.md)|<span data-ttu-id="84041-110">このクライアントが接続できるエンドポイントを指定するエンドポイント要素のコレクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="84041-110">Contains a collection of endpoint elements that specify the endpoints that this client can connect to.</span></span>|
|[\<metadata>](metadata.md)|<span data-ttu-id="84041-111">メタデータを処理するための設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="84041-111">Contains settings for processing metadata.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="84041-112">親要素</span><span class="sxs-lookup"><span data-stu-id="84041-112">Parent Elements</span></span>

|<span data-ttu-id="84041-113">要素</span><span class="sxs-lookup"><span data-stu-id="84041-113">Element</span></span>|<span data-ttu-id="84041-114">説明</span><span class="sxs-lookup"><span data-stu-id="84041-114">Description</span></span>|
|-------------|-----------------|
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="84041-115">すべての Windows Communication Foundation (WCF) 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="84041-115">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="84041-116">解説</span><span class="sxs-lookup"><span data-stu-id="84041-116">Remarks</span></span>
 <span data-ttu-id="84041-117">`client` セクションは、クライアントが接続可能なエンドポイントの一覧を定義します。</span><span class="sxs-lookup"><span data-stu-id="84041-117">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="84041-118">クライアント セクションに示される各エンドポイントは、独自のバインディング、動作、およびコントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="84041-118">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="84041-119">各エンドポイントは、`name` 属性と `contract` 属性の組み合わせで一意に識別されます。</span><span class="sxs-lookup"><span data-stu-id="84041-119">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="84041-120">クライアント コードは、クライアントが実装するサービスのエンドポイントに接続するための `name` を指定します。</span><span class="sxs-lookup"><span data-stu-id="84041-120">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="84041-121">`name` 属性が省略されている場合、クライアントが実装するコントラクトのエンドポイントが既定のエンドポイントとして機能します。</span><span class="sxs-lookup"><span data-stu-id="84041-121">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>

 <span data-ttu-id="84041-122">さらに、このセクションはメタデータを処理するための設定も指定します。</span><span class="sxs-lookup"><span data-stu-id="84041-122">In addition, this section also specifies settings for processing metadata.</span></span>

## <a name="example"></a><span data-ttu-id="84041-123">例</span><span class="sxs-lookup"><span data-stu-id="84041-123">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="84041-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="84041-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="84041-125">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="84041-125">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="84041-126">クライアント</span><span class="sxs-lookup"><span data-stu-id="84041-126">Clients</span></span>](../../../wcf/feature-details/clients.md)
