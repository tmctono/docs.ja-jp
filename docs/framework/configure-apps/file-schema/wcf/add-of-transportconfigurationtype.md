---
title: <add> の <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: 483ede53df13c896b88171910031dbe9793d66dc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920033"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="72113-102">\<transportConfigurationType > の\<> の追加</span><span class="sxs-lookup"><span data-stu-id="72113-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="72113-103">この要素は、特定のトランスポートの種類を識別するキーと値のペアです。</span><span class="sxs-lookup"><span data-stu-id="72113-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="72113-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="72113-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="72113-105">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="72113-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="72113-106">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="72113-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="72113-107">\<add></span><span class="sxs-lookup"><span data-stu-id="72113-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72113-108">構文</span><span class="sxs-lookup"><span data-stu-id="72113-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72113-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="72113-109">Attributes and Elements</span></span>  
 <span data-ttu-id="72113-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="72113-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72113-111">属性</span><span class="sxs-lookup"><span data-stu-id="72113-111">Attributes</span></span>  
  
|<span data-ttu-id="72113-112">属性</span><span class="sxs-lookup"><span data-stu-id="72113-112">Attribute</span></span>|<span data-ttu-id="72113-113">説明</span><span class="sxs-lookup"><span data-stu-id="72113-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="72113-114">name</span><span class="sxs-lookup"><span data-stu-id="72113-114">name</span></span>|<span data-ttu-id="72113-115">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="72113-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="72113-116">トランスポートの種類を一意に識別するユーザー定義キーを含みます。</span><span class="sxs-lookup"><span data-stu-id="72113-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="72113-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="72113-117">transportConfigurationType</span></span>|<span data-ttu-id="72113-118">特定のトランスポートを実装する種類を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="72113-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72113-119">子要素</span><span class="sxs-lookup"><span data-stu-id="72113-119">Child Elements</span></span>  
 <span data-ttu-id="72113-120">なし</span><span class="sxs-lookup"><span data-stu-id="72113-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72113-121">親要素</span><span class="sxs-lookup"><span data-stu-id="72113-121">Parent Elements</span></span>  
  
|<span data-ttu-id="72113-122">要素</span><span class="sxs-lookup"><span data-stu-id="72113-122">Element</span></span>|<span data-ttu-id="72113-123">説明</span><span class="sxs-lookup"><span data-stu-id="72113-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72113-124">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="72113-124">\<transportConfigurationTypes></span></span>](transportconfigurationtypes.md)|<span data-ttu-id="72113-125">特定のトランスポートを実装する型のコレクション。</span><span class="sxs-lookup"><span data-stu-id="72113-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="72113-126">例</span><span class="sxs-lookup"><span data-stu-id="72113-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="72113-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="72113-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="72113-128">ホスティング</span><span class="sxs-lookup"><span data-stu-id="72113-128">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
