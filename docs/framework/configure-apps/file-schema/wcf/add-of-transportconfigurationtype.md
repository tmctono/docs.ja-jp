---
title: <add> の <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: adf4cd7f02db6535c5950443d09476a9a5ff63fb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850308"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="5c101-102">\<transportConfigurationType > の\<> の追加</span><span class="sxs-lookup"><span data-stu-id="5c101-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="5c101-103">この要素は、特定のトランスポートの種類を識別するキーと値のペアです。</span><span class="sxs-lookup"><span data-stu-id="5c101-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
<span data-ttu-id="5c101-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5c101-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5c101-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5c101-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5c101-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceHostingEnvironment >** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="5c101-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="5c101-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<transportConfigurationTypes >** ](transportconfigurationtypes.md)</span><span class="sxs-lookup"><span data-stu-id="5c101-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)</span></span>\
<span data-ttu-id="5c101-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="5c101-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c101-109">構文</span><span class="sxs-lookup"><span data-stu-id="5c101-109">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c101-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5c101-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5c101-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c101-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c101-112">属性</span><span class="sxs-lookup"><span data-stu-id="5c101-112">Attributes</span></span>  
  
|<span data-ttu-id="5c101-113">属性</span><span class="sxs-lookup"><span data-stu-id="5c101-113">Attribute</span></span>|<span data-ttu-id="5c101-114">説明</span><span class="sxs-lookup"><span data-stu-id="5c101-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c101-115">name</span><span class="sxs-lookup"><span data-stu-id="5c101-115">name</span></span>|<span data-ttu-id="5c101-116">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="5c101-116">Required String attribute.</span></span><br /><br /> <span data-ttu-id="5c101-117">トランスポートの種類を一意に識別するユーザー定義キーを含みます。</span><span class="sxs-lookup"><span data-stu-id="5c101-117">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="5c101-118">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="5c101-118">transportConfigurationType</span></span>|<span data-ttu-id="5c101-119">特定のトランスポートを実装する種類を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="5c101-119">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c101-120">子要素</span><span class="sxs-lookup"><span data-stu-id="5c101-120">Child Elements</span></span>  
 <span data-ttu-id="5c101-121">なし</span><span class="sxs-lookup"><span data-stu-id="5c101-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5c101-122">親要素</span><span class="sxs-lookup"><span data-stu-id="5c101-122">Parent Elements</span></span>  
  
|<span data-ttu-id="5c101-123">要素</span><span class="sxs-lookup"><span data-stu-id="5c101-123">Element</span></span>|<span data-ttu-id="5c101-124">説明</span><span class="sxs-lookup"><span data-stu-id="5c101-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c101-125">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="5c101-125">\<transportConfigurationTypes></span></span>](transportconfigurationtypes.md)|<span data-ttu-id="5c101-126">特定のトランスポートを実装する型のコレクション。</span><span class="sxs-lookup"><span data-stu-id="5c101-126">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5c101-127">例</span><span class="sxs-lookup"><span data-stu-id="5c101-127">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="5c101-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c101-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="5c101-129">ホスティング</span><span class="sxs-lookup"><span data-stu-id="5c101-129">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
