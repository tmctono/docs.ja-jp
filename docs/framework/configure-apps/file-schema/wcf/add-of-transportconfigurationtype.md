---
title: <add> の <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: adf4cd7f02db6535c5950443d09476a9a5ff63fb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850308"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="7720b-102">\<add> の \<transportConfigurationType></span><span class="sxs-lookup"><span data-stu-id="7720b-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="7720b-103">この要素は、特定のトランスポートの種類を識別するキーと値のペアです。</span><span class="sxs-lookup"><span data-stu-id="7720b-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="7720b-104">構文</span><span class="sxs-lookup"><span data-stu-id="7720b-104">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7720b-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7720b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7720b-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7720b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7720b-107">属性</span><span class="sxs-lookup"><span data-stu-id="7720b-107">Attributes</span></span>  
  
|<span data-ttu-id="7720b-108">属性</span><span class="sxs-lookup"><span data-stu-id="7720b-108">Attribute</span></span>|<span data-ttu-id="7720b-109">説明</span><span class="sxs-lookup"><span data-stu-id="7720b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7720b-110">name</span><span class="sxs-lookup"><span data-stu-id="7720b-110">name</span></span>|<span data-ttu-id="7720b-111">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="7720b-111">Required String attribute.</span></span><br /><br /> <span data-ttu-id="7720b-112">トランスポートの種類を一意に識別するユーザー定義キーを含みます。</span><span class="sxs-lookup"><span data-stu-id="7720b-112">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="7720b-113">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="7720b-113">transportConfigurationType</span></span>|<span data-ttu-id="7720b-114">特定のトランスポートを実装する種類を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="7720b-114">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7720b-115">子要素</span><span class="sxs-lookup"><span data-stu-id="7720b-115">Child Elements</span></span>  
 <span data-ttu-id="7720b-116">なし</span><span class="sxs-lookup"><span data-stu-id="7720b-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7720b-117">親要素</span><span class="sxs-lookup"><span data-stu-id="7720b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="7720b-118">要素</span><span class="sxs-lookup"><span data-stu-id="7720b-118">Element</span></span>|<span data-ttu-id="7720b-119">Description</span><span class="sxs-lookup"><span data-stu-id="7720b-119">Description</span></span>|  
|-------------|-----------------|  
|[\<transportConfigurationTypes>](transportconfigurationtypes.md)|<span data-ttu-id="7720b-120">特定のトランスポートを実装する型のコレクション。</span><span class="sxs-lookup"><span data-stu-id="7720b-120">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7720b-121">例</span><span class="sxs-lookup"><span data-stu-id="7720b-121">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="7720b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="7720b-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="7720b-123">ホスティング</span><span class="sxs-lookup"><span data-stu-id="7720b-123">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
