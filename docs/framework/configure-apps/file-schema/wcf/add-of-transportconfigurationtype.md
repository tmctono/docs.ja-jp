---
title: <add> の <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: 9bef44ed39ee892080342058206f779b38fb460d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151156"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="ae1f0-102">\<add> の \<transportConfigurationType></span><span class="sxs-lookup"><span data-stu-id="ae1f0-102">\<add> of \<transportConfigurationType></span></span>

<span data-ttu-id="ae1f0-103">この要素は、特定のトランスポートの種類を識別するキーと値のペアです。</span><span class="sxs-lookup"><span data-stu-id="ae1f0-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="ae1f0-104">構文</span><span class="sxs-lookup"><span data-stu-id="ae1f0-104">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae1f0-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ae1f0-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ae1f0-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae1f0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae1f0-107">属性</span><span class="sxs-lookup"><span data-stu-id="ae1f0-107">Attributes</span></span>  
  
|<span data-ttu-id="ae1f0-108">属性</span><span class="sxs-lookup"><span data-stu-id="ae1f0-108">Attribute</span></span>|<span data-ttu-id="ae1f0-109">説明</span><span class="sxs-lookup"><span data-stu-id="ae1f0-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ae1f0-110">name</span><span class="sxs-lookup"><span data-stu-id="ae1f0-110">name</span></span>|<span data-ttu-id="ae1f0-111">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="ae1f0-111">Required String attribute.</span></span><br /><br /> <span data-ttu-id="ae1f0-112">トランスポートの種類を一意に識別するユーザー定義キーを含みます。</span><span class="sxs-lookup"><span data-stu-id="ae1f0-112">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="ae1f0-113">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="ae1f0-113">transportConfigurationType</span></span>|<span data-ttu-id="ae1f0-114">特定のトランスポートを実装する種類を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="ae1f0-114">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae1f0-115">子要素</span><span class="sxs-lookup"><span data-stu-id="ae1f0-115">Child Elements</span></span>  

 <span data-ttu-id="ae1f0-116">None</span><span class="sxs-lookup"><span data-stu-id="ae1f0-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae1f0-117">親要素</span><span class="sxs-lookup"><span data-stu-id="ae1f0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ae1f0-118">要素</span><span class="sxs-lookup"><span data-stu-id="ae1f0-118">Element</span></span>|<span data-ttu-id="ae1f0-119">説明</span><span class="sxs-lookup"><span data-stu-id="ae1f0-119">Description</span></span>|  
|-------------|-----------------|  
|[\<transportConfigurationTypes>](transportconfigurationtypes.md)|<span data-ttu-id="ae1f0-120">特定のトランスポートを実装する型のコレクション。</span><span class="sxs-lookup"><span data-stu-id="ae1f0-120">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ae1f0-121">例</span><span class="sxs-lookup"><span data-stu-id="ae1f0-121">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="ae1f0-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae1f0-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="ae1f0-123">ホスティング</span><span class="sxs-lookup"><span data-stu-id="ae1f0-123">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
